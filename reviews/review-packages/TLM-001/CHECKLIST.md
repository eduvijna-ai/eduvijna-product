---
id: TLM-001-CHECKLIST
title: TLM-001 Review Checklist
owner: EduVijna Product Office
status: draft
version: 0.1.0
created: 2026-08-07
reviewers: []
---

# TLM-001 — Checklist

Product Architecture Review checklist for the Teacher Journey Model.

## A. Scope conformance

- [ ] Work is product intelligence only (no UI designed)
- [ ] No React / application code created
- [ ] No APIs / backend / database designed
- [ ] No architecture diagrams or ADRs created
- [ ] No prompts or AI workflow implementations created
- [ ] Perspective is teacher life — not feature marketing

## B. Repository structure

- [ ] `eduvijna-product/` repository exists with required tree
- [ ] `README.md` present
- [ ] `vision/` contains PRODUCT_VISION, PRODUCT_PRINCIPLES, NORTH_STAR
- [ ] `personas/` contains teacher, student, parent, principal
- [ ] `journeys/teacher/` contains daily, weekly, monthly, academic-year
- [ ] `jobs-to-be-done/teacher-jtbd.md` present
- [ ] `pain-points/teacher-pain-points.md` present
- [ ] `opportunities/ai-opportunities.md` present
- [ ] `capability-mapping/teacher-capabilities.md` present
- [ ] `metrics/success-metrics.md` present
- [ ] `reviews/review-packages/TLM-001/` complete

## C. Deliverable 1 — Teacher Persona

- [ ] Goals documented
- [ ] Daily responsibilities documented
- [ ] Biggest frustrations documented
- [ ] Current tools documented
- [ ] Technology comfort documented
- [ ] AI expectations documented
- [ ] Success definition documented

## D. Deliverable 2 — Complete Teacher Journey

- [ ] Before school (preparation, travel, planning, materials)
- [ ] During school (assembly, classes, assessments, doubts, homework, attendance, communication, unexpected events)
- [ ] After school (evaluation, reports, parent communication, planning tomorrow, PD)
- [ ] Weekly activities (tests, staff meetings, planning)
- [ ] Monthly activities (PTM, reports, exam preparation)
- [ ] Academic year (planning, teaching, exams, results, admissions, holiday work)

## E. Deliverable 3 — JTBD

- [ ] Jobs include Trigger
- [ ] Jobs include Desired outcome
- [ ] Jobs include Current process
- [ ] Jobs include Pain
- [ ] Jobs include AI opportunity
- [ ] “Prepare tomorrow’s lesson” style examples present

## F. Deliverable 4 — Pain points

- [ ] Current effort
- [ ] Frequency
- [ ] Impact
- [ ] Estimated time lost
- [ ] Automation opportunity
- [ ] Priority

## G. Deliverable 5 — AI Opportunity Matrix

- [ ] Teacher Problem column
- [ ] Current Workflow column
- [ ] AI Solution column
- [ ] Expected Time Saved column
- [ ] Student Impact column
- [ ] Implementation Complexity column

## H. Deliverable 6 — Capability mapping

- [ ] Teacher activities mapped
- [ ] Existing EduVijna capability called out
- [ ] Gaps labelled (None / Improve / Partial / Missing / New / Ops)
- [ ] Document usable as backlog signal

## I. Deliverable 7 — Product Principles

- [ ] Teacher First
- [ ] AI Assists, Teacher Decides
- [ ] One Intent, Many AI Services (Teaching Intent)
- [ ] Minimize Teacher Workload
- [ ] Explain Every AI Output
- [ ] Human Approval Before Student Delivery
- [ ] Save Time Daily
- [ ] Continuous Improvement
- [ ] Privacy by Design
- [ ] School-Aware AI (expanded School Context)
- [ ] Teacher Memory Compounds
- [ ] Daily Loop Is the Product

## I2. Four amendments before build

- [ ] Teaching Intent documented as product↔orchestration API
- [ ] Prepare Tomorrow → multi-artefact expansion documented
- [ ] Teacher Memory documented
- [ ] School Context inheritance list documented
- [ ] Daily Loop (6 stages) documented
- [ ] Teacher OS structure documented (Today/Prepare/Teach/Assess/Improve/AI Assistant)
- [ ] Capability map reorganized around Intent + Loop (not generators-only)

## J. Deliverable 8 — North Star

- [ ] Mission
- [ ] Vision
- [ ] Product Promise
- [ ] Primary Users
- [ ] Core Value Proposition
- [ ] Long-term Vision
- [ ] Success Metrics defined (prep time, assessment time, weekly hours saved, satisfaction, engagement, adoption, retention, school adoption)

## K. Package completeness

- [ ] SUMMARY.md
- [ ] PERSONAS.md
- [ ] JOURNEY.md
- [ ] JTBD.md
- [ ] PAIN_POINTS.md
- [ ] OPPORTUNITIES.md
- [ ] CAPABILITY_MAP.md
- [ ] PRODUCT_PRINCIPLES.md
- [ ] NORTH_STAR.md
- [ ] CHECKLIST.md
- [ ] OPEN_QUESTIONS.md

## L. Stop condition

- [ ] Package explicitly stops for Product Architecture Review
- [ ] No implementation work authorised by this package alone

## Review decision

- [ ] Approve
- [ ] Approve with conditions
- [ ] Request changes

**Reviewer signature / date:** __________________
