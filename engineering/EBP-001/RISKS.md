# EBP-001 — Risks

**ID:** EBP-001-RISKS

---

## Risk register

| ID | Risk | Impact | Likelihood | Mitigation |
|----|------|--------|------------|------------|
| R-01 | Dual nav confusion (legacy + Teacher OS) | High teacher friction | High | Clear flag cohorts; Mission-first when on; legacy labeled; migration doc |
| R-02 | Review Queue bypass (generate still shares to students) | Critical — violates principle | Medium | Explicit tests; code review gate; disable share until approved |
| R-03 | Mission depends on incomplete ERP timetable | Empty/wrong counts | High | Soft dependency; honest empty states; don't block Queue |
| R-04 | Continuous Context incomplete → “which class?” regressions | Breaks signature promise | Medium | Bind to Content AI sessions; E2E refine test required |
| R-05 | Performance Mission &gt; 2s | Adoption failure | Medium | Aggregate caching; parallel fetches; skeleton UI |
| R-06 | Flag drift (web env ≠ API meta) | Split-brain UX | Medium | Prefer API `/health/meta` as source of truth where possible |
| R-07 | Scope creep into new generators | Delay Wave 1 | High | Out-of-scope enforcement in PR checklist |
| R-08 | Large PRs reverting to layer-first | Unusable sprints | Medium | Sprint DoD requires vertical slice demo |
| R-09 | ApprovalState model mismatch with queue UX | Rework | Medium | Spike in Sprint 0/2; extend domain carefully, no redesign |
| R-10 | Accessibility debt on new shell | Compliance / usability | Medium | a11y checks in TEST_PLAN mandatory |
| R-11 | Rollback leaves orphan pending items | Support load | Low | Rollback plan: flags off; data retained; classic UI can still open content |
| R-12 | Pilot teachers treat Queue as optional | Principle failure | Medium | Mission CTA + badge; training; product messaging |

---

## Open risks for review package

At blueprint time (pre-implementation):

- R-02, R-03, R-04, R-09 require validation spikes early in Sprint 0–2.  
- Residual risk accepted only with documented mitigations and tests.

---

## Escalation

Any risk that threatens **AI Assists, Teacher Decides** (especially R-02) blocks release to Pilot until mitigated.
