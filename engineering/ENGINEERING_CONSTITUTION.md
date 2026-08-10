# Engineering Constitution

**ID:** EBP-000  
**Document:** ENGINEERING_CONSTITUTION.md  
**Version:** **1.0**  
**Status:** **Frozen — Engineering Constitution v1.0**  
**Applies to:** Implementation in existing repos (`Quiz-React` / eduvijna-web, `eduvijna-api`)  
**Does not:** Create or rename repositories; modify approved product/architecture docs without Product Architecture Review

---

## Constitutional freeze (v1.0)

This suite (**EBP-000**) is declared:

# Engineering Constitution v1.0

From this point:

1. **No engineering task may contradict these standards.**  
2. If implementation requires a change:  
   - **Update Product Architecture first**  
   - **Obtain architecture approval**  
   - **Then** update this Engineering Constitution (and related standards) if necessary  
3. **Not the other way around** — code and EDRs must not drive silent architecture drift.

Version bumps after 1.0 require Product + Engineering lead acknowledgement and a recorded reason.

---

## Purpose

This is the **root engineering document** for EduVijna Teacher OS delivery.

All other engineering standards inherit from these principles.  
Specialized rules live in sibling documents under `engineering/`.

---

## Principles

### 1. Preserve Architecture

Implementation **cannot** modify approved architecture.

- PA-001 Teacher OS, Artifact Model, Intent/Work, Review Queue, Mission, Continuous Context are binding.  
- Code adapts *to* architecture; architecture does not bend to convenience PRs.  
- Conflicts → open Product Architecture / Engineering review — do not silently diverge.

### 2. Vertical Slice Delivery

Every engineering task delivers an **end-to-end teacher outcome**.

```text
User Story → React → Backend → Tests → Review → Deploy (flagged)
```

Layer-only mega-PRs (frontend then backend then tests) are non-compliant.

Across capabilities, sequencing follows **ADR-043**:

```text
Foundation → Hardening → Review → Next Capability
```

Never: Feature → Feature → Feature → Refactor.

### 3. Backward Compatibility

**Never break existing schools.**

- Classic landing, generators, ERP, and auth remain operational when Teacher OS flags are off.  
- Additive changes preferred; migrations must be reversible or dual-read.  
- Pilot/GA cannot remove legacy paths until migration criteria in Feature Flag Standards are met.

### 4. Feature Flags

**Everything ships behind flags.**

- Defaults false in production until entitled rollout.  
- Flag ownership, purpose, default, rollout, and removal criteria are mandatory (see `FEATURE_FLAG_STANDARDS.md`).

### 5. AI Review

**All AI-generated Artifacts require explicit teacher approval before publishing.**

Aligns with:

- Review Queue (generic, type-agnostic)  
- Artifact lifecycle (**ADR-046**): Draft → Generating → Generated → In Review → Approved → Published → Archived  
  (**No exceptions** for any Artifact type.)

No generate-and-share bypass. No silent parent/student delivery.

### 6. Testing First

**No merge without automated validation** appropriate to the slice (unit, integration, E2E where needed, a11y, regression).

See `TESTING_STANDARDS.md`.

### 7. Observability

**Every new feature emits telemetry** (and structured logs without PII).

See `OBSERVABILITY_STANDARDS.md`.

### 8. Accessibility

**Teacher OS must meet accessibility expectations** — keyboard, semantics, contrast, focus, labels.

See `ACCESSIBILITY_STANDARDS.md`.

### 9. Implementation decisions via EDRs

Implementation choices that **do not** change architecture are recorded as **Engineering Decision Records** under `edrs/`.

If a choice would change architecture → **ADR / Product Architecture update**, not an EDR.

See `edrs/README.md`.

---

## Binding product decisions (non-negotiable)

