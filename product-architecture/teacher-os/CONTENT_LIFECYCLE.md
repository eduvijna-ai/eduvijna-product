# Content Lifecycle

**ID:** PA-LIFE-001  
**Status:** Draft — PA-001 (aligned to Decision A — Artifact Model)  
**Canonical model:** `ARTIFACT_MODEL.md`

---

## Purpose

Define how **Artifacts** move from idea to classroom to archive — without duplicate “versions of truth.”

**Everything is an Artifact.** Types (worksheet, quiz, PPT, …) are attributes.

---

## Unified Artifact lifecycle (Decision A)

```text
Draft
   ↓
AI Generated
   ↓
Teacher Review      ← Review Queue (generic — type-agnostic)
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
| AI Generated | Entered queue as needs review |
| Teacher Review | Opened / editing / Continuous Context refine |
| Approved | Ready to Publish |
| Published | Assigned/sent to audience |
| Archived | Library history |

Optional: **Superseded** when regenerate replaces an older Artifact version under the same Work.

---

## Intent vs Work (Decision B)

- **Teaching Intent** is stateless and completes when orchestration finishes.  
- **Work** is stateful and holds Artifacts over time (continue, edit, share, duplicate, archive).  

See `INTENT_AND_WORK.md`.

---

## State rules

| From → To | Who | Rule |
|-----------|-----|------|
| Draft → AI Generated | System (generate) | Intent may complete; Work persists; Artifact enters Review Queue |
| AI Generated → Teacher Review | Teacher | Opens queue item |
| Teacher Review → Approved | Teacher | Explicit approve |
| Approved → Published | Teacher | Explicit assign/send |
| * → Archived | Teacher or policy | Remains searchable in Library |

**Product rule:** Student/parent-facing Artifacts cannot jump to Published without Teacher Review approval.


---

## Object types in lifecycle

| Object | Notes |
|--------|-------|
| Teaching Intent | Parent object |
| Kit | Bundle of artefacts for an intent |
| Artefact | Lesson, worksheet, quiz, PPT, sketch notes, homework, message draft, etc. |
| Assignment / attempt | Student-facing instance of published artefact |
| Insight snapshot | Analyze output linked to Improve actions |

---

## Library relationship

- **Approved** and **Completed** kits appear in Library by default  
- **Draft / In Review** appear under Prepare, not Library browse (unless “my drafts” filter)  
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

- `AI_ORCHESTRATION.md`  
- Library screens in `SCREEN_HIERARCHY.md`
