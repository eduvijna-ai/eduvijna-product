# School Context (Product Architecture)

**ID:** PA-CTX-001  
**Status:** Draft — PA-001  
**Expanded School-Aware AI — behaviour only**

---

## Rule

**Every Teaching Intent and AI-assisted request automatically inherits School Context.**

Teachers must not repeatedly enter institutional facts.

---

## Inherited context set

| Layer | Inherits | Used for |
|-------|----------|----------|
| **School** | Identity, tenancy, campus, roles | Permissions, branding, isolation |
| **Academic year** | Current session, term | Syllabus pacing, reports |
| **Academic calendar** | Holidays, exams, PTM, events | Intent timing, week plan |
| **Timetable** | Periods, rooms, substitutions | Today, Prepare Tomorrow slot |
| **Curriculum** | Board, grade subjects, chapters, outcomes | Alignment, explainability |
| **Assessment policy** | Blueprints, grading scheme, internals | Assessment intents |
| **ERP context** | Roster, attendance, exams schedule, LMS state, notices | Conduct, Analyze, Improve |
| **Branding** | Name, logo, printable headers | Approved printables |
| **Language** | Medium; parent languages | Kits + communication drafts |
| **Policies** | Homework rules, communication norms | Guardrails |

---

## Product behaviour

```text
Teacher: “Prepare tomorrow photosynthesis”
OS attaches: school, 7-B roster, CBSE Science chapter map, tomorrow’s period slot,
             assessment norms, English medium, school header, calendar conflicts
Teacher only confirms topic + artefact toggles
```

If Context is incomplete, OS asks **once** for the missing institutional fact and offers to save into school setup — not into every future form.

---

## Teacher vs school precedence

| Conflict | Resolution |
|----------|------------|
| Memory language vs school medium | Teaching artefacts follow medium; parent drafts may follow Memory bilingual preference |
| Memory difficulty vs assessment policy | Policy caps win; Memory styles within policy |
| Personal template vs branding | Branding required fields always applied on publish/print |

---

## What teachers never re-type

Board · school name · class roster · timetable slot metadata · holiday calendar · grading scheme · logo · default medium · exam windows already in ERP

---

## Surfaces

Context is mostly invisible. Visible only as:

- Chips on Intent (“CBSE · 7-B · Period 3 · English”)  
- Explain panel (“Aligned to Chapter 7 learning outcomes”)  
- Settings read-only “Your school context” summary (edits go to Admin where appropriate)

---

## Related

- TLM: `../../context/school-context.md`  
- Boundaries: Admin owns ERP master data — `FEATURE_BOUNDARIES.md`
