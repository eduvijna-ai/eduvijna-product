# AI Orchestration (Product Perspective)

**ID:** PA-ORCH-AI-001  
**Status:** Draft — PA-001  
**No backend · no prompts · no model selection**

---

## Canonical flow

```text
Teacher
   ↓
Teaching Intent
   ↓
Continuous Context (thread opens)
   ↓
Capability Orchestration
   ↓
Review Queue          ← signature experience
   ↓
Ready to Publish
   ↓
Publish (explicit)
```

Follow-ups (“make worksheet harder”) stay inside **Continuous Context** and update the focused Review Queue item — they do not restart the Intent from zero.

---

## Stage behaviours

### 1. Teacher

Expresses outcome in Teacher OS (Prepare, Assess, Improve, AI Assistant, or Mission → Review).  
May attach sources.  
Sees Memory + Context chips — does not re-enter school facts.  
May refine with short directives while Continuous Context is active.

### 2. Teaching Intent

OS normalises the request into an Intent type + parameters (class, topic, when, artefact checklist).  
Assistant chat **proposes** an Intent; teacher confirms before orchestration.  
Opens a Continuous Context thread.

### 3. Continuous Context

Holds active Intent, artefacts in play, recent directives, and queue focus.  
Distinct from durable Teacher Memory and institutional School Context.  
See `CONTINUOUS_CONTEXT.md`.

### 4. Capability Orchestration

OS selects and sequences **existing EduVijna capabilities** (and declared new kit parts) to draft artefacts.  
Product requirements:

- Prefer reuse over new parallel generators  
- Keep kit coherent (same topic, difficulty band, language)  
- Attach explainability per artefact and for the kit  
- Respect quotas / entitlements as user-visible constraints (not infra detail)  
- **Every output enters Review Queue**

### 5. Review Queue

Teacher lands on the **Review Queue** (kit-grouped), not a pile of downloads.  
Actions: edit · regenerate one · follow-up refine · explain · approve subset · reject.  
See `REVIEW_QUEUE.md`.

**AI never skips Review Queue for student/parent-facing outputs.**

### 6. Ready to Publish → Publish

Approved items appear in Ready to Publish.  
Publish/Assign/Send is an explicit second step.

| Audience | Gate |
|----------|------|
| Teacher-only (lesson notes) | Approve → available in Teach/Library |
| Students | Explicit assign after approval |
| Parents | Explicit send after approval |
| Report cards / official marks | Explicit confirm into records |

---

## Orchestration principles (product)

| Principle | Behaviour |
|-----------|-----------|
| One conversation | Intent is the conversation unit |
| Minimum clicks | Defaults from Memory/Context |
| Always explain AI | Why this question / difficulty / chapter |
| Teacher control | Edit beats regenerate beats accept |
| Never surprise | No silent send; clear status |
| Fast review | Kit summary first; deep edit on demand |

---

## Failure behaviours (product)

| Situation | Teacher experience |
|-----------|--------------------|
| Partial capability failure | Kit shows succeeded parts + retry for failed |
| Low confidence alignment | Warning + explain; still reviewable |
| Policy conflict | Block publish with plain-language reason |
| Offline | Work on last approved kits; queue new intents when defined by rollout |

---

## Related

- `CAPABILITY_ORCHESTRATION.md`  
- `CONTENT_LIFECYCLE.md`  
- `EXPERIENCE_PRINCIPLES.md`
