# Engineering Review Checklist

**ID:** ENG-REVIEW-001  
**Parent:** ENGINEERING_CONSTITUTION.md  
**Use:** Every engineering PR / review for Teacher OS (and related) work

---

## Every engineering review must answer

| # | Question | Pass? |
|---|----------|-------|
| 1 | **Architecture preserved?** Implementation does not alter approved PA-001 / Artifact / Intent-Work / Mission / Queue models | ☐ |
| 2 | **Product behavior preserved?** Teacher outcomes match approved journeys/principles (AI Assists, Teacher Decides) | ☐ |
| 3 | **Existing capabilities reused?** Generators/platform content orchestrated — not forked/rewritten without approval | ☐ |
| 4 | **Artifact lifecycle unchanged?** ADR-046: Draft → Generating → Generated → In Review → Approved → Published → Archived (no type exceptions) | ☐ |
| 5 | **Intent vs Work preserved?** Intent not used as durable store; Work/Artifacts persist correctly | ☐ |
| 6 | **Tests passed?** Unit + integration/E2E as required; principle tests if touching generate/publish | ☐ |
| 7 | **Accessibility checked?** New UI keyboard/semantics/contrast addressed | ☐ |
| 8 | **Telemetry added?** Required events/logs for the feature present and PII-safe | ☐ |
| 9 | **Documentation updated?** EBP tasks/flags/standards notes or review package evidence updated when needed | ☐ |
| 10 | **Constitution honored?** Change does not contradict Engineering Constitution v1.0 | ☐ |
| 11 | **EDR vs ADR?** Implementation-only decisions recorded as EDR if needed; architecture changes not smuggled via EDR | ☐ |

**Additional gates**

| # | Question | Pass? |
|---|----------|-------|
| 12 | Feature flag gated with owner/purpose/default/rollout/removal noted? | ☐ |
| 13 | Backward compatible / flag-off safe? | ☐ |
| 14 | Security/tenant isolation preserved? | ☐ |

---

## Reviewer decision

- [ ] Approve  
- [ ] Approve with conditions  
- [ ] Request changes  

**Reviewer / date:** __________________

---

## Related

- `ENGINEERING_CONSTITUTION.md`  
- `TESTING_STANDARDS.md` · `FEATURE_FLAG_STANDARDS.md` · `OBSERVABILITY_STANDARDS.md`  
