# Content Lifecycle

**ID:** PA-LIFE-001  
**Status:** Draft — PA-001 (aligned to Decision A — Artifact Model · **ADR-046**)  
**Canonical model:** `ARTIFACT_MODEL.md` · **ADR-046**

---

## Purpose

Define how **Artifacts** move from idea to classroom to archive — without duplicate “versions of truth.”

**Everything is an Artifact.** Types (worksheet, quiz, PPT, homework, rubric, question bank, …) are attributes.

**One lifecycle. No exceptions.** (ADR-046)

---

## Unified Artifact lifecycle (ADR-046)

```text
Draft
   ↓
Generating
   ↓
Generated
   ↓
In Review      ← Review Queue (generic — type-agnostic)
   ↓
Approved
   ↓
Published
   ↓
Archived
```

| State | Queue / product meaning |
|-------|-------------------------|
| Draft | Stub / pre-generate |
| Generating | Capability/orchestration in progress |
| Generated | Machine version ready; awaiting / entering queue |
| In Review | Opened / editing / Continuous Context refine |
| Approved | Ready to Publish |
| Published | Assigned/sent to audience |
| Archived | Library history |

Optional: **Superseded** when regenerate replaces an older Artifact version under the same Work (versioning detail — does not replace the ADR-046 public status set).

---

## Intent vs Work (Decision B)

- **Teaching Intent** is stateless and completes when orchestration finishes.  
- **Work** is stateful and holds Artifacts over time (continue, edit, share, duplicate, archive).  

See `INTENT_AND_WORK.md`.

---

## State rules

| From → To | Who | Rule |
|-----------|-----|------|
| Draft → Generating | System | Generation/orchestration started |
| Generating → Generated | System | Machine version complete |
| Generated → In Review | System / Teacher | Enters or opens Review Queue |
| In Review → Approved | Teacher | Explicit approve |
| Approved → Published | Teacher | Explicit assign/send |
| * → Archived | Teacher or policy | Remains searchable in Library |

**Product rule:** Student/parent-facing Artifacts cannot jump to Published without **In Review** approval.

---

## Object types in lifecycle

| Object | Notes |
|--------|-------|
| Teaching Intent | Parent object |
| Kit | Bundle of artefacts for an intent |
| Artefact | Lesson, worksheet, quiz, PPT, homework, rubric, question bank, etc. |
| Assignment / attempt | Student-facing instance of published artefact |
| Insight snapshot | Analyze output linked to Improve actions |

---

## Library relationship

- **Approved** and **Published** kits/artifacts appear in Library by default  
- **Draft / Generating / Generated / In Review** appear under Prepare / Queue, not Library browse (unless “my drafts” filter)  
- Duplicating Library item creates new Intent Draft (does not mutate history)

---

## Explainability & provenance

Each artefact retains:

- Intent that created it  
- Capabilities used (product names, not infra)  
- Context chips (board, class, chapter)  
- Memory style applied  
- Teacher edit flag (edited vs accepted as drafted)

---

## Related

- **ADR-046** Artifact Status Lifecycle  
- `ARTIFACT_MODEL.md`  
- `REVIEW_QUEUE.md`  
- `INTENT_AND_WORK.md`  
