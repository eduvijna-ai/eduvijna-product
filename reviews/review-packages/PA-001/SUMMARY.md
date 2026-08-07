---
id: PA-001
title: Review Package — Teacher OS Product Architecture
owner: EduVijna Product Office
status: draft
version: 0.1.0
created: 2026-08-07
last_updated: 2026-08-07
reviewers: []
review_type: Product Architecture Review
foundation: TLM-001
stop_condition: STOP — Await Product Architecture Review decision
---

# PA-001 — Summary

## Subject

Complete Teacher OS Product Architecture derived from approved TLM-001 artefacts.

## Objective

Define Teacher OS as an intent-driven, loop-centred product — navigation, screens, Teaching Intent, Daily Learning Loop, Teacher Memory, School Context, orchestration, boundaries, flags, experience principles, metrics, roadmap, and markdown wireframes — **without** implementation.

## Scope

| In scope | Out of scope |
|----------|--------------|
| Product architecture under `product-architecture/` | React / frontend code |
| Markdown wireframes | APIs / databases |
| Capability reuse mapping | Prompts / AI workflow implementation |
| Feature boundaries across OS surfaces | Backend / infra architecture diagrams |

## Acceptance criteria status (author self-check)

| Criterion | Met |
|-----------|-----|
| Navigation is teacher-centric | Yes — Today…Settings outcomes |
| Product is intent-driven | Yes — Teaching Intent model |
| Existing capabilities reused | Yes — capability orchestration maps |
| No duplicated functionality | Yes — IA anti-patterns + boundaries |
| Teacher Memory defined | Yes |
| School Context defined | Yes |
| Daily Learning Loop complete | Yes + gap list |
| Capability orchestration documented | Yes |
| Wireframes exist | Yes — Home/Today/Prepare/Teach/Assess/Improve/AI |
| Review package complete | Yes |

## Headline architecture decisions

1. Top nav = **Today · Prepare · Teach · Assess · Improve · Library · AI Assistant · Settings** (Library + Settings added vs TLM shell for reuse and control).  
2. Generators are **services under Intent**, never peer top-level nav.  
3. Canonical AI flow: Teacher → Intent → Capability Orchestration → Review → Publish.  
4. Observe lives inside Teach screens; Analyze lives inside Assess; both hand off to Improve.  
5. Rollout via Preview → Pilot → GA with legacy fallback.

## Recommended outcomes

- **Approve** — proceed to engineering blueprints under EAO/Product process  
- **Approve with conditions** — resolve OPEN_QUESTIONS  
- **Request changes** — adjust nav or intent catalogue  

## Stop

**STOP. Await Product Architecture Review decision. No coding authorised by this package alone.**
