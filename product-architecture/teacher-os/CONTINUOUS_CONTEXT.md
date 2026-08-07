# Continuous Context

**ID:** PA-CTX-CONT-001  
**Status:** Draft — PA-001 Amendment  
**Role:** Session continuity across related teaching actions — not durable Teacher Memory

---

## Problem

Without session continuity, every follow-up feels like a new request:

> Prepare Grade 8 → Worksheet → Quiz → “Make worksheet harder”

…and the AI forgets Grade 8, the topic, and that the quiz belongs to the same kit.

---

## Definition

**Continuous Context** is the active working thread for a Teaching Intent (or related intent chain) within a session.

It persists across related actions so the teacher can refine without re-stating school, class, topic, or prior artefacts.

```text
Teacher: Prepare Grade 8
        ↓
OS: Intent + School Context + Teacher Memory attached
        ↓
Worksheet drafted  →  enters Review Queue
        ↓
Quiz drafted       →  enters Review Queue (same thread)
        ↓
Teacher: Make worksheet harder
        ↓
AI already knows: Grade 8 · topic · kit · which worksheet · prior difficulty
        ↓
Harder worksheet replaces/updates queue item — conversation continues
```

---

## What Continuous Context holds (product)

| Layer | Examples |
|-------|----------|
| Active Intent | Prepare Tomorrow · Grade 8 Science · Photosynthesis |
| Thread id | Stable for this working session/kit |
| Artefacts in play | Worksheet v2, Quiz v1, Lesson v1 |
| Recent teacher directives | “Make worksheet harder”, “Add one diagram” |
| Review Queue focus | Which item is open |
| Inherited chips | Board, language, period (from School Context + Memory) |

---

## Continuous Context vs Teacher Memory vs School Context

| Concept | Lifespan | Purpose |
|---------|----------|---------|
| **School Context** | Institutional / ongoing | Auto-inherit school facts |
| **Teacher Memory** | Durable across weeks | Style, preferences, learned patterns |
| **Continuous Context** | Session / active Intent thread | Keep *this* conversation coherent |

Continuous Context may **propose** Memory updates (“Always prefer harder worksheets for 8-A?”) — teacher confirms.

---

## Product behaviour rules

1. Related actions stay in one thread until teacher starts a **new Intent** or explicitly clears context.  
2. Follow-ups like “make it harder”, “shorter”, “add MCQs” apply to the **focused artefact** (or kit if stated).  
3. Switching artefacts in Review Queue does not kill the thread — focus moves.  
4. Starting “Prepare Grade 7” starts a **new** thread (with confirmation if current thread has unsaved review work).  
5. AI Assistant and Prepare share the same Continuous Context when working the same Intent.  
6. Never publish from a follow-up utterance — still Review → Approve.

---

## Experience principle alignment

- **One Conversation** — Continuous Context is the mechanism  
- **Minimum Clicks** — no re-entry of Grade/topic  
- **Never Surprise** — show thread chips (“Grade 8 · Photosynthesis · Worksheet”)  
- **Teacher Control** — clear / switch thread visible

---

## Signature test

Teacher can say only “make the worksheet harder” and the OS updates the correct artefact without asking which class.

---

## Related

- `TEACHER_MEMORY.md`  
- `SCHOOL_CONTEXT.md`  
- `TEACHING_INTENT_MODEL.md`  
- `REVIEW_QUEUE.md`  
- `AI_ORCHESTRATION.md`
