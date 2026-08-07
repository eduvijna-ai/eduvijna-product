# EBP-001 — Tasks

**ID:** EBP-001-TASKS  
**Format:** Vertical-slice tasks · repos `Quiz-React` + `eduvijna-api`

---

## Legend

| Tag | Meaning |
|-----|---------|
| `[WEB]` | Quiz-React |
| `[API]` | eduvijna-api |
| `[TEST]` | Automated tests required in same slice |
| `[FLAG]` | Feature-flag work |

---

## Sprint 0

| ID | Task | Tags |
|----|------|------|
| T-001 | Add `FEATURE_TEACHER_OS_ENABLED` (+ child keys) and document `FEATURE_FLAGS_JSON` overrides | `[API]` `[FLAG]` |
| T-002 | Expose flags on `/health/meta` | `[API]` `[TEST]` |
| T-003 | Add `src/config/teacherOsFeature.ts` (env + optional meta fetch) | `[WEB]` `[FLAG]` |
| T-004 | Create `src/features/teacher-os/` module scaffold (routes, empty Shell layout) | `[WEB]` |
| T-005 | Gate Teacher OS nav entry in `MainLayout.tsx` | `[WEB]` `[FLAG]` |
| T-006 | Register `/teacher-os` under protected layout in `App.tsx` | `[WEB]` |
| T-007 | Unit tests for flag helpers; E2E flag off/on nav visibility | `[TEST]` |

---

## Sprint 1

| ID | Task | Tags |
|----|------|------|
| T-010 | Implement outcome-first Teacher OS nav items (8 destinations) | `[WEB]` |
| T-011 | Stub Prepare/Teach/Assess/Improve/Library/AI/Settings routes (safe placeholders deep-linking where ready) | `[WEB]` |
| T-012 | Build Today's Mission landing component (greeting, counts, AI prepared, Review CTA) | `[WEB]` |
| T-013 | When `today_dashboard_enabled`, route `/dashboard` & `/home` to Mission for teacher roles | `[WEB]` `[FLAG]` |
| T-014 | Mission data adapter: compose classes/assessments/PTM/pending from existing APIs; empty-safe | `[WEB]` `[API]` |
| T-015 | Optional lightweight `GET /api/v1/teacher-os/mission` aggregate if client composition insufficient | `[API]` |
| T-016 | Keep legacy HomePage when flags off | `[WEB]` `[FLAG]` |
| T-017 | UI + a11y tests for Mission; regression flag-off landing | `[TEST]` |

---

## Sprint 2

| ID | Task | Tags |
|----|------|------|
| T-020 | Ensure Platform AI `content/generate` results are queryable as needs-review for acting teacher | `[API]` |
| T-021 | Add/extend list API: pending review items (type, title, created_at, content_id, intent/thread id if any) | `[API]` `[TEST]` |
| T-022 | Add approve / reject (or wire existing content decision APIs) — **no student publish on generate** | `[API]` `[TEST]` |
| T-023 | Build Review Queue page `/teacher-os/review` (kit/type grouping, filters Today / Needs review) | `[WEB]` |
| T-024 | Wire Open → existing preview route; Approve/Reject actions | `[WEB]` |
| T-025 | Shell badge for pending review count | `[WEB]` |
| T-026 | Mission **Review →** deep-links to Queue with today filter | `[WEB]` |
| T-027 | Map generator types into queue labels (Worksheet, Quiz, Lesson Plan, …) | `[WEB]` `[API]` |
| T-028 | Integration + E2E: generate → queue → approve; regression generators | `[TEST]` |
| T-029 | Verify parent/student delivery paths still require approval gate | `[TEST]` |

---

## Sprint 3

| ID | Task | Tags |
|----|------|------|
| T-030 | Continuous Context provider (active class/subject/topic/artefact focus/thread id) | `[WEB]` `[FLAG]` |
| T-031 | Bind Context to Content AI sessions / platform session store | `[WEB]` `[API]` |
| T-032 | Follow-up refine UX (“make it harder”) updates focused queue item | `[WEB]` `[API]` `[TEST]` |
| T-033 | Today Dashboard sections: classes, pending reviews, recent activity, quick continue, AI recommendations | `[WEB]` |
| T-034 | Teacher Memory Summary card (read from profile/preferences available today) | `[WEB]` |
| T-035 | School Context Summary card (school/board/year from platform context) | `[WEB]` |
| T-036 | Progress indicators for any multi-step generate/orchestrate | `[WEB]` |
| T-037 | Performance smoke: Mission &lt; 2s on pilot data profile | `[TEST]` |
| T-038 | Unit tests for context reducer; E2E follow-up refine | `[TEST]` |

---

## Sprint 4

| ID | Task | Tags |
|----|------|------|
| T-040 | Legacy nav / Platform AI visibility rules during migration | `[WEB]` `[FLAG]` |
| T-041 | Error empty states + honest Mission copy when AI not fully prepared | `[WEB]` |
| T-042 | Rollback drill (disable flags) documented and verified | `[FLAG]` `[TEST]` |
| T-043 | Full regression pack (auth, generators, ERP smoke if impacted) | `[TEST]` |
| T-044 | Accessibility audit pass on Mission, Queue, nav | `[TEST]` |
| T-045 | Rollout checklist + metrics hooks (approval rate, Mission load time) | `[API]` `[WEB]` |
| T-046 | Update EBP-001 review package with implementation summary + test results | docs |

---

## Non-tasks (explicitly excluded)

- New generator engines / model providers  
- PPT/Sketch Notes **engines** if not already present — queue may show “coming soon” only if product agrees; prefer hide until capability exists  
- Student/Parent/Principal OS  
- Major schema redesign  

---

## Task completion rule

No task moves to Done without accompanying `[TEST]` evidence in the same PR (or a linked PR in a same-sprint pair that must merge together).
