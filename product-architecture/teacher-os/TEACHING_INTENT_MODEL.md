# Teaching Intent Model

**ID:** PA-INTENT-001  
**Status:** Draft — PA-001 · **bound by ADR-045 (constitutional)**  
**Role:** Heart of Teacher OS — product behaviour only  
**Strategic expression:** ADR-047 — “Help me prepare tomorrow.”  
**Service boundary:** ADR-044 — Teacher OS talks only to stable application services (never agents/MCP in the frontend).  
**Artifact lifecycle:** ADR-046 — one status machine for every type (no exceptions).

---

## Definition

A **Teaching Intent** is the teacher’s stated outcome for a class, topic, and time window.

**ADR-045:** Teaching Intent owns teacher goals. Generators are capabilities behind Intent — they do not own goals.

The OS expands one intent into multiple capabilities, then presents a **single kit** for review and approval.

```text
Teacher states Intent
        ↓
School Context + Teacher Memory attach automatically
        ↓
Capability Orchestration assembles artefacts
        ↓
Teacher reviews / edits / regenerates
        ↓
Teacher approves
        ↓
Artefacts become available to Teach / Assess / Improve / Library
```

---

## Product behaviour rules

1. Teacher speaks outcomes, not tool names.  
2. Defaults come from Memory + Context — teacher may override.  
3. Orchestration may draft many artefacts; **publish requires approval**.  
4. Partial approval is allowed (approve lesson now, hold quiz).  
5. Every intent has a lifecycle: Draft → Assembling → Ready for review → Partially approved → Approved → Archived.  
6. Reuse: duplicating a past kit creates a **new intent** prefilled from Library.

---

## Intent catalogue (v1)

### INT-PREPARE-TOMORROW

| | |
|--|--|
| **When** | Planning next day’s period(s) |
| **Teacher says** | “Prepare tomorrow’s Class 7-B Science on photosynthesis” |
| **Default artefacts** | Learning objectives, Lesson plan, Worksheet, Quiz/exit check, PPT/slides (if enabled), Sketch notes, Homework, Answer key |
| **Reuse** | Worksheet, quiz, lesson, flashcard, ingest capabilities |
| **Handoff** | Teach (kit) · Assess (quiz) · Library |

### INT-PREPARE-EXAM-WEEK

| | |
|--|--|
| **When** | Unit/term exam window |
| **Teacher says** | “Prepare exam week for Grade 8 Science Chapter 5–8” |
| **Default artefacts** | Blueprint-aligned practice paper(s), section variants, revision plan, flashcards, answer key, weak-topic drills |
| **Handoff** | Assess · Improve (remediation) |

### INT-CREATE-REMEDIATION

| | |
|--|--|
| **When** | After Analyze shows gaps |
| **Teacher says** | “Remediate chlorophyll misconceptions for 12 students” |
| **Default artefacts** | Re-teach outline, differentiated practice, short check quiz, optional parent note draft |
| **Handoff** | Teach/Assess · Improve communicate |

### INT-REVIEW-CLASS

| | |
|--|--|
| **When** | Need class health snapshot |
| **Teacher says** | “Review Class 7-B Science this fortnight” |
| **Default artefacts** | Attendance/performance narrative, concept heatmap summary, action list, PTM-ready bullets |
| **Handoff** | Improve hub |

### INT-PLAN-REVISION

| | |
|--|--|
| **When** | Pre-exam revision block |
| **Teacher says** | “Plan 5-day revision for light chapter set” |
| **Default artefacts** | Day-wise revision plan, mixed practice, sketch-note summaries |
| **Handoff** | Prepare week plan · Assess practice |

### INT-COMMUNICATE-PARENTS

| | |
|--|--|
| **When** | Updates, concerns, PTM follow-ups |
| **Teacher says** | “Draft message to parents of students weak in fractions” |
| **Default artefacts** | Message draft(s) multilingual, optional evidence bullets |
| **Handoff** | Improve communicate — **always approve before send** |

### INT-RECOVER-LOST-PERIOD

| | |
|--|--|
| **When** | Substitution, assembly overrun, cancellation |
| **Teacher says** | “Cover period for 7-B Science — 30 minutes” |
| **Default artefacts** | Compact activity, mini-check, optional homework light |
| **Handoff** | Teach cover |

### INT-CREATE-ASSESSMENT *(explicit)*

| | |
|--|--|
| **When** | Formal test creation without full lesson kit |
| **Teacher says** | “Create unit test on Chapter 3 — CBSE pattern” |
| **Default artefacts** | Paper, variants, answer key, explanations |
| **Reuse** | Assessment generators, source ingest |
| **Handoff** | Assess conduct |

### INT-INGEST-TO-ASSETS

| | |
|--|--|
| **When** | Teacher has PDF/notes/video to convert |
| **Teacher says** | “Turn this PDF into a quiz and worksheet” |
| **Default artefacts** | Quiz, worksheet, summary as chosen |
| **Reuse** | Existing ingest pipelines |
| **Handoff** | Kit review · Library |

---

## Intent card (what teacher sees)

| Element | Behaviour |
|---------|-----------|
| Intent type | Selected or inferred |
| Class / subject / topic | Prefill from Context + timetable; editable |
| When | Tomorrow / date / exam week |
| Artefact checklist | Defaults on; teacher toggles |
| Sources | Optional attach |
| Explain | Why these artefacts / difficulty |
| Generate | Creates draft kit |
| Status | Lifecycle badge |

---

## Orchestration expectations (product)

For **Prepare Tomorrow**, behaviour must feel like one action:

> Teacher confirms intent → waits briefly → reviews a coherent kit → edits outliers → approves → assigned to tomorrow’s period.

Not: open six tools serially.

---

## Missing capabilities this model exposes

| Need | Status from TLM capability map |
|------|--------------------------------|
| Intent layer itself | New |
| PPT / sketch notes services | Missing / New |
| Remediation grouping | Missing / New |
| Unified kit object | New |
| Parent draft intent | New |

Existing worksheet/quiz/lesson/flashcard/ingest **must be reused** as services under intents.

---

## Related

- `CAPABILITY_ORCHESTRATION.md`  
- `AI_ORCHESTRATION.md`  
- `CONTENT_LIFECYCLE.md`
