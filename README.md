# EduVijna Product

Product intelligence workspace for the EduVijna Product Office.

## Mission

Understand the real life of teachers, students, parents, and school leaders — then define where EduVijna creates extraordinary value.

This repository is **not** an implementation repository.

It captures product vision, personas, journeys, jobs-to-be-done, pain points, opportunities, capability gaps, and success metrics — before architecture and engineering begin.

## Teacher OS (central product model)

```text
Teacher OS
├── Today
├── Prepare
├── Teach
├── Assess
├── Improve
└── AI Assistant
```

Powered by:

| Abstraction | Role |
|-------------|------|
| **Teaching Intent** | Product ↔ orchestration API (one intent → many artefacts) |
| **Teacher Memory** | Persistent teacher profile that compounds |
| **School Context** | Auto-inherits school, calendar, timetable, curriculum, policy, branding, language, ERP |
| **Daily Loop** | Prepare → Teach → Observe → Assess → Analyze → Improve → Prepare Again |

## What this repository is

| In scope | Out of scope |
|----------|--------------|
| Product vision and principles | UI design |
| Personas and journeys | React / mobile / API code |
| Jobs-to-be-done | Backend / database design |
| Pain-point analysis | Implementation architecture |
| AI opportunity intelligence | Prompt engineering |
| Capability mapping (product backlog signal) | Infrastructure |
| Teacher OS / Intent / Memory / Context models | Feature implementation |
| Success metrics | |

## Repository structure

```text
eduvijna-product/
├── README.md
├── vision/
│   ├── PRODUCT_VISION.md
│   ├── PRODUCT_PRINCIPLES.md
│   ├── NORTH_STAR.md
│   ├── TEACHING_INTENT.md
│   ├── DAILY_LOOP.md
│   └── TEACHER_OS.md
├── memory/
│   └── teacher-memory.md
├── context/
│   └── school-context.md
├── personas/
├── journeys/teacher/
├── jobs-to-be-done/
├── pain-points/
├── opportunities/
├── capability-mapping/
├── metrics/
└── reviews/review-packages/TLM-001/
```

## Current focus

**TLM-001 — Teacher Journey Model** (amended with Intent, Memory, School Context, Daily Loop, Teacher OS)

## How to use this repository

1. Read `vision/` (including Teaching Intent, Daily Loop, Teacher OS).  
2. Read `memory/` and `context/` before proposing AI behaviour.  
3. Read `personas/teacher.md` and walk `journeys/teacher/`.  
4. Use JTBD / pains / opportunities as demand signals.  
5. Use `capability-mapping/` as backlog input — Intent layer first, not generator menus.  
6. Package work under `reviews/review-packages/` for Product Architecture Review.

## Stop condition for TLM-001

Product intelligence for the Teacher Journey Model is complete (including the four amendments).

**STOP. Await Product Architecture Review.**

## Ownership

EduVijna Product Office.

GitHub: [github.com/eduvijna/eduvijna-product](https://github.com/eduvijna/eduvijna-product)

## License

Copyright 2026 EduVijna

Licensed under the [Apache License, Version 2.0](LICENSE).

