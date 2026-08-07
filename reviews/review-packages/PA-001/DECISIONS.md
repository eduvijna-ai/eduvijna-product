---
id: PA-001-DECISIONS
title: PA-001 — Decisions Log (Product Architecture)
owner: EduVijna Product Office
status: draft
version: 0.1.0
---

# Decisions

Product architecture decisions proposed for review. Not ADRs for infrastructure.

| ID | Decision | Rationale | Status |
|----|----------|-----------|--------|
| D-001 | Top nav = Today, Prepare, Teach, Assess, Improve, Library, AI Assistant, Settings | Teacher-centric outcomes; Library for reuse; Settings for Memory control | Proposed |
| D-002 | Generators are not top-level nav | Intent-driven product; avoid tool zoo (TLM) | Proposed |
| D-003 | Teaching Intent is the product↔orchestration contract | One Conversation; capability reuse | Proposed |
| D-004 | AI flow = Teacher → Intent → Capability Orchestration → Review → Publish | Approval gate; Never Surprise | Proposed |
| D-005 | Observe under Teach; Analyze under Assess; actions in Improve | Keep nav lean; preserve loop handoffs | Proposed |
| D-006 | School Context auto-inherits on every Intent | School-Aware AI expanded | Proposed |
| D-007 | Teacher Memory is visible/editable; inferences confirmable | Trust; Continuous Improvement | Proposed |
| D-008 | Feature flags: Preview → Pilot → GA + legacy fallback | Safe migration; reuse capabilities | Proposed |
| D-009 | Roadmap Phases 1–5 as Foundation → Teaching Assistant → Student → School → Parent Intelligence | North Star sequencing | Proposed |
| D-010 | Admin Console owns ERP master data; Teacher OS consumes Context | Feature boundaries; no overlap | Proposed |
| D-011 | Markdown wireframes only in PA-001 | No Figma/React in this review | Proposed |
| D-012 | Existing worksheet/quiz/lesson/ingest/analytics/OpenQuiz reused as services | No duplicated functionality | Proposed |

## Supersedes / extends

Extends TLM-001 models into architecture. Does not invalidate TLM research; navigation expands with Library + Settings.
