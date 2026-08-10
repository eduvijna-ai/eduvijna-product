# EBP-001 — Teacher OS Foundation Engineering Blueprint

**ID:** EBP-001  
**Status:** EBP-001.4 Review Queue Entry implemented — awaiting architecture review  
**Wave:** 1 — Teacher OS Shell  
**Philosophy:** Vertical-slice first (usable teacher value every sprint)  
**Product foundation:** PA-001 · TLM-001  
**Owner:** EduVijna Product Office + Engineering

**Implementation package:** see `IMPLEMENTATION_SUMMARY.md` (latest: EBP-001.4) and sibling review docs in this folder.

---

## Purpose

This is the **first engineering blueprint** that must produce **production-ready software**.

It instructs how to evolve existing EduVijna apps into the Teacher OS Shell — not how to write a new application.

## Engineering philosophy (mandatory)

Until now: document-first.  
Now: **vertical-slice first**.

```text
User Story
   ↓
React (Quiz-React / eduvijna-web)
   ↓
Backend (eduvijna-api)
   ↓
Tests (unit + integration + UI + a11y + regression)
   ↓
Review
   ↓
Deploy (behind feature flags)
```

A teacher must be able to **use something after every sprint**.

### Architecture decisions that bind every sprint

| Decision | Doc |
|----------|-----|
| A — Everything is an Artifact | `../../product-architecture/teacher-os/ARTIFACT_MODEL.md` |
| B — Intent stateless / Work stateful | `../../product-architecture/teacher-os/INTENT_AND_WORK.md` |

### Engineering constitution (mandatory before Sprint 0)

**EBP-000 Engineering Constitution v1.0** is **frozen**.

Start at [`../ENGINEERING_CONSTITUTION.md`](../ENGINEERING_CONSTITUTION.md) and [`../REVIEW_CHECKLIST.md`](../REVIEW_CHECKLIST.md).  
Implementation decisions: [`../edrs/`](../edrs/) (EDRs — not architecture ADRs).

Sprint 0 coding starts only after Product + Engineering acknowledge v1.0.

Forbidden for Wave 1:

```text
Frontend-only mega PR → then Backend → then Database → then Testing
```

## Target repositories (existing only)

| Product name | Implementation repo | Role |
|--------------|---------------------|------|
| **eduvijna-web** | `Quiz-React` (ui.eduvijna.com) | Teacher OS shell, Mission, Review Queue UI |
| **eduvijna-api** | `eduvijna-api` (eduapi.eduvijna.com) | Flags, review/approval APIs, continuous context/session |

**Do not create a new application.** Teacher OS is the next evolution of EduVijna.

## Wave 1 goal

Teachers can log in and experience the new product structure immediately:

- Outcome-first navigation  
- Today's Mission landing  
- Today Dashboard  
- Review Queue (mandatory)  
- Continuous Context within session  
- Teacher Memory + School Context **summaries** (read surfaces)  
- Existing generators reused and still operational behind flags  

## Blueprint contents

| Doc | Role |
|-----|------|
| [IMPLEMENTATION_PLAN.md](IMPLEMENTATION_PLAN.md) | How to build Wave 1 on existing code |
| [SPRINT_BREAKDOWN.md](SPRINT_BREAKDOWN.md) | Vertical slices per sprint |
| [TASKS.md](TASKS.md) | Concrete engineering tasks |
| [DEPENDENCIES.md](DEPENDENCIES.md) | Systems, APIs, PA artefacts |
| [RISKS.md](RISKS.md) | Risks and mitigations |
| [TEST_PLAN.md](TEST_PLAN.md) | Required automated validation |
| [ROLLBACK_PLAN.md](ROLLBACK_PLAN.md) | Safe disable / revert |
| [FEATURE_FLAGS.md](FEATURE_FLAGS.md) | Flag catalogue and rollout |

Review package: `../../reviews/review-packages/EBP-001/`

## Out of scope (Wave 1)

- New AI models or new generators  
- Student OS / Parent OS / Principal OS  
- Major database redesign  
- Platform extraction  
- Full Prepare Tomorrow multi-artefact orchestration depth (shell + queue + context first; deepen in later EBPs)

## Acceptance criteria (Wave 1 complete when)

1. Teachers can access the new Teacher OS shell  
2. Navigation follows approved PA-001 architecture  
3. Today's Mission is functional  
4. Review Queue works with existing generators  
5. Continuous Context works within a session  
6. Existing generators remain operational  
7. No regression in current workflows  
8. Feature flags enable safe rollout  

## Stop condition for this blueprint package

Blueprint + review package authored.  
`ENGINEERING_STANDARDS.md` authored (constitution).  

**Implementation starts only after Engineering / Product Architecture Review of EBP-001 and acceptance of Engineering Standards.**
