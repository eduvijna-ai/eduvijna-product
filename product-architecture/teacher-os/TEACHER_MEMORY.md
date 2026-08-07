# Teacher Memory (Product Architecture)

**ID:** PA-MEM-001  
**Status:** Draft — PA-001  
**No storage implementation — profile behaviour only**

---

## Purpose

Ensure AI never behaves like a first-time assistant.

Teacher Memory is a **teacher-owned, visible, editable** profile that shapes every Teaching Intent.

---

## Profile domains

### Identity & assignment

| Field | Example | Source |
|-------|---------|--------|
| Preferred language(s) | English; Telugu for parents | Onboarding + Settings |
| Board | CBSE | School Context + override |
| Subjects | Science | Assignment |
| Grades / sections | 6–8; Class Teacher 7-B | Assignment |
| Medium | English | School Context |

### Pedagogical style

| Field | Example |
|-------|---------|
| Preferred style | Diagram-first; short explanations |
| Bloom’s preference | Understand mid-week; Apply before tests |
| Question patterns | Mixed MCQ+FITB; avoid trick negatives |
| Difficulty bias | Scaffolded core + stretch set |
| Worksheet style | Clean print; 1 diagram; ≤2 pages |
| PPT / sketch preference | Minimal slides; sketch notes on |
| Homework philosophy | Light weekdays |
| Favorite templates | “7-B Science standard kit” |

### Continuity

| Field | Example |
|-------|---------|
| Recent history | Last 20 intents/kits |
| Frequent edits | Deletes trick Qs; adds local analogy |
| Class-specific notes | 7-B needs visuals; 8-A handles abstraction |
| Rejected behaviours | Never invent off-syllabus topics |

### Policy overlays (personal)

| Field | Example |
|-------|---------|
| Communication boundary | No parent messages after 7 PM (preference) |
| Remark tone | Firm-kind; no public ranking language |

---

## How memory improves future interactions

| Moment | Behaviour |
|--------|-----------|
| Intent composer opens | Defaults artefact set, difficulty, language, Bloom mix |
| Orchestration runs | Style applied across lesson/worksheet/quiz consistently |
| Teacher edits kit | System proposes Memory update (“Always prefer diagram-first?”) — teacher confirms |
| Prepare Again | Prior class notes + successful kits bias next draft |
| Parent drafts | Tone/language from Memory + School Context |
| Assistant chat | Resolves shorthand (“same as last photosynthesis kit”) |

---

## Governance (product)

1. Teacher can view all Memory fields  
2. Teacher can edit or clear categories  
3. Inferences require confirmation before becoming durable (or soft-weight until confirmed)  
4. Student PII is not stored as “teacher personality”  
5. Memory never auto-publishes to students/parents  
6. School admin cannot silently overwrite pedagogical style without transparency  

---

## Surfaces

| Surface | Role |
|---------|------|
| Settings → Memory | Full control |
| Improve → Memory insights | Learned patterns + confirm |
| Intent composer | Compact “using your style” chip |
| Kit review | “Matched to your worksheet style” explain |

---

## Success test

After two weeks: *“It already knows how I teach Class 7.”*

---

## Related

- TLM: `../../memory/teacher-memory.md`  
- Settings screens in `SCREEN_HIERARCHY.md`
