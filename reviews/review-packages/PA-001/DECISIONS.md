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
| D-013 | Login lands on Today's Mission briefing; nav is secondary | Teachers need day load + Review CTA, not a menu | Proposed |
| D-014 | Continuous Context = session/Intent thread; distinct from Teacher Memory & School Context | “Make worksheet harder” must not forget Grade/topic | Proposed |
| D-015 | Review Queue is signature approval surface; all AI outputs enter it before publish | Replace one-by-one downloads; Mission Review → opens queue | Proposed |
| D-016 | **Everything is an Artifact** — unified lifecycle; Review Queue is type-agnostic | Future capabilities add types, not new queues | **Accepted** |
| D-016a | **ADR-046** Artifact Status Lifecycle: Draft → Generating → Generated → In Review → Approved → Published → Archived — **no exceptions** | One machine for Worksheet/Quiz/Lesson/PPT/Homework/Rubric/Question Bank/… | **Accepted** |
| D-017 | **Intent is stateless; Work is stateful** — Intent completes; Work persists (continue/edit/share/duplicate/archive) | Durable teaching projects without reifying intents | **Accepted** |
| D-018 | Notification Center in Wave 2 (workflow notifications, not chat) | Complements Today/Mission; avoid Wave 1 scope creep | **Accepted (planned)** |
| D-019 | **ADR-042** Teacher OS Shell owns UX — not worksheet/quiz/report/analytics business logic | Preserve existing modules; shell = experience + entry points | **Accepted** |
| D-020 | **ADR-043** Foundation → Hardening → Review → Next Capability (never Feature×N → Refactor) | Stable Teacher OS before capability stacking | **Accepted** |
| D-021 | **ADR-047** Flagship teacher language: “Help me prepare tomorrow” — teacher does not assemble tools | Differentiation; outcome-first IA | **Accepted** |
| D-022 | **ADR-045** Teaching Intent owns goals; generators are capabilities behind Intent (**constitutional**) | Prevent tool zoo; Intent → orchestration → engines | **Accepted** |
| D-023 | **ADR-044** Teacher OS uses stable product services only; AI orchestrator/agents/MCP/LLMs stay backend-internal | Provider swap & multi-agent evolution without UI rewrite | **Accepted** |
| D-024 | **ADR-048** Review Queue owns approval — teacher judgement only (Review / Approve / Reject / Regenerate / Explain / Open editor); not generation, editing-as-product, or orchestration | Review is the primary experience; clean ownership vs Intent & orchestration | **Accepted** |

## Supersedes / extends

Extends TLM-001 models into architecture. v0.2 adds Mission, Continuous Context, and Review Queue.  
v0.3 locks Artifact + Intent/Work decisions and schedules Notification Center for Wave 2.  
Engineering constitution: `engineering/ENGINEERING_STANDARDS.md` (required before EBP-001 Sprint 0).
