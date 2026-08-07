# The Daily Loop

**ID:** MODEL-DAILY-LOOP-001  
**Status:** Draft — TLM-001 Amendment  
**Owner:** EduVijna Product Office  
**Role:** Central mental model of the Teacher OS

---

## The loop

EduVijna’s Teacher OS revolves around one continuous cycle:

```text
Prepare
   ↓
Teach
   ↓
Observe
   ↓
Assess
   ↓
Analyze
   ↓
Improve
   ↓
Prepare Again
```

This is not a feature list.  
This is the **product’s central mental model**.

Every capability, screen group, and AI service must belong to one or more of these six stages — or it does not belong in the Teacher OS.

---

## Stage definitions

### 1. Prepare

**Teacher job:** Walk into class ready.

**Includes:** Teaching Intent, lesson kits, materials, homework design, week pacing, substitute packs.

**Feels like:** Calm confidence before the bell.

---

### 2. Teach

**Teacher job:** Deliver learning in the period.

**Includes:** Run the plan, alternate explanations, in-class activities, materials in hand, manage time and room.

**Feels like:** Flow — with backup when the plan breaks.

---

### 3. Observe

**Teacher job:** Notice understanding and struggle in real time.

**Includes:** Exit checks, oral signals, confusion flags, attendance/presence, pastoral cues, “who is lost right now.”

**Feels like:** Seeing the room clearly — not guessing from the loudest students.

> Observe is often invisible in edtech. It is mandatory here. Without Observe, Assess becomes autopsy.

---

### 4. Assess

**Teacher job:** Evidence what was learned.

**Includes:** Quizzes, worksheets as scored work, unit tests, homework review, practicals, assisted evaluation.

**Feels like:** Fair measurement without drowning in scripts.

---

### 5. Analyze

**Teacher job:** Understand what the evidence means.

**Includes:** Concept heatmaps, weak-student lists, section comparisons, syllabus coverage vs mastery, parent/PTM evidence packs.

**Feels like:** Clarity — “I know what to do next Tuesday.”

---

### 6. Improve

**Teacher job:** Change the next teaching move.

**Includes:** Remediation groups, re-teach outlines, differentiated practice, pacing adjustments, Teacher Memory updates from edits/preferences, report/communication follow-through.

**Feels like:** Progress — the loop gets smarter every turn.

---

## Why the loop matters

| Without the loop | With the loop |
|------------------|---------------|
| Generators are souvenirs | Artefacts feed the next stage |
| Analytics are dashboards | Analytics trigger Improve → Prepare Again |
| AI is a first-time assistant | Memory + context compound across cycles |
| Features compete | Features have a home |

---

## Mapping Teacher OS navigation to the loop

| Teacher OS section | Primary loop stages |
|--------------------|---------------------|
| **Today** | Cross-cutting hub: what to Prepare / Teach / Observe *now* |
| **Prepare** | Prepare |
| **Teach** | Teach + Observe (in-period) |
| **Assess** | Assess + Analyze |
| **Improve** | Improve → feeds Prepare Again |
| **AI Assistant** | Cross-stage helper that always returns to an intent or loop stage |

---

## Feature placement rule

Before any feature is prioritised, answer:

1. Which loop stage does it primarily serve?  
2. What does it hand off to the next stage?  
3. Does it strengthen Teaching Intent, Teacher Memory, or School Context — or ignore them?

If it creates a dead-end artefact with no handoff, it is incomplete.

---

## Example: one topic through the loop

**Topic:** Photosynthesis · Class 7-B · Science

| Stage | What happens |
|-------|--------------|
| Prepare | Intent → lesson + worksheet + exit quiz + homework |
| Teach | Deliver lesson; use alternate example when faces blank |
| Observe | 5-question exit check shows 12 students miss “chlorophyll role” |
| Assess | Short quiz next day confirms the gap |
| Analyze | Heatmap isolates concept + names |
| Improve | Remediation mini-kit approved; Memory notes “more diagram-first for this class” |
| Prepare Again | Next intent already biased toward diagram-first + chlorophyll practice |

---

## Related

- Teaching Intent: `TEACHING_INTENT.md`  
- Teacher OS: `TEACHER_OS.md`  
- Journeys: `../journeys/teacher/daily-journey.md`
