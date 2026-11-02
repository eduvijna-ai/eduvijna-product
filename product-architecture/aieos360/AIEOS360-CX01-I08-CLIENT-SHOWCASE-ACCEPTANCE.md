---
id: AIEOS360-CX01-I08-P
title: AIEOS360 Founder Client Showcase — Product Acceptance Record
owner: EduVijna Product Office · Product Architecture
status: acceptance-pending
version: 1.0.0-draft
created: 2026-11-02
last_updated: 2026-11-02
programme: AIEOS360-CX01 — Client Showcase
architecture_workday: AIEOS360-CX01-I08
governing_contract: AIEOS360-CX01-W01 §1.3
---

# AIEOS360-CX01-I08-P — Founder Client Showcase Product Acceptance

**Declaration at drafting:** **FOUNDER SHOWCASE ACCEPTANCE PENDING.** This is a product-experience and acceptance record, not a record of a demonstration already performed. **AIEOS 360 CLIENT SHOWCASE READY = NOT YET DECLARED. PRODUCTION READY = NO.**

**Programme target:** **2026-11-20** (showcase development readiness, not a production launch). The separate AIEOS v1 development-readiness target remains **2026-12-18**.

**Authority and cross-references:** [W01 architecture acceptance baseline](https://github.com/eduvijna-ai/eduvijna-architecture/blob/491295c3cf0a151f31686a6a2e1a2176cd92c782/AIEOS/AIEOS360-CX01-W01-CLIENT-SHOWCASE-GAP-BASELINE.md) · [I08 Architecture Issue #50](https://github.com/eduvijna-ai/eduvijna-architecture/issues/50) · [I08 Product Issue #2](https://github.com/eduvijna-ai/eduvijna-product/issues/2) · [Architecture draft PR #51](https://github.com/eduvijna-ai/eduvijna-architecture/pull/51) (evidence dossier and conditional closeout). This Product record is **not** an ADR and does not replace Teacher OS PA-001.

## 1. Product outcome and boundaries

**Intended client takeaway:** One coherent, readable educational-workflow story across HUMAN Teacher, Student, Principal and Parent roles under the same synthetic Grade 5A school context, with truthful automated safeguards and deliberate human authority. Product acceptance requires the Founder to judge the actual client-facing flow; code and CI cannot make that judgment for the Founder.

**Canonical scenario:** `AIEOS360-CX-SCENARIO-01`, governed by ADR-AIEOS-052…062. Teacher prepares a six-artifact kit, reviews and approves before publishing; Teacher assigns an **exact published ContentVersion** to Grade 5A (`class-5a`); Student A starts, saves and submits; Teacher explicitly invokes current-policy evaluation, records a separate HUMAN ClassroomAssessment, deliberately creates Improve/remediation work; Principal sees **DERIVED_ON_REQUEST** school aggregates; Parent sees only authorized-child assignment lifecycle. Student B (Grade 5B) and wrong-tenant access must fail closed.

This is **not** a completion claim for Admin OS, production ERP/SIS, a full Student/Principal/Parent product, broad Educational Intelligence, generalized Agents/MCP, production deployments or learner mastery.

## 2. W01 §1.3 — six acceptance criteria

Outcome vocabulary: **ENGINEERING_PROVEN**, **PENDING_FOUNDER**, **FOUNDER_DEMONSTRATED**, **GAP**, **DEFERRED_NOT_REQUIRED**. These classifications are evidence-specific; do not mistake an engineering PASS for human acceptance.

| # | W01 client acceptance criterion | Current evidence class | Founder decision outstanding |
|---|---|---|---|
| 1 | Repeatable deterministic reset/reseed of a canonical shared, non-production school scenario | **ENGINEERING_PROVEN** — I01R9 lifecycle proof and I07 same-substrate integration | Witness safe operator preflight, repeatability and recovery; **PENDING_FOUNDER** |
| 2 | Teacher, Student, Principal and Parent entry points on one coherent school story | **ENGINEERING_PROVEN** — four-role I07 real-stack proof; unified launcher I02 | Confirm the actual role transitions and continuity in the room; **PENDING_FOUNDER** |
| 3 | Human walkthrough without engineering-only DEV session wiring **during** the client story | **PENDING_FOUNDER** — memory-only sessions must be pre-connected in separate tabs | Observe successful prepared role handoff; no token-pasting or secret screen during demonstration |
| 4 | Student, Principal and Parent client-demo quality relative to accepted Teacher showcase bar | **ENGINEERING_PROVEN** (functional/UX uplift I02–I05); **PENDING_FOUNDER** (client presentation) | Judge readability, navigation, responsiveness and narrative confidence |
| 5 | Explicit, safe distinction between DETERMINISTIC and REAL_AI mode | **ENGINEERING_PROVEN** (I06 mode governance); whole-vertical REAL_AI live generation **PENDING** | Approve mode selection and truthful disclosure, not an unverified provider claim |
| 6 | Integrated real-stack evidence retained, with no claim of production readiness | **ENGINEERING_PROVEN** — I07 10/10 and security negatives; post-merge CI and analysis PASS | Accept the evidence dossier and non-production scope |

**Binding rule:** An unconditional **AIEOS 360 CLIENT SHOWCASE READY** declaration is forbidden while a mandatory W01 condition remains unmet or unaccepted by the Founder.

## 3. Evidence provenance and what it does not prove

- **Same-run I07 engineering proof:** [Frontend merge PR #47](https://github.com/eduvijna-ai/eduvijna-aieos-frontend/pull/47), normal merge SHA `569ef8be46617ab1412ddb3f5a0214c40bdb946b`; [post-merge CI 41410487754](https://github.com/eduvijna-ai/eduvijna-aieos-frontend/actions/runs/41410487754) **9/9 jobs PASS**, I07 integrated **10/10 tests PASS**, mandatory Fake PreparationKit proof PASS on one shared disposable PostgreSQL 18 substrate, with zero mocked Product `/api` responses; [CodeQL 41410487287](https://github.com/eduvijna-ai/eduvijna-aieos-frontend/actions/runs/41410487287) three analysis jobs PASS.
- **Privacy/authority negatives in that proof:** Grade 5B Student B cannot read Grade 5A assignment; wrong-tenant requests fail; Principal response contains aggregate-only school insights, no learner score/mastery/leaderboard; Parent cannot view another child or evaluation existence.
- **Historic, separate from I07:** Teacher-only Groq Real-AI Founder acceptance on **2026-09-07** (TOS-CX01), S04-I03 cross-role data-plane proof, S01-I05 Teacher Improve proof. They do not establish a cross-role paid-provider generation rehearsal.
- **Not proven by automated tests:** Founder execution of local setup and the in-room walkthrough; Founder/client observations; production security/SSO/ERP operation; whole-AIEOS360 live provider generation.

Source contracts and human walkthrough: [I07 presenter preflight](https://github.com/eduvijna-ai/eduvijna-aieos-frontend/blob/569ef8be46617ab1412ddb3f5a0214c40bdb946b/docs/AIEOS360-CX01-I07-PRESENTER-PREFLIGHT.md), [cue sheet](https://github.com/eduvijna-ai/eduvijna-aieos-frontend/blob/569ef8be46617ab1412ddb3f5a0214c40bdb946b/docs/AIEOS360-CX01-I07-FOUNDER-CUE-SHEET.md), [I07 post-merge verification report](https://github.com/eduvijna-ai/eduvijna-aieos-frontend/pull/47#issuecomment-6572411930).

## 4. Founder demonstration acceptance checklist (NOT RUN)

**Before clients:** Confirm an owned NON_PRODUCTION disposable PostgreSQL18 substrate on Linux/WSL2; reset/start/status healthy; pre-connect Teacher, Student, Principal and Parent memory-only DEV sessions **before** audience; avoid displaying tenant IDs, bearer values or local fixtures; select mode and record it; safe stop/cleanup afterward. Do not imply SSO or real ERP identity.

**Allowed narrative modes:** **Mode A** creates fresh deterministic Fake kit, matching I07; **Mode B** uses an already seeded approved-but-unpublished *synthetic* worksheet and explains the prerequisites. Keep ContentVersion lineage consistent. **REAL_AI LIVE GENERATION = PENDING** for the whole-AIEOS360 story. Neither an I06 runtime toggle nor a Provider Aggregator `REAL` label proves a live generated artifact.

| Beat | Observable Founder/client experience | Outcome (Founder fills) | Note/evidence (Founder fills) |
|---|---|---|---|
| Preflight | Safe 8-process operator status; role tabs ready; mode displayed | **NOT RUN** | — |
| Teacher | Prepare or disclose Mode B seed; review/approve/publish controlled | **NOT RUN** | — |
| Teacher → Class | Published exact version assigned to Grade 5A | **NOT RUN** | — |
| Student | Assignment visible; Start → Save → Submit | **NOT RUN** | — |
| Assessment / Improve | Explicit evaluation; HUMAN class judgment `MIXED`; deliberate Improve | **NOT RUN** | — |
| Principal | Two-class aggregate story; read-only; no learner details | **NOT RUN** | — |
| Parent | Authorized-child lifecycle only; no evaluation existence | **NOT RUN** | — |
| Privacy | Student B/other child and wrong-tenant denial explained or safely shown | **NOT RUN** | — |
| Continuity | No in-audience DEV wiring; readable pages/handoffs/client device | **NOT RUN** | — |
| Safe exit | Scoped process stop, no unrelated resources touched | **NOT RUN** | — |

**Outcome values for Founder:** PASS / PARTIAL / FAIL / NOT RUN. **Do not backfill PASS from CI**, and do not record attendance, quotes or screenshots until actually supplied.

## 5. Limitations, product gaps and decision register

| ID | Product acceptance issue | Status / classification | Required decision |
|---|---|---|---|
| G-01 | Actual Founder-performed client walkthrough not yet recorded | **BLOCKER_FOR_SHOWCASE** | Founder executes and signs off (or explicitly accepts clearly scoped demonstration limits) |
| G-02 | Memory-only preconnected DEV role tabs, no single-click SSO | **ACCEPTED_LIMITATION** for non-production showcase | Founder acknowledges; no auth bypass |
| G-03 | Mode B seeded worksheet could be mistaken for live AI | **ACCEPTED_LIMITATION** only with explicit synthetic disclosure | Founder chooses Mode A or B |
| G-04 | Real-AI whole-vertical generation unverified | **PENDING** / deferred from this deterministic I08 acceptance evidence | Separate approved provider proof if ever required; no spend implied |
| G-05 | Production ERP/SIS, Admin OS, full EIS, Agents/MCP and other depth | **DEFERRED_ORIGINAL_SCOPE** under locked roadmap | Not a client-showcase production claim |
| G-06 | UX presentation may differ from engineering-functional checks | **PENDING_FOUNDER** | Founder records per-role quality and any blocker |

**Escalation:** A major UX or identity gap discovered at Founder rehearsal requires a separately authorized work package. This record does not authorize new Backend/Frontend functionality.

## 6. Founder acceptance / explicit authorization — PENDING

| Acceptance field | Current value (do not invent) |
|---|---|
| Founder name/signature | **PENDING / NOT PROVIDED** |
| Real rehearsal date/time | **NOT RECORDED** |
| Selected Mode A / B | **NOT CHOSEN BY FOUNDER** |
| W01 criterion-by-criterion acceptance | **PENDING** |
| Limitations explicitly accepted | **PENDING** |
| Observed blockers and dispositions | **PENDING** |
| Product declaration “AIEOS 360 CLIENT SHOWCASE READY” | **NOT AUTHORIZED** |
| Architecture CX01-C01 status upgrade | **NOT AUTHORIZED** |
| Product / Architecture PR merge authorizations | **NOT AUTHORIZED** |

A separate, exact-HEAD Founder decision must precede any merging, READY declaration, I08 issue closure or new Dec18-programme workday. A technical PR approval alone does not substitute for the Founder session.

## 7. Product repository delivery governance

**Approved Product base:** `b4b3048fb7a6a1c50ae8619dc490743714f2e3e2`. **Related Architecture draft PR:** [#51](https://github.com/eduvijna-ai/eduvijna-architecture/pull/51), exact initial HEAD `9fc40d020b88d69c5e236397c63409c470fefb4f`. This Product record is authored as a **Chief Architect administrative recovery** because Cursor's local Product commit `68619d0c2158b89b6d701404ce85cd002aa58dec` could not be pushed under Cursor's credentials; that local commit **has not been independently reviewed or claimed as this branch's source**. No other repository is changed by this Product draft.

**Scope:** Product Markdown records only; no direct main modification, Frozen ADR edits, code, new APIs, cloud action, provider calls or student data. [Architecture Issue #50](https://github.com/eduvijna-ai/eduvijna-architecture/issues/50) and [Product Issue #2](https://github.com/eduvijna-ai/eduvijna-product/issues/2) remain OPEN through Founder review. [AIEOS-GOV-CI01](https://github.com/eduvijna-ai/eduvijna-architecture/issues/49) governs any corrective code/CI iteration.

**Product status: ACCEPTANCE EVIDENCE DRAFT / FOUNDER SIGN-OFF PENDING.**
