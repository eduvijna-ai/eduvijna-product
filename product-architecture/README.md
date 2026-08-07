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
│   ├── CONTINUOUS_CONTEXT.md
│   ├── TODAYS_MISSION.md
│   ├── REVIEW_QUEUE.md
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
    ├── REVIEW_QUEUE.md
    └── AI_ASSISTANT.md
```

Review package: `../reviews/review-packages/PA-001/`

## Signature experiences (PA-001 amendments)

1. **Today's Mission** — login briefing (not nav-first)  
2. **Continuous Context** — session thread across related actions  
3. **Review Queue** — one place to approve all AI outputs  

## Approved inputs only

- TLM-001 Teacher Journey  
- JTBD · Pain Points · Capability Mapping  
- Product Principles · North Star  
- Teaching Intent · Teacher Memory · School Context · Daily Learning Loop refinements  
- PA-001 amendments: Today's Mission · Continuous Context · Review Queue  

## Reading order

1. `VISION.md`  
2. `teacher-os/TODAYS_MISSION.md` · `CONTINUOUS_CONTEXT.md` · `REVIEW_QUEUE.md`  
3. `INFORMATION_ARCHITECTURE.md` + `NAVIGATION_MODEL.md`  
4. Intent / Loop / Memory / School Context  
5. Orchestration + lifecycle  
6. Boundaries, flags, experience, metrics, roadmap  
7. `wireframes/` (especially HOME + REVIEW_QUEUE)  
8. `reviews/review-packages/PA-001/`  

## Stop condition

**STOP after PA-001 review package. Await Product Architecture Review decision before engineering.**
