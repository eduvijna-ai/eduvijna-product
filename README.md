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
├── memory/
├── context/
├── personas/
├── journeys/teacher/
├── jobs-to-be-done/
├── pain-points/
├── opportunities/
├── capability-mapping/
├── metrics/
├── product-architecture/          ← PA-001 Teacher OS
│   ├── teacher-os/
│   └── wireframes/
└── reviews/review-packages/
    ├── TLM-001/
    └── PA-001/
```

## Current focus

**EBP-001 — Teacher OS Foundation Engineering Blueprint** (Wave 1 Shell)

See `engineering/EBP-001/` and `reviews/review-packages/EBP-001/`.

Implementation targets existing apps: **Quiz-React (eduvijna-web)** + **eduvijna-api** — vertical-slice first, behind feature flags.

**PA-001** remains the product architecture foundation under `product-architecture/`.  
**TLM-001** remains the research foundation.

## How to use this repository

1. Read `vision/` and TLM artefacts for *why*.  
2. Read `product-architecture/` for *what the Teacher OS is* (incl. Artifact + Intent/Work decisions).  
3. Read `engineering/ENGINEERING_STANDARDS.md` before any coding.  
4. Read `engineering/EBP-*` for *how to build the next vertical slices*.  
5. Review packages: `TLM-001` · `PA-001` · `EBP-001`.  

## Stop condition

**EBP-001 + Engineering Standards ready. STOP. Await review before Sprint 0 coding in application repos.**

## Contribution

Follow [`CONTRIBUTING.md`](CONTRIBUTING.md). Same core rules as [eduvijna-architecture](https://github.com/eduvijna/eduvijna-architecture):

- No implementation code  
- Pull requests required to `main`  
- Product Architecture Review for material architecture changes  
- Stable artefact IDs  
- Markdown quality and cross-references  

Ownership: see [`CODEOWNERS`](CODEOWNERS).

## Ownership

EduVijna Product Office.

GitHub: [github.com/eduvijna/eduvijna-product](https://github.com/eduvijna/eduvijna-product)

## License

Copyright 2026 EduVijna

Licensed under the [Apache License, Version 2.0](LICENSE).

