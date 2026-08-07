# Artifact Model

**ID:** PA-ARTIFACT-001  
**Decision:** A — Everything is an Artifact  
**Status:** Accepted (product architecture)  
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

## Unified lifecycle

```text
Draft
   ↓
AI Generated
   ↓
Teacher Review      ← Review Queue (generic)
   ↓
Approved
   ↓
Published
   ↓
Archived
```

| State | Meaning |
|-------|---------|
| **Draft** | Intent/work stub or teacher-started empty shell |
| **AI Generated** | Orchestration produced a version; awaiting human |
| **Teacher Review** | In Review Queue / being edited |
| **Approved** | Teacher accepted; Ready to Publish |
| **Published** | Delivered to intended audience (students/parents/records) |
| **Archived** | Retained in Library history; not active |

Mapping from earlier PA wording: *Needs review / In review* ⊂ **Teacher Review**; *Ready to Publish* = **Approved**; etc.

---

## Artifact (product shape — not a DB schema)

| Field group | Examples |
|-------------|----------|
| Identity | artifact_id, version |
| Type | worksheet \| quiz \| lesson_plan \| ppt \| sketch_notes \| homework \| parent_draft \| … |
| Lifecycle state | Draft → … → Archived |
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
3. New capability = new type + renderer, not a new queue product.  
4. Library indexes Artifacts in Approved/Published/Archived.  
5. Telemetry uses `artifact_id`, `artifact_type`, `lifecycle_state`.

---

## Non-goals

- Forcing one UI editor for all types (type-specific editors OK behind generic shell)  
- Migrating all legacy content in Wave 1 (wrap/adapt progressively)

---

## Related

- `CONTENT_LIFECYCLE.md` (aligned to this lifecycle)  
- `REVIEW_QUEUE.md`  
- `INTENT_AND_WORK.md` (Decision B)  
