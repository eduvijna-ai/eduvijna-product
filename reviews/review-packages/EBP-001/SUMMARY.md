---
id: EBP-001
title: Review Package — Teacher OS Foundation Engineering Blueprint
owner: EduVijna Product Office + Engineering
status: draft
version: 0.1.0
created: 2026-08-07
last_updated: 2026-08-07
review_type: Engineering Blueprint Review
foundation: PA-001 · TLM-001
---

# EBP-001 — Summary

## Subject

Engineering Blueprint for **Wave 1 — Teacher OS Shell**: production-ready vertical-slice delivery on existing `Quiz-React` (eduvijna-web) and `eduvijna-api`.

## Objective

Enable teachers to log in and use outcome-first Teacher OS structure immediately — Mission, Today Dashboard, Review Queue, Continuous Context — while reusing existing generators and protecting rollout with feature flags.

## Philosophy change

**Document-first → Vertical-slice first.**  
Each sprint: User Story → React → Backend → Tests → Review → Deploy (flagged).

## Scope

| In | Out |
|----|-----|
| Shell navigation | New AI models / generators |
| Today's Mission + Today Dashboard | Student / Parent / Principal OS |
| Review Queue with existing generators | Major DB redesign |
| Continuous Context (session) | Platform extraction |
| Feature flags + tests + rollback | New application repo |

## Implementation summary (planned)

| Area | Approach |
|------|----------|
| Nav | Additive Teacher OS section in `MainLayout`; flag-gated |
| Mission | Override `/dashboard` when `today_dashboard_enabled` |
| Review Queue | Content approval states + list/approve APIs; UI `/teacher-os/review` |
| Continuous Context | Content AI sessions + client thread provider |
| Generators | Reuse `/platform-ai/*` + `POST /api/v1/content/generate` |
| Flags | Extend API `feature_flags` + web config |

## Blueprint artefacts

All under `engineering/EBP-001/`:

README · IMPLEMENTATION_PLAN · SPRINT_BREAKDOWN · TASKS · DEPENDENCIES · RISKS · TEST_PLAN · ROLLBACK_PLAN · FEATURE_FLAGS

## Test results

**Pre-implementation.** No production code shipped under this blueprint yet.  
Test results section to be filled after Sprint slices with CI links.

## Open risks

See `engineering/EBP-001/RISKS.md` — especially R-02 (queue bypass), R-03 (mission aggregates), R-04 (context), R-09 (approval model fit).

## Rollout checklist

- [ ] Flags default false in prod  
- [ ] Preview env validates Sprint 0–1  
- [ ] Pilot schools entitled  
- [ ] Rollback drill passed (Sprint 4)  
- [ ] Principle tests P-01–P-04 green  
- [ ] Performance Mission &lt; 2s on pilot profile  
- [ ] Product sign-off on Mission + Queue UX  

## Deployment notes

1. Deploy **API flags** first (meta exposure).  
2. Deploy **web** Teacher OS module behind flags.  
3. Enable `teacher_os_enabled` only on Preview, then Pilot tenants.  
4. Enable child flags in order: dashboard → review_queue → continuous_context.  
5. Monitor approval bypass incidents = zero tolerance.  

## Changed files (this package)

See `CHANGED_FILES.md`.

## Recommended review outcomes

- **Approve** — Engineering may start Sprint 0 in `Quiz-React` + `eduvijna-api`  
- **Approve with conditions** — resolve open questions first  
- **Request changes** — adjust slice order or scope  

## Stop

**Implementation must not start until EBP-001 is approved.**  
This review package is the blueprint gate — not an implementation completion report.
