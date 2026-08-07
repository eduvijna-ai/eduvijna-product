# School Context

**ID:** MODEL-SCHOOL-CONTEXT-001  
**Status:** Draft — TLM-001 Amendment  
**Owner:** EduVijna Product Office  
**Role:** Expand “School-Aware AI” into automatic institutional inheritance

---

## Principle expansion

**School-Aware AI** is not a slogan.

Every Teaching Intent and AI request should **automatically inherit** school reality so the teacher never re-enters institutional facts.

---

## What every request inherits

| Context layer | Examples | Teacher should re-type? |
|---------------|----------|-------------------------|
| **School** | School identity, campus, tenancy, role permissions | No |
| **Academic calendar** | Terms, holidays, exam windows, PTM dates, events | No |
| **Timetable** | Periods, substitutions, lab/smart-class slots | No |
| **Curriculum** | Board, grade subjects, chapter lists, learning outcomes | No |
| **Assessment policy** | Blueprint norms, grading scheme, internals weight, retake rules | No |
| **Branding** | School name/logo on printables, letter tone, header standards | No |
| **Language** | Medium of instruction; parent communication languages | No (unless personal override in Memory) |
| **Existing ERP context** | Classes, roster, attendance state, exam schedules, LMS assignments, notices | No |

---

## Inheritance model

```text
School Context (institutional truth)
        +
Teacher Memory (personal preferences & learned style)
        +
Teaching Intent (this moment’s goal)
        ↓
Orchestrated AI services
        ↓
Teacher approval
```

If School Context is missing, AI becomes generic.  
If Teacher Memory is missing, AI becomes impersonal.  
If Teaching Intent is missing, AI becomes a tool menu.

All three are required.

---

## Why teachers should not repeat this

Repeating school facts is **cognitive tax** and a **error source**:

- Wrong board version of a chapter  
- Worksheet in the wrong language  
- Test scheduled on a holiday week  
- Difficulty that violates assessment policy  
- Printable without school identification when policy requires it  

School Context makes correctness the default.

---

## ERP as context substrate (not a separate teacher brain)

School ERP modules are not only admin software. For Teacher OS they are **context providers**:

| ERP domain | Feeds School Context for |
|------------|--------------------------|
| Academic setup / SIS | Grades, sections, subjects, roster |
| Timetable | Today + Prepare scheduling |
| Attendance | Observe / pastoral / PTM evidence |
| Exams | Assess policy + schedules |
| LMS | Assignment state |
| Parent portal | Communication channels & PTM |
| Holidays / calendar | Pacing and intent timing |
| Notices | Today interruptions |

Teacher OS must read this context. Teachers must not re-key it into AI forms.

---

## Branding & language

| Need | Behaviour |
|------|-----------|
| Branding | Approved printables/PDFs can carry school identity when policy says so |
| Language | Default to school medium; Memory may prefer bilingual parent drafts |
| Policy tone | Assessment and remarks follow school assessment policy |

---

## Gaps vs today

| Context element | Status signal | Gap |
|-----------------|---------------|-----|
| School tenancy / roster | ERP exists | Improve bind into AI generate |
| Timetable | ERP exists | Improve → Today/Prepare inheritance |
| Academic calendar | Holidays/ERP partial | Improve |
| Curriculum / board alignment | Partial in generators | **Improve → first-class** |
| Assessment policy | Exams ERP partial | **Missing as AI constraint** |
| Branding on artefacts | Unclear / partial | Partial → Improve |
| Language defaults | Partial (multilingual signals) | Improve |
| Full “inherit on every request” | Not evidenced as unified layer | **Missing / New** |

---

## Success test

A teacher opens Prepare Tomorrow, names only the topic, and the kit already matches:

> her school · her board · her class timetable slot · her assessment norms · her language · her branding rules

---

## Related

- Product Principles (School-Aware AI): `../vision/PRODUCT_PRINCIPLES.md`  
- Teacher Memory: `../memory/teacher-memory.md`  
- Teaching Intent: `../vision/TEACHING_INTENT.md`  
- Teacher OS: `../vision/TEACHER_OS.md`
