# Engineering Standards

**ID:** ENG-STD-001  
**Parent:** [ENGINEERING_CONSTITUTION.md](ENGINEERING_CONSTITUTION.md) (EBP-000)  
**Status:** Mandatory  
**Applies to:** `Quiz-React` (eduvijna-web) · `eduvijna-api`

Cross-cutting engineering rules. Detailed topics live in specialized standards — this file is the **index and summary**.

---

## Specialized standards (source of truth by topic)

| Topic | Document |
|-------|----------|
| Constitution / principles | `ENGINEERING_CONSTITUTION.md` |
| Folders, naming, code shape | `CODING_STANDARDS.md` |
| HTTP APIs | `API_STANDARDS.md` |
| UI / UX engineering guidance | `UI_STANDARDS.md` |
| Tests | `TESTING_STANDARDS.md` |
| Accessibility | `ACCESSIBILITY_STANDARDS.md` |
| Feature flags | `FEATURE_FLAG_STANDARDS.md` |
| Logs & telemetry | `OBSERVABILITY_STANDARDS.md` |
| Security | `SECURITY_STANDARDS.md` |
| Release & rollback | `RELEASE_STANDARDS.md` |
| PR / eng review questions | `REVIEW_CHECKLIST.md` |
| Implementation decisions (not architecture) | `edrs/` |

**Constitution version:** **v1.0 frozen** — see `ENGINEERING_CONSTITUTION.md`.

---

## Cross-cutting rules (summary)

1. **Preserve architecture** — implement PA-001; do not redefine it in code.  
2. **Vertical slices** — teacher-visible outcome each sprint/PR pair.  
3. **Reuse generators** — orchestrate Platform AI / existing services; do not fork.  
4. **Artifacts** — all AI outputs follow Artifact lifecycle; Review Queue is generic.  
5. **Intent vs Work** — Intent completes; Work/Artifacts persist.  
6. **Flags** — Teacher OS behaviour gated; defaults false in prod until rollout.  
7. **Tests + a11y + telemetry** — required for user-visible slices.  
8. **Backward compatible** — flag-off restores classic EduVijna teacher flows.  
9. **EDRs for implementation** — architecture changes require ADR/PA first, never EDR alone.  
10. **No task contradicts Constitution v1.0.**

---

## Vocabulary (use consistently)

| Term | Meaning |
|------|---------|
| Artifact | Unit of generate/review/publish (type is an attribute) |
| Work | Stateful container of Artifacts over time |
| Intent | Stateless teaching request that completes |
| Review Queue | Type-agnostic approval surface |
| Continuous Context | In-session thread (not durable Memory) |

Do not invent synonyms (`item`, `doc`, `job`) for these concepts in Teacher OS code.

---

## Repositories (do not create or rename)

| Product name | Implementation |
|--------------|----------------|
| eduvijna-web | `Quiz-React` |
| eduvijna-api | `eduvijna-api` |

Documentation hierarchy remains in **eduvijna-product** (and EAO in **eduvijna-architecture**) as approved.

---

## Related blueprints

- `EBP-001/` — Teacher OS Foundation Wave 1 Shell  
