# Artifact Model

**ID:** PA-ARTIFACT-001  
**Decision:** A — Everything is an Artifact  
**Status:** Accepted (product architecture)  
**Lifecycle authority:** **ADR-046** (Artifact Status Lifecycle) — **no exceptions**  
**Influences:** Every sprint from EBP-001 forward

---

## Decision

Stop thinking primarily in type silos (Worksheet · Quiz · PPT).

**Every generated item is an Artifact.**

Types are **attributes** of an Artifact, not separate product systems.

---

## Why

| Type-first thinking | Artifact-first thinking |
|---------------------|-------------------------|
| New Review UI per type | One Review Queue for all |
| Divergent lifecycles | One lifecycle |
| Hard to add Sketch Notes / Parent Draft | New `artifact_type` only |
| Inconsistent approval | Same gates everywhere |

This makes future capabilities cheaper and keeps **AI Assists, Teacher Decides** enforceable in one place.

---

## Unified lifecycle (ADR-046)

**Every** Artifact type — Worksheet, Quiz, Lesson Plan, PPT, Homework, Rubric, Question Bank, and all future types — uses this lifecycle. **No exceptions.**

```text
Draft
   ↓
Generating
   ↓
Generated
   ↓
In Review
   ↓
Approved
   ↓
Published
   ↓
Archived
```

| State | Meaning |
|-------|---------|
| **Draft** | Stub / teacher-started shell; not yet (or not currently) generating |
| **Generating** | Capability/orchestration in progress |
| **Generated** | Machine produced a version; awaiting human review admission |
| **In Review** | In Review Queue / teacher editing, regenerating, or deciding |
| **Approved** | Teacher accepted; ready to publish |
| **Published** | Delivered to intended audience (students/parents/records) |
| **Archived** | Retained in Library history; not active |

Canonical record: `eduvijna-architecture/decisions/ADR-046-artifact-status-lifecycle.md`.

---

## Artifact (product shape — not a DB schema)

| Field group | Examples |
|-------------|----------|
| Identity | artifact_id, version |
| Type | worksheet \| quiz \| lesson_plan \| ppt \| homework \| rubric \| question_bank \| … |
| Lifecycle state | Draft → Generating → Generated → In Review → Approved → Published → Archived |
| Provenance | intent_id (optional, may be completed), work_id, capabilities used |
| Context chips | school, class, subject, topic (from School Context + Continuous Context at creation) |
| Ownership | teacher_id, school_id |
| Payload | type-specific body (questions, slides, message text…) |
| Explainability | why this version |

Review Queue **does not care** what the content is — it operates on Artifact + state + actions (open, edit, regenerate, approve, reject).

---

## Implications for engineering

1. Prefer one Artifact API/list filter over per-type queue endpoints.  
2. Generators produce Artifacts (reuse existing content rows as Artifact backing where possible).  
3. New capability = new type + renderer, not a new queue product **or** a new lifecycle.  
4. Library indexes Artifacts in Approved/Published/Archived.  
5. Telemetry uses `artifact_id`, `artifact_type`, `lifecycle_state` (ADR-046 names only).  
6. Backend AI job states (ADR-044) must **map into** Generating / Generated — not invent UI-facing enums.

---

## Non-goals

- Forcing one UI editor for all types (type-specific editors OK behind generic shell)  
- Migrating all legacy content in Wave 1 (wrap/adapt progressively)

---

## Related

- **ADR-046** Artifact Status Lifecycle  
- `CONTENT_LIFECYCLE.md` (align to ADR-046)  
- `REVIEW_QUEUE.md`  
- `INTENT_AND_WORK.md` (Decision B)  
