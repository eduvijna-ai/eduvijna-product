# Product Principles

**Status:** Draft — TLM-001  
**Owner:** EduVijna Product Office  
**Applies to:** All EduVijna teacher-facing product decisions

---

These principles govern how EduVijna creates value for teachers.  
Every feature proposal, AI capability, and release priority must pass these tests.

---

## 1. Teacher First

Start with the teacher's day, not with technology.

If a capability does not reduce teacher burden, improve teaching quality, or deepen student understanding under teacher control — it is not priority.

**Test:** Would a tired teacher on a Monday morning thank us for this?

---

## 2. AI Assists, Teacher Decides

AI prepares. Teachers approve. Students receive only what a teacher has accepted.

Automation never silently publishes to students, parents, or report cards.

**Test:** Can the teacher reject, edit, or regenerate every AI output before it leaves their control?

---

## 3. One Intent, Many AI Services

Teachers express a **Teaching Intent** once — “prepare tomorrow’s Class 7 Science lesson on photosynthesis.”

Teaching Intent is the API between the Teacher OS and the orchestration engine. Behind one intent, many AI services may run (lesson plan, worksheet, quiz, PPT, sketch notes, homework, remediation). The teacher should not manage a zoo of disconnected generators.

**Test:** Does the teacher state a goal, or operate a menu of generators?

See `vision/TEACHING_INTENT.md`.

---

## 4. Minimize Teacher Workload

Every interaction should shrink total weekly hours of non-teaching work.

If a feature creates more configuration, duplicate entry, or parallel tracking, it fails this principle.

**Test:** Net weekly hours saved — not features shipped.

---

## 5. Explain Every AI Output

Teachers must see *why* AI suggested something — source board/syllabus alignment, difficulty rationale, student evidence used, or content assumptions.

Opaque answers destroy trust in schools.

**Test:** Can a teacher defend an AI-assisted decision to a parent or principal?

---

## 6. Human Approval Before Student Delivery

No worksheet, quiz, mark, message, or remedial task reaches a student without teacher (or authorised human) approval — unless the school explicitly configures a controlled exception for a narrow, audited case.

**Default:** human approval required.

---

## 7. Save Time Daily

Value must appear inside a single school day — not only after a long onboarding programme.

Daily time saved is the product’s heartbeat metric.

**Test:** After first successful use, does tomorrow’s preparation take meaningfully less time?

---

## 8. Continuous Improvement

The product learns from teaching patterns, school calendars, board syllabi, and teacher corrections — without trapping teachers in rigid templates.

Teacher edits are gold. They improve future assistance via **Teacher Memory**.

**Test:** Does correcting AI once reduce the chance of the same error next week?

---

## 9. Privacy by Design

Student data, marks, behavioural notes, and parent communications are sensitive by default.

Collect minimum necessary data. Prefer school-scoped tenancy. Never train public models on identifiable school data without explicit institutional consent and governance. Teacher Memory is teacher-visible and teacher-controllable.

**Test:** Would a principal be comfortable explaining our data practice to parents?

---

## 10. School-Aware AI (expanded)

EduVijna AI must automatically inherit **School Context** on every request so teachers never re-enter institutional facts:

- School identity and tenancy  
- Academic calendar  
- Timetable  
- Curriculum (board, grade, subject, chapters)  
- Assessment policy  
- Branding  
- Language / medium  
- Existing ERP context (roster, attendance, exams, LMS, notices)  

Plus classroom reality: class strength, mixed ability, role hierarchy.

Generic global tutoring AI is not enough.

**Test:** Can the teacher name only the topic — and still get an output correct for *this* school *this* week?

See `context/school-context.md`.

---

## 11. Teacher Memory Compounds

The AI must not behave like a first-time assistant on every use.

Persist preferences and learned patterns: language, board, subjects, grades, difficulty, worksheet style, Bloom emphasis, explanation style, and school-policy overlays the teacher actually follows.

**Test:** After two weeks, does Prepare Tomorrow already feel like *her* teaching — without re-profiling?

See `memory/teacher-memory.md`.

---

## 12. Daily Loop Is the Product

The Teacher OS revolves around one continuous cycle:

Prepare → Teach → Observe → Assess → Analyze → Improve → Prepare Again

Every feature must belong to one of these stages (or the Today / AI Assistant hubs that serve them). Dead-end generators without handoff are incomplete.

**Test:** Does this capability clearly strengthen a loop stage and pass work to the next?

See `vision/DAILY_LOOP.md` and `vision/TEACHER_OS.md`.

---

## Operating rules derived from principles

| Rule | Meaning |
|------|---------|
| No dark patterns for AI adoption | Teachers opt into assistance; assistance earns trust |
| Dual entry is failure | Marks, attendance, homework must not be typed twice |
| Offline / low-connectivity empathy | Real schools have uneven networks |
| Language dignity | Support Indian languages where teachers and parents need them |
| Respect professional identity | Teachers are professionals, not content operators |
| Generators are services | Teaching Intent is the product surface; artefact tools are orchestration |
| Context is inherited | School Context + Teacher Memory attach before generation |

---

## Principle conflict resolution

When principles conflict, resolve in this order:

1. Student safety and privacy  
2. Teacher control and approval  
3. Workload reduction  
4. Insight quality  
5. Speed of delivery  

---

## Review use

Product Architecture Review must cite which principles a proposed capability upholds or risks violating.
