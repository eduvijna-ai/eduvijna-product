# Product Architecture

**ID:** PA-001  
**Status:** Draft — Product Architecture Review  
**Owner:** EduVijna Product Office · Principal Product Architect  
**Foundation:** TLM-001 (approved product intelligence)

---

## Purpose

Transform the approved Teacher Journey Model into the complete **Teacher OS Product Architecture**.

This folder defines *what the product is* — information architecture, intents, loops, memory, context, orchestration, boundaries, experience principles, rollout, metrics, and roadmap.

It does **not** implement software.

## Constraints (hard)

| Do | Do not |
|----|--------|
| Design product behaviour | Write React / frontend |
| Define screens conceptually | Design APIs |
| Map capabilities & intents | Design databases |
| Define review/publish gates | Write prompts |
| Plan rollout & metrics | Implement AI workflows |
| Markdown wireframes | Architecture diagrams / backend |

## Structure

```text
product-architecture/
├── README.md
├── VISION.md
├── teacher-os/
│   ├── INFORMATION_ARCHITECTURE.md
│   ├── NAVIGATION_MODEL.md
│   ├── SCREEN_HIERARCHY.md
│   ├── TEACHING_INTENT_MODEL.md
│   ├── DAILY_LEARNING_LOOP.md
│   ├── TEACHER_MEMORY.md
│   ├── SCHOOL_CONTEXT.md
│   ├── AI_ORCHESTRATION.md
│   ├── CONTENT_LIFECYCLE.md
│   ├── CAPABILITY_ORCHESTRATION.md
│   ├── FEATURE_BOUNDARIES.md
│   ├── FEATURE_FLAGS.md
│   ├── EXPERIENCE_PRINCIPLES.md
│   ├── SUCCESS_METRICS.md
│   └── ROADMAP.md
└── wireframes/
    ├── HOME.md
    ├── TODAY.md
    ├── PREPARE.md
    ├── TEACH.md
    ├── ASSESS.md
    ├── IMPROVE.md
    └── AI_ASSISTANT.md
```

Review package: `../reviews/review-packages/PA-001/`

## Approved inputs only

- TLM-001 Teacher Journey  
- JTBD · Pain Points · Capability Mapping  
- Product Principles · North Star  
- Teaching Intent · Teacher Memory · School Context · Daily Learning Loop refinements  

## Reading order

1. `VISION.md`  
2. `teacher-os/INFORMATION_ARCHITECTURE.md` + `NAVIGATION_MODEL.md`  
3. `TEACHING_INTENT_MODEL.md` + `DAILY_LEARNING_LOOP.md`  
4. `TEACHER_MEMORY.md` + `SCHOOL_CONTEXT.md`  
5. `AI_ORCHESTRATION.md` + `CAPABILITY_ORCHESTRATION.md` + `CONTENT_LIFECYCLE.md`  
6. Boundaries, flags, experience, metrics, roadmap  
7. `wireframes/`  
8. `reviews/review-packages/PA-001/`  

## Stop condition

**STOP after PA-001 review package. Await Product Architecture Review decision before engineering.**
