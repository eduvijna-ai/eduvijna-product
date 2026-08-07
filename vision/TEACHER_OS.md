# Teacher OS

**ID:** MODEL-TEACHER-OS-001  
**Status:** Draft — TLM-001 Amendment  
**Owner:** EduVijna Product Office  
**Role:** Product information architecture (not UI design)

---

## Purpose

Define how the Teacher product is organised in the teacher’s mind.

This is a **navigation and capability home** model — not wireframes, not React routes.

---

## Structure

```text
Teacher OS

├── Today
├── Prepare
├── Teach
├── Assess
├── Improve
└── AI Assistant
```

Every existing and future teacher feature should reorganize into one of these sections.

---

## Section definitions

### Today

**Job:** Orient the teacher to *this school day*.

**Contains:**

- Today’s timetable periods  
- Ready / not-ready Teaching Intents for upcoming periods  
- Observe signals waiting (unchecked exit tickets, flagged students)  
- Urgent school notices that affect teaching  
- One-tap continue: “Resume Prepare Tomorrow” / “Review exit check”  

**Loop role:** Cross-cutting hub into Prepare, Teach, Observe.

---

### Prepare

**Job:** Turn Teaching Intent into an approved kit.

**Contains:**

- Teaching Intent composer (“Prepare Tomorrow…”)  
- Lesson kits (lesson plan, worksheet, quiz, PPT, sketch notes, homework)  
- Week / unit planning  
- Content library of approved artefacts  
- Source ingest (PDF, image, YouTube, website, handwritten) as *inputs to intent*  

**Loop role:** Prepare → handoff to Teach.

---

### Teach

**Job:** Support live delivery and in-period noticing.

**Contains:**

- Today’s approved kit for the current period  
- Alternate explanations / examples (teacher-facing)  
- Quick Observe tools (exit check launch, confusion capture)  
- Cover / lost-period packs  
- Class roster context for the live period  

**Loop role:** Teach + Observe.

---

### Assess

**Job:** Create, conduct, evaluate, and understand evidence.

**Contains:**

- Assessment creation (including from intent)  
- Assign / share / attempt flows  
- Evaluation assist + marks confirmation  
- Concept heatmaps and weak-student lists (Analyze)  
- Exam / unit test cycles  

**Loop role:** Assess + Analyze.

---

### Improve

**Job:** Act on insight and compound teacher/school learning.

**Contains:**

- Remediation plans and groups  
- Re-teach outlines  
- Pacing adjustments after disruption  
- PTM briefs, remark drafts, approved parent follow-ups  
- Teacher Memory preferences (visible, editable)  
- Handover / next-cycle Prepare suggestions  

**Loop role:** Improve → Prepare Again.

---

### AI Assistant

**Job:** Conversational / on-demand help that still respects the OS.

**Contains:**

- Ask in teacher language (“explain this doubt for Grade 7”)  
- Shortcut to start or refine a Teaching Intent  
- Never a bypass of approval for student/parent delivery  
- Always inherits Teacher Memory + School Context  

**Loop role:** Cross-stage; must land work into Prepare / Teach / Assess / Improve — not a parallel product.

---

## Reorganizing existing capabilities

| Existing capability | Teacher OS home |
|---------------------|-----------------|
| Worksheet / quiz / lesson / flashcard generators | Prepare (via Teaching Intent) |
| PDF / image / YouTube / website ingest | Prepare (intent inputs) |
| OpenQuiz / assign / attempts | Assess (conduct) + Teach (quick checks) |
| Scoring / explanations | Assess |
| Student analytics / dashboards | Assess (Analyze) → Improve |
| EduAsk / AI Teacher Assistant | AI Assistant (+ Teach assist) |
| Attendance | Today + Teach (ops) |
| LMS assignments / homework | Prepare (design) + Assess (review) |
| Parent portal / notices | Improve (comms) + Today (urgent) |
| Timetable | Today + School Context substrate |
| Exams / marks ERP | Assess |
| Reports / remarks | Improve |

---

## Substrate (not top-nav, but always on)

These are not sixth/seventh tabs — they power every section:

1. **Teaching Intent** — product ↔ orchestration API  
2. **Teacher Memory** — persistent personalisation  
3. **School Context** — automatic institutional inheritance  
4. **Daily Loop** — Prepare → Teach → Observe → Assess → Analyze → Improve  

---

## Design rule (product, not UI)

If a capability cannot be explained as:

> “In **[Section]**, the teacher does **[Loop stage job]** using **[Intent / Memory / Context]**…”

…it is not ready for the Teacher OS.

---

## Related

- Daily Loop: `DAILY_LOOP.md`  
- Teaching Intent: `TEACHING_INTENT.md`  
- Teacher Memory: `../memory/teacher-memory.md`  
- School Context: `../context/school-context.md`
