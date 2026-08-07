# Teaching Intent

**ID:** MODEL-TEACHING-INTENT-001  
**Status:** Draft — TLM-001 Amendment  
**Owner:** EduVijna Product Office  
**Role:** Product ↔ orchestration contract (conceptual API, not implementation)

---

## Why this exists

Activity-based product thinking produces a menu of generators:

- Worksheet  
- Quiz  
- PPT  
- Lesson plan  
- Homework  

Teachers do not wake up wanting a worksheet generator.

Teachers wake up with a **teaching intent**.

---

## Definition

**Teaching Intent** is the single statement of what the teacher wants to accomplish for a class, topic, and time window — expressed once, then fulfilled by many coordinated AI services under teacher approval.

```text
Teaching Intent
      ↓
Prepare Tomorrow   (or Prepare This Period / This Week / This Unit)
      ↓
┌─────────────────────────────────────────────────────────┐
│  Lesson Plan                                            │
│  Worksheet                                              │
│  Quiz / Exit Check                                      │
│  PPT / Slides                                           │
│  Sketch Notes                                           │
│  Homework                                               │
│  (+ Remediation pack, flashcards, parent note — as needed) │
└─────────────────────────────────────────────────────────┘
      ↓
Teacher reviews · edits · approves
      ↓
Ready for Teach stage of the Daily Loop
```

---

## Teaching Intent as the product–orchestration API

Teaching Intent is the **contract** between:

| Side | Responsibility |
|------|----------------|
| **Product (Teacher OS)** | Capture intent in teacher language; bind Teacher Memory + School Context; present reviewable kit |
| **Orchestration engine** | Expand one intent into the right set of AI services; respect policies, quotas, and approval gates |

The teacher never addresses the orchestration engine directly.  
The teacher addresses **intent**.

### Conceptual intent shape (product, not schema)

| Field group | Examples |
|-------------|----------|
| Who | Teacher identity (from Teacher Memory) |
| Where | School, board, medium (from School Context) |
| Whom | Grade, section, subject, class roster context |
| What | Topic / chapter / learning outcome |
| When | Period length, date, timetable slot |
| Why now | Tomorrow’s class, revision, remediation, exam prep |
| How | Preferred artefacts (lesson + worksheet + quiz…); difficulty; Bloom emphasis |
| Constraints | Printable, bilingual, no devices, lab available, lost-period filler |

Teachers may state only: *“Prepare tomorrow’s Class 7-B Science on photosynthesis.”*  
Memory + School Context fill the rest. Intent remains editable.

---

## Intent types (initial catalogue)

| Intent | Typical outputs |
|--------|-----------------|
| **Prepare Tomorrow** | Lesson plan, worksheet, quiz/exit check, PPT, sketch notes, homework |
| **Prepare This Period** (same-day / cover) | Compact activity pack + check |
| **Revise for Test** | Practice paper variants, flashcards, weak-topic drills |
| **Remediate Weak Concepts** | Differentiated practice groups + short re-teach outline |
| **Create Assessment** | Blueprint-aligned paper + answer key + section variants |
| **Communicate Progress** | Parent message draft / PTM brief / remark draft (approval required) |
| **Recover Lost Period** | Alternate activity + re-paced week suggestion |

**Prepare Tomorrow** is the flagship intent for Teacher OS v1 narrative.

---

## Relationship to generators

Generators remain **services**, not the product surface.

| Old mental model | New mental model |
|------------------|------------------|
| Open Worksheet Generator | State Teaching Intent → receive kit including worksheet |
| Open Quiz Generator | Same intent may include quiz without a second tool hunt |
| Open PPT tool | PPT is an optional artefact inside the intent |

Capability mapping must therefore include:

1. **Intent layer** (product API)  
2. **Artefact services** (orchestrated outputs)  
3. **Activity / ERP ops** (attendance, marks entry, etc.)

---

## Approval rule

Every student-facing or parent-facing artefact produced from an intent requires **human approval** before delivery — per Product Principles.

Orchestration may draft many things.  
Orchestration may not publish many things.

---

## Success test

A teacher can express one intent and, within minutes, review a coherent kit that feels written for *her* school, *her* class, and *her* style — without re-entering board, language, or policy.

---

## Related

- Daily Loop: `DAILY_LOOP.md`  
- Teacher Memory: `../memory/teacher-memory.md`  
- School Context: `../context/school-context.md`  
- Teacher OS: `TEACHER_OS.md`  
- Capability map: `../capability-mapping/teacher-capabilities.md`
