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

**PA-001 — Teacher OS Product Architecture** (built on approved TLM-001)

See `product-architecture/` and `reviews/review-packages/PA-001/`.

**TLM-001 — Teacher Journey Model** remains the research foundation under `personas/`, `journeys/`, `vision/`, etc.

## How to use this repository

1. Read `vision/` and TLM artefacts for *why*.  
2. Read `product-architecture/` for *what the Teacher OS is*.  
3. Use `capability-mapping/` and `product-architecture/teacher-os/CAPABILITY_ORCHESTRATION.md` as backlog input.  
4. Review packages: `TLM-001` (research), `PA-001` (architecture).  

## Stop condition

**PA-001 complete. STOP. Await Product Architecture Review decision before engineering.**

## Ownership

EduVijna Product Office.

GitHub: [github.com/eduvijna/eduvijna-product](https://github.com/eduvijna/eduvijna-product)

## License

Copyright 2026 EduVijna

Licensed under the [Apache License, Version 2.0](LICENSE).

