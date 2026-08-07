---
id: TLM-001
title: Review Package — Teacher Journey Model
owner: EduVijna Product Office
status: draft
version: 0.2.0
created: 2026-08-07
last_updated: 2026-08-07
reviewers: []
review_type: Product Architecture Review
stop_condition: STOP — Await Product Architecture Review
---

# TLM-001 — Summary

## Subject

Complete Teacher Journey Model for EduVijna — product intelligence only — **amended** with four foundational product-model changes before build.

## Objective

Model the full life of a school teacher and define where EduVijna creates extraordinary value — then fix the product abstractions that must exist **before** feature build:

1. **Teaching Intent** (product ↔ orchestration API)  
2. **Teacher Memory**  
3. **School Context** (expanded School-Aware AI)  
4. **Daily Loop** + **Teacher OS** information architecture  

## Four amendments (v0.2)

| Change | Canonical doc | Why it blocks naive build |
|--------|---------------|---------------------------|
| Teaching Intent | `vision/TEACHING_INTENT.md` | Stops generator-menu product; one intent → lesson/worksheet/quiz/PPT/sketch notes/homework |
| Teacher Memory | `memory/teacher-memory.md` | Stops first-time-assistant behaviour |
| School Context | `context/school-context.md` | Auto-inherits school/calendar/timetable/curriculum/policy/branding/language/ERP |
| Daily Loop + Teacher OS | `vision/DAILY_LOOP.md`, `vision/TEACHER_OS.md` | Central cycle + Today/Prepare/Teach/Assess/Improve/AI Assistant |

## Scope

| In scope | Out of scope |
|----------|--------------|
| Personas, journeys, JTBD, pains, opportunities | UI design |
| Capability mapping with Intent/Memory/Context layers | React / APIs / backend / DB |
| Teacher OS IA (conceptual) | Implementation architecture |
| Principles & north star | Prompts / AI workflow code |

## Headline findings

1. Teachers lose ~20–28 hours/week to prep, evaluation, fragmentation, and communication.  
2. Value is a **Daily Loop**, not a tool catalogue.  
3. **Teaching Intent** is the API; generators are services.  
4. Without **Teacher Memory** + **School Context**, AI will not feel extraordinary.  
5. EduVijna already has strong assessment/worksheet/ingestion muscles — bind them under Intent.  
6. Teacher OS navigation: **Today · Prepare · Teach · Assess · Improve · AI Assistant**.

## Recommended review outcome paths

- **Approve** — Proceed to Product Architecture for Epic 0 (foundations) then Epic 1 (Prepare Tomorrow).  
- **Approve with conditions** — Resolve open questions on memory governance / context source-of-truth.  
- **Request changes** — Adjust Intent catalogue or OS IA before architecture.

## Stop condition

**STOP. Await Product Architecture Review.**

## Package contents

SUMMARY · PERSONAS · JOURNEY · JTBD · PAIN_POINTS · OPPORTUNITIES · CAPABILITY_MAP · PRODUCT_PRINCIPLES · NORTH_STAR · CHECKLIST · OPEN_QUESTIONS · plus amendment digests referenced in CAPABILITY_MAP / PRINCIPLES.
