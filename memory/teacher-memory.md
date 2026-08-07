# Teacher Memory

**ID:** MODEL-TEACHER-MEMORY-001  
**Status:** Draft — TLM-001 Amendment  
**Owner:** EduVijna Product Office  
**Role:** Persistent teacher profile that compounds across the Daily Loop

---

## Problem

Without memory, every AI interaction behaves like a **first-time assistant**.

The teacher re-explains:

- language  
- board  
- subjects and grades  
- difficulty taste  
- worksheet style  
- school norms  

That tax destroys trust and time savings.

---

## Definition

**Teacher Memory** is a persistent, teacher-owned profile that stores durable preferences and learned patterns so every Teaching Intent starts from *this teacher*, not a generic model.

Memory is not surveillance.  
Memory is **continuity of professional identity**.

---

## What Teacher Memory holds

### A. Identity & assignment

| Memory item | Example |
|-------------|---------|
| Preferred language(s) | English + Telugu parent tone |
| Board | CBSE |
| Subjects | Science, maybe Computer temporary |
| Grades / sections | 6–8; Class Teacher 7-B |
| Medium of instruction | English |
| Role mix | Class teacher + subject teacher |

### B. Pedagogical preferences

| Memory item | Example |
|-------------|---------|
| Difficulty preference | Slightly scaffolded for 7-B; stretch set for toppers |
| Worksheet style | Short mixed (MCQ + FITB + one diagram); clean print layout |
| Bloom’s Taxonomy preference | Remember/Understand heavy mid-week; Apply on Fridays |
| Explanation style | Diagram-first; local analogies; avoid long paragraphs |
| PPT / sketch notes preference | Minimal slides; sketch-note summaries preferred |
| Homework load philosophy | Light weekday; deeper weekend only before tests |

### C. Institutional overlays (cached from School Context, personalised)

| Memory item | Example |
|-------------|---------|
| School policies that affect her | No WhatsApp homework after 7 PM (personal boundary + school) |
| Assessment norms she follows | Unit test blueprint ratios she actually uses |
| Remark tone | Firm-kind; avoid comparative ranking language |

### D. Learned from use (continuous improvement)

| Memory item | Example |
|-------------|---------|
| Frequent edit patterns | Always deletes trick questions; adds one diagram |
| Successful kits | “Photosynthesis kit v3” reused next year |
| Class-specific notes | 7-B needs more visuals; 8-A handles abstraction |
| Rejected AI behaviours | Never invent topics outside chapter list |

---

## How memory is populated

| Source | Mechanism |
|--------|-----------|
| Onboarding | Short preference capture (board, subjects, language, style) |
| School Context bind | Inherit school defaults; teacher overrides personal layer |
| Teaching Intent usage | Store recurring artefact choices |
| Teacher edits | Edits are gold — update preference weights |
| Explicit controls | Teacher can view, edit, reset memory categories |

---

## Privacy & control

1. Teacher can see what Memory believes about them  
2. Teacher can correct or delete preference items  
3. Student-identifying analytics are **not** dumped into a free-form teacher “personality” store without purpose limitation  
4. Memory stays within school tenancy / governance rules  
5. Memory never auto-sends to students or parents  

---

## Relationship to other models

```text
School Context  →  institutional defaults
Teacher Memory  →  personal + learned preferences
Teaching Intent →  this moment’s goal
        ↓
Orchestration uses all three
        ↓
Daily Loop stages consume outputs
        ↓
Improve stage writes back to Memory
```

---

## Product implications

| Without Memory | With Memory |
|----------------|-------------|
| Every generate asks board/grade again | Intent is short; defaults are smart |
| Style drifts randomly | Kits feel “hers” |
| Improve stage dies | Improve compounds into Prepare Again |

---

## Capability gap

| Activity | Existing EduVijna Capability | Gap |
|----------|------------------------------|-----|
| Persistent teacher preference profile | Quotas / user accounts / partial personalisation signals | **Missing / New** |
| Learn from teacher edits | — | **Missing / New** |
| Visible memory controls | — | **Missing / New** |

---

## Success test

After two weeks of use, a teacher can say:

> “It already knows how I teach Class 7.”

---

## Related

- School Context: `../context/school-context.md`  
- Teaching Intent: `../vision/TEACHING_INTENT.md`  
- Daily Loop Improve stage: `../vision/DAILY_LOOP.md`
