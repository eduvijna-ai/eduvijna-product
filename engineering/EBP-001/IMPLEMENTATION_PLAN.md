# EBP-001 — Implementation Plan

**ID:** EBP-001-PLAN  
**Wave:** 1 — Teacher OS Shell  
**Repos:** `Quiz-React` (eduvijna-web) · `eduvijna-api`

---

## 1. Strategy

Integrate Teacher OS as an **additive shell** on the current teacher experience.

| Principle | Practice |
|-----------|----------|
| Evolve, don't replace | Keep legacy nav/generators reachable when flags off or via Legacy fallback |
| Orchestrate, don't rewrite | Call existing Platform AI + legacy generate endpoints |
| Vertical slices | Each sprint ships UI + API + tests + flag |
| Safe rollout | All Teacher OS surfaces behind flags |

---

## 2. Current-state anchors (reuse)

### Web (`Quiz-React`)

| Concern | Existing anchor |
|---------|-----------------|
| Auth / login | `src/features/auth/`, `/login`, `ProtectedRoute` |
| Shell / sidebar | `src/components/layouts/MainLayout.tsx` |
| Default landing | `/dashboard`, `/home` → `HomePage` |
| Platform AI generators | `/platform-ai/*`, `src/features/platform-ai/` |
| Content generate client | `src/api/contentApi.ts` → `POST /api/v1/content/generate` |
| Tests | Vitest + Playwright |

### API (`eduvijna-api`)

| Concern | Existing anchor |
|---------|-----------------|
| Auth | `/api/v1/auth/*`, JWT `Authorize()` |
| Unified generate | `POST /api/v1/content/generate` |
| Content list / lifecycle | `/api/v1/content*`, `ApprovalState` / `ReviewState` |
| Session continuity | `/api/v1/content-ai/sessions*` |
| Feature flags | `app/platform/feature_flags.py`, `FEATURE_FLAGS_JSON`, `/health/meta` |
| Tests | pytest |

---

## 3. Target experience (Wave 1)

### 3.1 Navigation (outcome-first)

When `teacher_os_enabled`:

```text
Today · Prepare · Teach · Assess · Improve · Library · AI Assistant · Settings
```

- Implemented as Teacher OS nav section in `MainLayout` (and/or seeded quiz-nav items).  
- Existing feature-first / Platform AI / ERP entries remain available behind migration / legacy visibility rules.  
- Routes live under `/teacher-os/*` plus Mission overrides `/dashboard` when `today_dashboard_enabled`.

### 3.2 Today's Mission (login landing)

Replace teacher default landing (when flags on) with Mission briefing:

- Greeting  
- Today's Mission counts (classes, assessments, PTM)  
- AI Prepared / Ready for Review status  
- CTA → Review Queue  

### 3.3 Today Dashboard

Mission + expandable day workspace:

- Today's Classes  
- Pending Reviews  
- Recent Activity  
- Quick Continue  
- AI Recommendations  
- Review Queue preview  
- Teacher Memory Summary (read)  
- School Context Summary (read)

### 3.4 Review Queue (mandatory)

Every AI-generated **Artifact** from Teacher OS / Platform AI generate flows enters the **generic** Review Queue (Decision A).

Types are attributes (`worksheet`, `quiz`, `lesson_plan`, …) — the queue does not fork per type.

**Nothing reaches students without teacher approval.**

**Work** (Decision B) groups Artifacts durably; **Intent** completes after orchestration.

Implementation approach:

1. On successful `content/generate` (and mapped legacy generates used by Teacher OS), ensure content row carries pending approval / needs-review state.  
2. `GET` list endpoint filtered for current teacher + pending review.  
3. UI `/teacher-os/review` — approve / reject / open preview (reuse `/platform-ai/preview/:id`).  
4. Publish/assign only after approve.

### 3.5 Continuous Context

Within a teaching session / active Intent thread:

- Preserve class, subject, topic, active artefact focus  
- “Make it harder” applies to focused artefact without re-prompting Grade/topic  
- Reuse/extend Content AI sessions + client session store; add Teacher OS thread metadata as needed  

Do **not** require repeated prompts within the same workflow.

---

## 4. Technical approach by layer

### 4.1 Feature flags

| Flag | Default Wave 1 Preview |
|------|------------------------|
| `teacher_os_enabled` | false (env/JSON true in preview) |
| `today_dashboard_enabled` | depends on teacher_os |
| `review_queue_enabled` | depends on teacher_os |
| `continuous_context_enabled` | depends on teacher_os |

API: extend `feature_flags.py` + expose on `/health/meta`.  
Web: `src/config/teacherOsFeature.ts` (env) **and/or** consume health/meta for alignment.

### 4.2 API work (minimal additive)

| Work | Notes |
|------|-------|
| Flags | `teacher_os_*` keys |
| Review queue list | Filter existing content by approval/review state + owner |
| Approve / reject | Thin endpoints or extend content service decisions already in domain |
| Continuous context | Prefer Content AI sessions; add thread fields only if gap |
| Mission aggregates | Compose from timetable/ERP/content pending counts — **no major schema redesign**; use existing sources with graceful empty states |

### 4.3 Web work

| Work | Notes |
|------|-------|
| `teacher-os` feature module | routes, layout, components |
| Mission + Today dashboard | landing |
| Review Queue page | list + actions |
| Continuous Context strip / provider | wraps Prepare/AI Assistant flows |
| Memory / School Context summary cards | read-only from profile + platform school context |
| Nav integration | MainLayout gated section |
| Keep generators | Deep-link to `/platform-ai/*` |

### 4.4 Performance budgets

| Surface | Target |
|---------|--------|
| Dashboard / Mission | &lt; 2 seconds |
| Navigation interaction | &lt; 100 ms |
| AI status updates | &lt; 500 ms |
| Orchestration | Visible progress indicators (never silent hang) |

---

## 5. Vertical-slice delivery rule

Every sprint must end with:

1. At least one teacher-visible behaviour behind a flag  
2. Matching API support if needed  
3. Automated tests green  
4. Rollback via flag documented  

See `SPRINT_BREAKDOWN.md` and `TASKS.md`.

---

## 6. Explicit non-goals

- Rewriting worksheet/quiz/lesson/OCR/analytics engines  
- New model providers  
- Student/Parent/Principal OS  
- Major DB redesign / platform extraction  

---

## 7. Definition of Done (per slice)

- [ ] User story demonstrated on Preview flag  
- [ ] Unit + integration + UI tests added/updated  
- [ ] Accessibility checks for new interactive surfaces  
- [ ] Regression suite for generators / login / nav still passes  
- [ ] Feature flag documented  
- [ ] No unapproved publish path to students  
