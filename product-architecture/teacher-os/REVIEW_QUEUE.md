# Review Queue

**ID:** PA-REVIEW-Q-001  
**Status:** Draft — PA-001 Amendment  
**Role:** Signature Teacher OS experience — one place to review and approve AI outputs

---

## Problem

If teachers download or open AI files one by one (lesson, worksheet, quiz, PPT, homework, parent draft), approval becomes fragmented and easy to skip.

EduVijna needs a **single review surface**.

---

## Definition

**Review Queue** is the unified, **type-agnostic** list of **Artifacts** awaiting teacher judgement.

Per Decision A (*Everything is an Artifact*), the queue does not care whether the item is a worksheet, quiz, PPT, or parent draft — it operates on Artifact lifecycle state.

Every AI-generated Artifact that could reach a student, parent, or official record **must enter the Review Queue** before publish.

```text
Capability Orchestration
        ↓
Artifacts (AI Generated)
        ↓
Review Queue (generic)
  · any artifact_type
        ↓
Teacher Review → Approved
        ↓
Published (explicit)
```

---

## Why this is signature

| Old pattern | Review Queue |
|-------------|--------------|
| Open six tools / six downloads | One queue |
| Approve in scattered screens | Approve in one place |
| Easy to miss an artefact | Kit completeness visible |
| “Generate” feels like the product | **Review** feels like the product |

**Review →** from Today's Mission opens this queue.

---

## Queue item types (examples)

| Item | Typical Intent source |
|------|------------------------|
| Lesson Plan | Prepare Tomorrow |
| Worksheet | Prepare Tomorrow / Ingest |
| Quiz / Assessment | Prepare / Create Assessment / Observe |
| PPT | Prepare Tomorrow |
| Sketch Notes | Prepare Tomorrow |
| Homework | Prepare Tomorrow |
| Answer Key | With assessment/worksheet |
| Parent Draft | Communicate Parents |
| PTM Brief | Review Class / Improve |
| Remediation Pack | Create Remediation |
| Cover Pack | Recover Lost Period |

---

## Queue states (product)

| State | Meaning |
|-------|---------|
| Assembling | Orchestration still running |
| Needs review | Ready for teacher |
| In review | Teacher has opened/edited |
| Blocked | Failed / policy conflict — needs attention |
| Approved | Ready to Publish |
| Published | Assigned/sent |
| Dismissed | Rejected / not using |

---

## Review Queue UX behaviour

### List

- Group by **Intent / kit** (default) or by type  
- Filter: Today · Needs review · Approved · All  
- Badges: explain available, edited, Continuous Context thread  

### Item actions

| Action | Result |
|--------|--------|
| Open | Preview + edit + explain |
| Approve | Moves to Ready to Publish |
| Approve all in kit | When teacher confirms |
| Regenerate | Keeps Continuous Context; new draft replaces or versions |
| Make harder / shorter… | Follow-up via Continuous Context |
| Remove | Dismiss from kit |
| Publish / Assign / Send | Only from Approved items; explicit |

### Ready to Publish panel

Shows approved items ready for audience delivery — still requires explicit Publish.

---

## Rules

1. **No bypass** — student/parent-facing outputs cannot skip the queue (except audited school policy exceptions — default off).  
2. **Kit coherence** — approving a quiz does not auto-approve the worksheet.  
3. **One conversation** — regenerating from queue stays in Continuous Context.  
4. **Mission CTA** — Today's Mission “Review →” opens queue filtered to today.  
5. **Not a download manager** — primary verb is Review/Approve, not Download (download/print remain secondary).  

---

## Navigation home

| Access | Path |
|--------|------|
| Primary | Today's Mission → Review → |
| Persistent | Badge on shell / Today (“5 to review”) |
| From Prepare | After Generate → land in Review Queue for that kit |
| From Improve | Parent drafts land here too |

Review Queue is **not** a ninth empty nav icon competing with generators — it is the **approval cockpit** of Teacher OS.

Optional: top-level **Review** entry if badge density warrants; default architecture keeps it reachable from Mission + Prepare + global badge without duplicating Create.

---

## Signature test

A teacher can approve an entire Prepare Tomorrow kit (lesson, worksheet, quiz, PPT, homework, parent note) without leaving the Review Queue.

---

## Related

- `AI_ORCHESTRATION.md`  
- `CONTENT_LIFECYCLE.md`  
- `TODAYS_MISSION.md`  
- `CONTINUOUS_CONTEXT.md`  
- Wireframe: `../wireframes/REVIEW_QUEUE.md`
