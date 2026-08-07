# EBP-001 — Rollback Plan

**ID:** EBP-001-ROLLBACK

---

## 1. Principle

Rollback must be **flag-first**, not redeploy-last-resort.

Teacher OS Wave 1 is additive. Disabling flags restores classic EduVijna teacher workflows.

---

## 2. Immediate rollback (minutes)

| Step | Action |
|------|--------|
| 1 | Set `teacher_os_enabled=false` in API `FEATURE_FLAGS_JSON` / env |
| 2 | Set child flags false: `today_dashboard_enabled`, `review_queue_enabled`, `continuous_context_enabled` |
| 3 | Set web `VITE_TEACHER_OS_ENABLED=false` (or rely on meta if web reads API) |
| 4 | Verify `/dashboard` shows classic `HomePage` |
| 5 | Verify no Teacher OS nav for standard teachers |
| 6 | Verify Platform AI / legacy generators still work |

**Expected RTO:** configuration change + cache/CDN refresh as applicable.

---

## 3. Partial rollback

| Symptom | Action |
|---------|--------|
| Mission broken, Queue OK | Disable `today_dashboard_enabled` only; keep shell/queue if useful |
| Queue broken | Disable `review_queue_enabled`; hide Mission Review CTA; keep generators classic |
| Context broken | Disable `continuous_context_enabled`; generators still usable |

---

## 4. Data handling

| Data | On rollback |
|------|-------------|
| Pending review content rows | **Retain** — accessible via classic content/history/preview |
| Approvals already made | **Retain** |
| Continuous Context sessions | Retain; unused when flag off |
| No destructive migrations in Wave 1 | Required — avoids hard rollback |

---

## 5. Code rollback (if flag insufficient)

1. Revert Teacher OS PRs on `Quiz-React` / `eduvijna-api` main  
2. Redeploy previous known-good artifacts  
3. Keep flags false as belt-and-suspenders  

Prefer not to need this if flags are correctly wired.

---

## 6. Rollback drill (Sprint 4 mandatory)

| Step | Pass criteria |
|------|---------------|
| Enable Teacher OS on Preview | Mission visible |
| Disable all Teacher OS flags | Classic home + nav restored |
| Generate worksheet | Still succeeds |
| Pending queue items | Still openable via classic preview/history |

Record drill evidence in EBP-001 review package.

---

## 7. Communication

On Pilot rollback: notify Product + pilot school champion; state that classic workflows remain available; file incident with risk ID if principle-related (e.g. publish bypass).
