# AI Opportunity Matrix

**ID:** OPP-AI-TEACHER-001  
**Status:** Draft — TLM-001  
**Rule:** Opportunities describe *value*, not prompts, models, or architecture.

---

## Matrix legend

| Column | Meaning |
|--------|---------|
| Teacher Problem | Lived problem in teacher language |
| Current Workflow | What she does today |
| AI Solution | Assistive outcome (teacher still decides) |
| Expected Time Saved | Directional |
| Student Impact | Learning / experience effect |
| Implementation Complexity | Low / Medium / High / Very High *(product+tech relative)* |

Complexity is a **product sequencing signal**, not an engineering estimate.

---

## Opportunity matrix

| ID | Teacher Problem | Current Workflow | AI Solution | Expected Time Saved | Student Impact | Implementation Complexity |
|----|-----------------|------------------|-------------|---------------------|----------------|----------------------------|
| AO-01 | Preparing tomorrow’s lesson takes hours | Textbook + memory + Word + YouTube hunt | Generate reviewable lesson kit (objectives, arc, examples, checks, homework) from board/grade/chapter | 60–100 min/lesson | Clearer, more consistent classes | Medium |
| AO-02 | Making worksheets is repetitive | Type questions / copy guides | Worksheet generator with answer key + difficulty control | 40–90 min/worksheet | More practice, better aligned | **Low–Medium** (exists in EduVijna) |
| AO-03 | Creating quizzes/tests is slow | Manual MCQs / old papers | Assessment generator from topic or source docs; section variants | 45–120 min/test | Fairer, more frequent formative checks | **Low–Medium** (core strength) |
| AO-04 | Has notes/PDF/video but must rebuild questions | Retype from sources | Ingest PDF/image/YouTube/website/handwritten → draft assessment | 30–90 min/source | Faster reuse of good content | **Low–Medium** (exists) |
| AO-05 | Needs lesson plans for compliance & teaching | Dual documents | Lesson plan draft aligned to actual teaching intent | 30–60 min/plan | Indirect — better structured teaching | Medium (partially exists) |
| AO-06 | Flashcards / revision aids take time | Manual cards | Flashcard generation for revision weeks | 20–40 min/set | Better recall practice | Low–Medium (partially exists) |
| AO-07 | No time to make quality slides | Sparse PPTs or none | Presentation outline + slide draft for teacher edit *(gap today)* | 40–80 min/deck | Better visual lessons when needed | Medium–High |
| AO-08 | Can’t see who is weak until too late | Mental notes / end-term averages | Concept-level analytics after attempts; weak-student lists | 1–2 hrs/week analysis | Earlier remediation | Medium (analytics exist; action loop partial) |
| AO-09 | Evaluation consumes evenings | Manual marking stacks | Auto-score objective; draft feedback for short answers; teacher confirm | 3–8 hrs/test cycle | Faster feedback | High |
| AO-10 | Remediation is ad hoc | Random extra worksheets | Group students by weak concepts; suggest 1-week remediation pack | 1–3 hrs/week | Targeted improvement | Medium–High |
| AO-11 | Parent messages eat nights | Type WhatsApp each time | Draft factual, tone-safe, multilingual messages for approval | 1–3 hrs/week | Parents better informed; less conflict | Medium |
| AO-12 | PTM talks lack evidence packs | Flip marks night before | Per-student briefing cards | 3–6 hrs/PTM | Better guidance to families | Medium |
| AO-13 | Report remarks are copy-paste | Remark banks | Evidence-based remark drafts | 2–5 hrs/term | More meaningful reports | Medium |
| AO-14 | Exit tickets rarely used | Skip or oral only | Instant 3–5 question checks + live confusion signal | 10–20 min/day setup replaced by seconds | Immediate clarity | Medium |
| AO-15 | Lost periods destroy pacing | Manual rewrite of plan | Re-pace remaining week after disruption | 30–60 min/incident | Less syllabus panic | High |
| AO-16 | New joiner level unknown | Observe for weeks | Short diagnostic + bridge kit | 1–2 hrs/student | Faster catch-up | Medium |
| AO-17 | Doubts need alternate explanations | Improvised re-teach | Teacher-facing explanation assistant with level variants | 15–30 min/day | Fewer stuck students | Medium (EduAsk-like) |
| AO-18 | Homework not differentiated | Same textbook sums | Differentiated practice from lesson objectives | 20–40 min/day | Right challenge level | Medium–High |
| AO-19 | Compliance docs ≠ real teaching | Retro-fill diaries | Generate inspection views from teaching activity | 1–3 hrs/month | Indirect | High |
| AO-20 | Generic AI content not trusted | Verify everything manually | School-aware, board-aware, explainable outputs with sources/rationale | Saves verification time; unlocks adoption | Safer content in class | High (platform principle) |
| AO-21 | Parallel sections need fair variants | Manual rewrite | Difficulty-matched paper variants | 30–60 min/test | Fairness across sections | Medium |
| AO-22 | Holiday packs are generic | Photocopy busywork | Differentiated holiday plan + parent instructions | 2–4 hrs/break | Continuity without conflict | Medium |
| AO-23 | Can’t turn results into next lesson | Start next chapter anyway | “Teach next” suggestions from gap analysis | 30–60 min/week | Closes loop | Medium–High |
| AO-24 | Study materials scattered | Pendrive / WhatsApp files | Organised class content library from generated+approved artefacts | 1–2 hrs/week hunting | Students find materials | Medium |
| AO-25 | Thinks in generators, not goals | Opens worksheet/quiz/PPT tools separately | **Teaching Intent** → Prepare Tomorrow kit (plan, worksheet, quiz, PPT, sketch notes, homework) | 60–120 min/kit vs tool-hopping | Coherent learning sequence | High |
| AO-26 | AI resets every session | Re-enters board, language, style | **Teacher Memory** persistent profile + learn-from-edits | 10–20 min/day + trust | Kits match how she teaches | Medium–High |
| AO-27 | Re-types school facts every generate | Manual board/class/policy fields | **School Context** auto-inherit (school, calendar, timetable, curriculum, assessment policy, branding, language, ERP) | 5–15 min/request + fewer errors | Correct, policy-fit materials | High |
| AO-28 | Features don’t compound | Dead-end artefacts | **Daily Loop**: Prepare→Teach→Observe→Assess→Analyze→Improve | Multiplies value of all AOs | Continuous student improvement | Medium (IA) / High (full) |
| AO-29 | No sketch-note style materials | Skip or hand-draw | Sketch notes as intent artefact | 20–40 min | Better visual revision | Medium |
| AO-30 | No Teacher OS mental model | Scattered ERP + AI surfaces | Reorganize into Today / Prepare / Teach / Assess / Improve / AI Assistant | Adoption + findability | Help in the moment | Medium |

