# Engineering

Engineering blueprints and standards for vertical-slice delivery of Teacher OS on existing EduVijna applications.

## Constitution (read first)

| Doc | Role |
|-----|------|
| [ENGINEERING_STANDARDS.md](ENGINEERING_STANDARDS.md) | **Mandatory** before Sprint 0 — folders, naming, flags, tests, a11y, telemetry, review checklist |

## Binding product decisions

| Decision | Doc |
|----------|-----|
| Everything is an Artifact | `../product-architecture/teacher-os/ARTIFACT_MODEL.md` |
| Intent stateless / Work stateful | `../product-architecture/teacher-os/INTENT_AND_WORK.md` |

## Blueprints

| ID | Title | Status |
|----|-------|--------|
| EBP-001 | Teacher OS Foundation (Wave 1 Shell) | Draft — awaiting review |

Application code lives in **Quiz-React (eduvijna-web)** and **eduvijna-api** — not in this repository.

## Wave 2 note

Notification Center (workflow notifications) is planned for Wave 2 — see `../product-architecture/teacher-os/NOTIFICATION_CENTER.md`. Out of scope for EBP-001.
