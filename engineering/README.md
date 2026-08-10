# Engineering

**EBP-000 — Engineering Constitution v1.0** (frozen)

Do not create or rename application repositories. Implementation remains in **Quiz-React (eduvijna-web)** and **eduvijna-api**. Documentation hierarchy remains in **eduvijna-product** as approved.

---

## Constitutional freeze

**No engineering task may contradict these standards.**

If implementation requires a change: update **Product Architecture** first → obtain approval → then update this constitution if needed. Not the other way around.

---

## Read first

| Document | Role |
|----------|------|
| [ENGINEERING_CONSTITUTION.md](ENGINEERING_CONSTITUTION.md) | **Root v1.0** — principles + freeze |
| [ENGINEERING_STANDARDS.md](ENGINEERING_STANDARDS.md) | Index + cross-cutting summary |
| [CODING_STANDARDS.md](CODING_STANDARDS.md) | Folders, naming, structure |
| [API_STANDARDS.md](API_STANDARDS.md) | Versioning, errors, pagination, idempotency, authZ, audit |
| [UI_STANDARDS.md](UI_STANDARDS.md) | Layout, states, AI progress, responsive guidance |
| [TESTING_STANDARDS.md](TESTING_STANDARDS.md) | Unit / integration / E2E / a11y / regression |
| [ACCESSIBILITY_STANDARDS.md](ACCESSIBILITY_STANDARDS.md) | Accessibility requirements |
| [FEATURE_FLAG_STANDARDS.md](FEATURE_FLAG_STANDARDS.md) | Owner, purpose, default, rollout, removal |
| [OBSERVABILITY_STANDARDS.md](OBSERVABILITY_STANDARDS.md) | Logging + telemetry |
| [SECURITY_STANDARDS.md](SECURITY_STANDARDS.md) | AuthZ, PII, publish gate |
| [RELEASE_STANDARDS.md](RELEASE_STANDARDS.md) | Deploy order, verify, rollback |
| [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) | Mandatory eng review questions |
| [edrs/](edrs/) | **EDRs** — implementation decisions (not architecture) |

---

## EDRs vs ADRs

| | EDR | ADR / PA change |
|--|-----|-----------------|
| Changes architecture? | **No** | **Yes** |
| Example | React Context for session Continuous Context ([EDR-001](edrs/EDR-001-continuous-context-react-context.md)) | Changing Artifact lifecycle or Intent semantics |

---

## Binding product decisions

| Decision | Doc |
|----------|-----|
| Everything is an Artifact | `../product-architecture/teacher-os/ARTIFACT_MODEL.md` |
| Intent stateless / Work stateful | `../product-architecture/teacher-os/INTENT_AND_WORK.md` |

---

## Blueprints

| ID | Title | Status |
|----|-------|--------|
| EBP-000 | Engineering Constitution v1.0 | **Frozen** |
| EBP-001 | Teacher OS Foundation (Wave 1 Shell) | Draft — Sprint 0 blocked on acknowledgement |

---

## Wave 2 note

Notification Center — `../product-architecture/teacher-os/NOTIFICATION_CENTER.md` — out of scope for EBP-001.
