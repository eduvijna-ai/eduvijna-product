# Feature Flag Standards

**ID:** ENG-FLAG-001  
**Parent:** ENGINEERING_CONSTITUTION.md  
**Complements:** Product roadmap rollout · EBP-001 `FEATURE_FLAGS.md`

---

## 1. Policy

**Everything ships behind flags** (Constitution).  
Defaults **false** in production until entitled rollout.

---

## 2. Required metadata (every flag)

| Field | Description |
|-------|-------------|
| **Key** | snake_case, stable |
| **Owner** | Named role/team (Product or Engineering lead) |
| **Purpose** | One-sentence why it exists |
| **Default state** | Usually `false` in prod |
| **Rollout plan** | Preview → Pilot → GA (or env-specific) |
| **Removal criteria** | When the flag will be deleted (e.g. “100% GA + 1 term + no rollback”) |

Optional: depends_on (parent flag), tenant targeting notes.

---

## 3. Wave 1 catalogue (reference)

| Key | Owner | Purpose | Default | Rollout | Removal criteria |
|-----|-------|---------|---------|---------|------------------|
| `teacher_os_enabled` | Eng + Product | Master Teacher OS shell | false | Preview → Pilot → GA | GA stable 1 term; legacy nav retired per migration |
| `today_dashboard_enabled` | Eng + Product | Mission + Today dashboard | false | After shell | Fold into master after GA |
| `review_queue_enabled` | Eng + Product | Review Queue + badge | false | With/after Mission | Fold into master after GA |
| `continuous_context_enabled` | Eng + Product | Session thread refine | false | After Queue | Fold into master after GA |

New flags must be added to blueprint FEATURE_FLAGS docs **and** listed with full metadata in the PR.

---

## 4. Implementation rules

1. Gate routes, nav, and behaviour — not only CSS hide.  
2. Prefer API `/health/meta` (or equivalent) as source of truth for web.  
3. Child flags ineffective unless parent `teacher_os_enabled` is true.  
4. E2E covers flag on and flag off.  
5. Rollback = disable flags first (`RELEASE_STANDARDS.md`).

---

## 5. Removal discipline

Flags are not permanent configuration.  
Track removal criteria; open tech-debt tickets when GA criteria met.