| Decision | Canonical doc |
|----------|---------------|
| Everything is an Artifact | `../product-architecture/teacher-os/ARTIFACT_MODEL.md` |
| **ADR-046** Artifact Status Lifecycle (Draft→…→Archived; no exceptions) | `eduvijna-architecture/decisions/ADR-046-artifact-status-lifecycle.md` |
| Intent is stateless; Work is stateful | `../product-architecture/teacher-os/INTENT_AND_WORK.md` |
| Review Queue is the approval cockpit | `../product-architecture/teacher-os/REVIEW_QUEUE.md` |
| **ADR-048** Review Queue owns approval (teacher judgement only — not generation/editing/orchestration) | `eduvijna-architecture/decisions/ADR-048-review-queue-owns-approval.md` |
| Today's Mission is login landing | `../product-architecture/teacher-os/TODAYS_MISSION.md` |
| **ADR-042** Shell owns UX — not business capabilities | `eduvijna-architecture/decisions/ADR-042-teacher-os-shell-owns-ux.md` |
| **ADR-043** Foundation → Hardening → Review → Next Capability | `eduvijna-architecture/decisions/ADR-043-stable-foundations-before-features.md` |
| **ADR-044** AI Platform behind stable product services (no frontend agents/MCP) | `eduvijna-architecture/decisions/ADR-044-ai-platform-behind-stable-services.md` |
| **ADR-045** Teaching Intent owns goals; generators are capabilities (**constitutional**) | `eduvijna-architecture/decisions/ADR-045-teaching-intent-owns-goals.md` |
| **ADR-047** Outcome-first language (Prepare Tomorrow) | `eduvijna-architecture/decisions/ADR-047-outcome-first-prepare-tomorrow.md` |

---

## Document map

| Document | Role |
|----------|------|
| [ENGINEERING_CONSTITUTION.md](ENGINEERING_CONSTITUTION.md) | **This file** — root principles (v1.0 frozen) |
| [ENGINEERING_STANDARDS.md](ENGINEERING_STANDARDS.md) | Index + cross-cutting engineering rules |
| [CODING_STANDARDS.md](CODING_STANDARDS.md) | Folders, naming, code structure |
| [API_STANDARDS.md](API_STANDARDS.md) | Versioning, errors, pagination, auth, audit |
| [UI_STANDARDS.md](UI_STANDARDS.md) | Layout, states, AI progress, responsive (guidance) |
| [TESTING_STANDARDS.md](TESTING_STANDARDS.md) | Required test types and merge gates |
| [ACCESSIBILITY_STANDARDS.md](ACCESSIBILITY_STANDARDS.md) | a11y requirements |
| [FEATURE_FLAG_STANDARDS.md](FEATURE_FLAG_STANDARDS.md) | Flag metadata and rollout/removal |
| [OBSERVABILITY_STANDARDS.md](OBSERVABILITY_STANDARDS.md) | Logging + telemetry |
| [SECURITY_STANDARDS.md](SECURITY_STANDARDS.md) | AuthZ, secrets, PII, tenancy |
| [RELEASE_STANDARDS.md](RELEASE_STANDARDS.md) | Deploy order, verification, rollback |
| [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) | Every engineering review must answer these |
| [edrs/](edrs/) | Engineering Decision Records (implementation only) |

Blueprints (e.g. `EBP-001/`) implement Wave scope under this constitution.

---

## Conflict resolution

1. **Approved product architecture (PA-*)** — change here first if needed  
2. **Constitution principles (this v1.0)**  
3. Active engineering blueprint (EBP-*)  
4. Accepted EDRs (implementation detail only)  
5. Local repo conventions (only where they do not conflict)

---

## Change control (after freeze)

```text
Need contradicts Constitution or PA
        ↓
Update Product Architecture (PA review / ADR as required)
        ↓
Architecture approval
        ↓
Update Engineering Constitution / standards (version bump)
        ↓
Then implement
```

EDRs may be added freely for compliant implementation choices.

---

## Acceptance for Sprint 0

EBP-001 Sprint 0 coding **must not start** until Engineering Constitution **v1.0** is acknowledged by Product + Engineering leads.
