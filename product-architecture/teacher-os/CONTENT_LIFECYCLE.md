# Content Lifecycle

**ID:** PA-LIFE-001  
**Status:** Draft — PA-001

---

## Purpose

Define how teaching artefacts move from idea to classroom to archive — without duplicate “versions of truth.”

---

## States

```text
Idea / Intent Draft
        ↓
Assembling (orchestration in progress)
        ↓
Ready for Review
        ↓
In Review (teacher editing)
        ↓
Approved (teacher-only)
        ↓
Published / Assigned (students or parents — if applicable)
        ↓
Completed (attempts/feedback in)
        ↓
Archived (Library history)
```

Optional: **Superseded** when a newer kit replaces an older for the same period.

---

## State rules

| From → To | Who | Rule |
|-----------|-----|------|
| Draft → Assembling | Teacher (Generate) | Intent validated |
| Assembling → Ready | System | All requested artefacts attempted |
| Ready → In Review | Teacher | Opens kit |
| In Review → Approved | Teacher | Explicit approve (full or partial) |
| Approved → Published | Teacher | Explicit assign/send |
| Published → Completed | System + Teacher | Attempts closed / marked |
| Any → Archived | Teacher or policy | Remains searchable in Library |

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