---

## Value × complexity view (sequencing)

### Wave 0 — Foundations (mandatory before scale)

AO-25 Teaching Intent · AO-26 Teacher Memory · AO-27 School Context · AO-28 Daily Loop · AO-30 Teacher OS

*Without these, generators remain a menu and AI remains a first-time assistant.*

### Wave A — Strengthen & unify what already creates trust

AO-02, AO-03, AO-04, AO-06, AO-08 (insight), AO-17, AO-20 (explainability)

*Bind existing assessment/worksheet/ingestion muscles under Intent + Context + Memory.*

### Wave B — Close the Daily Loop

AO-01, AO-05, AO-10, AO-14, AO-18, AO-23, AO-29

*Prepare → Teach → Observe → Assess → Analyze → Improve → Prepare Again.*

### Wave C — Communication & reporting relief

AO-11, AO-12, AO-13, AO-24

*Hours back + relationship quality. Always human-approve before send.*

### Wave D — Harder differentiation & operations intelligence

AO-07, AO-09, AO-15, AO-16, AO-19, AO-21, AO-22

*High impact; higher complexity or change management.*

---

## Non-negotiable constraints on all AI opportunities

1. Teacher approval before student/parent delivery  
2. Explainability of outputs  
3. School Context + Teacher Memory inherited on every request  
4. Privacy by design for student data  
5. Prefer time saved this week over speculative autonomy  
6. Features must map to a Daily Loop stage  

---

## Mapping to principles

| Principle | Most relevant AOs |
|-----------|-------------------|
| Teacher First | All; especially AO-01–04, 09, 11 |
| AI Assists, Teacher Decides | AO-09, 11, 12, 13 |
| One Intent, Many AI Services | AO-25, AO-01, 10, 23 |
| Minimize Teacher Workload | AO-03, 09, 11, 26, 27 |
| Explain Every AI Output | AO-20 |
| Human Approval Before Student Delivery | AO-02, 03, 11, 18 |
| Save Time Daily | AO-01, 02, 03, 14, 25 |
| Continuous Improvement / Teacher Memory | AO-26, 28 |
| School-Aware AI | AO-27, 01, 15, 20 |
| Daily Loop Is the Product | AO-28, 30 |

---

## Related

- JTBD: `../jobs-to-be-done/teacher-jtbd.md`  
- Capabilities: `../capability-mapping/teacher-capabilities.md`  
- Teaching Intent: `../vision/TEACHING_INTENT.md`  
- Teacher Memory: `../memory/teacher-memory.md`  
- School Context: `../context/school-context.md`  
- Daily Loop: `../vision/DAILY_LOOP.md`
