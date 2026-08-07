# EBP-001 — Sprint Breakdown

**ID:** EBP-001-SPRINTS  
**Model:** Vertical slices — usable teacher value each sprint

---

## Sprint 0 — Foundation plumbing (still shippable)

**Teacher can:** Toggle Teacher OS Preview and see a gated empty shell route without breaking login.

| Layer | Deliverable |
|-------|-------------|
| Story | As a teacher with Preview entitlement, I can open Teacher OS shell when flagged |
| React | `teacherOsFeature` config; `/teacher-os` placeholder layout; flag-gated MainLayout entry |
| Backend | `teacher_os_enabled` (+ child flags) on `/health/meta` |
| Tests | Unit: flag parsing; E2E: flag off → no Teacher OS nav; flag on → shell visible |
| Deploy | Preview env only |

---

## Sprint 1 — Outcome navigation + Mission landing

**Teacher can:** Log in and see Today's Mission instead of the old module tile home (when flagged).

| Layer | Deliverable |
|-------|-------------|
| Story | As a teacher, I see Good Morning + Today's Mission + Review CTA |
| React | Outcome nav (Today/Prepare/Teach/Assess/Improve/Library/AI/Settings); Mission page; `/dashboard` swap when `today_dashboard_enabled` |
| Backend | Mission aggregate endpoint **or** composed client reads from existing timetable/content pending APIs with empty-safe fallbacks |
| Tests | UI: Mission renders; a11y: heading hierarchy; regression: flag off restores HomePage |
| Deploy | Preview |

**Exit demo:** Teacher login → Mission briefing → click Review → (queue stub OK if Sprint 2).

---

## Sprint 2 — Review Queue (mandatory spine)

**Teacher can:** See AI artefacts needing approval and approve/reject without student publish.

| Layer | Deliverable |
|-------|-------------|
| Story | As a teacher, every generate I trigger enters Review Queue; I approve before publish |
| React | `/teacher-os/review` list; open preview; approve/reject; badge count on shell |
| Backend | List pending-by-teacher; approve/reject wiring to content `ApprovalState`; ensure generate sets needs-review |
| Tests | Integration: generate → pending → approve; E2E: queue happy path; regression: legacy generate still works |
| Deploy | Preview → limited Pilot schools |

**Exit demo:** Generate worksheet via Platform AI → appears in Queue → Approve → Ready to Publish (assign may be stubbed with clear label).

---

## Sprint 3 — Continuous Context + Today Dashboard depth

**Teacher can:** Say “make it harder” in-session without re-stating Grade/topic; see Today Dashboard sections.

| Layer | Deliverable |
|-------|-------------|
| Story | As a teacher in an active prepare thread, follow-ups keep class/topic/artefact focus |
| React | Continuous Context provider/strip; Today Dashboard cards (classes, pending reviews, recent activity, quick continue, AI recommendations, Memory/School summaries) |
| Backend | Session/thread continuity via Content AI sessions (+ metadata if required); status update channel meeting &lt;500 ms budget where applicable |
| Tests | Unit: context reducer; integration: follow-up refine; UI: dashboard sections; a11y on interactive queue/context |
| Deploy | Pilot |

**Exit demo:** Prepare Grade 8 Science → worksheet → “make it harder” updates same artefact in Queue.

---

## Sprint 4 — Hardening, migration safety, GA readiness

**Teacher can:** Use Teacher OS shell daily with flags; legacy paths remain intact.

| Layer | Deliverable |
|-------|-------------|
| Story | As a pilot teacher, I complete a morning Mission → Review loop without regressions |
| React | Polish Mission/Queue/Dashboard; legacy nav visibility; progress indicators for orchestration |
| Backend | Performance pass on Mission/Queue list; fix edge cases; metrics hooks for approval rate |
| Tests | Full regression pack; performance smoke (&lt;2s Mission); rollback drill |
| Deploy | Expand Pilot; document GA checklist |

---

## Sprint dependency graph

```text
Sprint 0 (flags + shell)
    ↓
Sprint 1 (nav + Mission)
    ↓
Sprint 2 (Review Queue)  ← critical path
    ↓
Sprint 3 (Continuous Context + Dashboard depth)
    ↓
Sprint 4 (hardening)
```

No sprint may skip Review Queue forever — Wave 1 acceptance requires Sprint 2 complete.

---

## Capacity note

Exact calendar length is team-dependent. Do not start Sprint N+1 UI without Sprint N tests green on main/preview.
