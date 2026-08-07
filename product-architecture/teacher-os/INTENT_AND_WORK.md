# Intent and Work

**ID:** PA-INTENT-WORK-001  
**Decision:** B — Intent is Stateless, Work is Stateful  
**Status:** Accepted (product architecture)  
**Influences:** Every sprint from EBP-001 forward

---

## Decision

| Concept | Nature | Lifespan |
|---------|--------|----------|
| **Teaching Intent** | Stateless request | Completes when orchestration has produced Work/Artifacts (or fails/cancels) |
| **Work** | Stateful container | Persists across days/weeks — continue, edit, share, duplicate, archive |

Teacher says: **“Prepare tomorrow.”**  
The **intent finishes**.  
The **resulting work persists**.

---

## Why

Intents are verbs (“prepare”, “remediate”, “communicate”).  
Work is the durable project that holds Artifacts over time.

Without this split:

- Teachers cannot “continue tomorrow” cleanly  
- Sessions and intents get confused with long-lived documents  
- Duplicate/archive/share have no home object  

---

## Product behaviour

```text
Teacher: Prepare tomorrow · Grade 8 Science · Photosynthesis
        ↓
Intent (stateless) runs → orchestrates capabilities
        ↓
Work (stateful) created/updated: "Photosynthesis · 8-A · 8 Aug"
        ↓
Artifacts attached (lesson, worksheet, quiz, …) in AI Generated / Teacher Review
        ↓
Intent completes (success)
        ↓
Teacher later: continue / edit / share / duplicate / archive the Work
```

### What teachers can do with Work

| Action | Meaning |
|--------|---------|
| Continue tomorrow | Re-open Work; resume Review Queue items |
| Edit next week | New Artifact versions under same Work |
| Share later | Publish from Approved Artifacts when ready |
| Duplicate | New Work (+ Artifact copies) from existing Work |
| Archive | Work + Artifacts → Archived |

### What Intent does *not* do

- Intent is not the long-lived folder  
- Intent is not re-run automatically every login  
- Completed intents are history/telemetry, not the editing surface  

---

## Relationship to Continuous Context

| Concept | Role |
|---------|------|
| **Intent** | Fire-and-complete request |
| **Continuous Context** | In-session thread while Intent/Work is actively refined |
| **Work** | Durable home after the session ends |
| **Artifact** | Unit of review/publish inside Work |

---

## Implications for engineering

1. Persist **Work** (or map clearly onto existing content collections / kits).  
2. Review Queue lists **Artifacts** (optionally grouped by Work).  
3. Mission / Continue deep-links to **Work**, not to a dead Intent id.  
4. “Prepare tomorrow” again on same topic may create new Work or offer Continue existing Work (product prompt).  
5. Do not delete Work when Intent completes.

---

## Wave 1 minimum

- Name the distinction in APIs/UI copy where visible (“Continue work” vs “New prepare”)  
- Back Work with existing kit/content grouping if a full Work table is not ready — but **do not** treat Intent as the durable object  

---

## Related

- `TEACHING_INTENT_MODEL.md`  
- `ARTIFACT_MODEL.md`  
- `CONTINUOUS_CONTEXT.md`  
- `REVIEW_QUEUE.md`  
