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
Capability Orchestration
   ↓
Review
   ↓
Publish
```

---

## Stage behaviours

### 1. Teacher

Expresses outcome in Teacher OS (Prepare, Assess, Improve, or AI Assistant).  
May attach sources.  
Sees Memory + Context chips — does not re-enter school facts.

### 2. Teaching Intent

OS normalises the request into an Intent type + parameters (class, topic, when, artefact checklist).  
Assistant chat **proposes** an Intent; teacher confirms before orchestration.

### 3. Capability Orchestration

OS selects and sequences **existing EduVijna capabilities** (and declared new kit parts) to draft artefacts.  
Product requirements:

- Prefer reuse over new parallel generators  
- Keep kit coherent (same topic, difficulty band, language)  
- Attach explainability per artefact and for the kit  
- Respect quotas / entitlements as user-visible constraints (not infra detail)

### 4. Review

Teacher lands on **Kit Review** (or single-artefact review for narrow intents).  
Actions: edit · regenerate one · remove · explain · approve subset · reject.

**AI never skips Review for student/parent-facing outputs.**

### 5. Publish

Publish means: make available to the intended audience under policy.

| Audience | Gate |
|----------|------|
| Teacher-only (lesson notes) | Approve to Library / Teach |
| Students | Explicit publish/assign after approval |
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
