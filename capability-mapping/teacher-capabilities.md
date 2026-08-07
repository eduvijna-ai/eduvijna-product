# Teacher Capability Mapping

**ID:** CAP-TEACHER-001  
**Status:** Draft — TLM-001 (Amended: Teaching Intent, Memory, School Context, Daily Loop)  
**Role:** Product backlog signal (not engineering backlog)

---

## Purpose

Map teacher capabilities across three layers:

1. **Product abstractions** — Teaching Intent, Teacher Memory, School Context, Daily Loop / Teacher OS  
2. **Loop-stage activities** — Prepare → Teach → Observe → Assess → Analyze → Improve  
3. **Artefact services** — worksheet, quiz, PPT, etc. (orchestrated *under* intent, not as the product surface)

This document becomes the **product backlog input** for prioritisation after Product Architecture Review.

---

## Gap legend

| Gap | Meaning |
|-----|---------|
| None | Capability exists and fits well enough to build upon |
| Improve | Exists but incomplete for daily habit / quality / integration |
| Partial | Related capability exists; activity not fully covered |
| Missing | No meaningful capability evidenced |
| Ops | Primarily workflow/ERP integration; light or no AI required |
| New | Strategic new capability class |

---

## Layer 0 — Product abstractions (mandatory substrate)

| Capability | Existing EduVijna Capability | Gap | Teacher OS / Loop |
|------------|------------------------------|-----|-------------------|
| **Teaching Intent** as product↔orchestration API | Separate generators only | **Missing / New** | Prepare (flagship) |
| **Prepare Tomorrow** intent → multi-artefact kit | — | **Missing / New** | Prepare |
| Intent → Lesson Plan | Lesson plan generation | Partial → Improve | Prepare |
| Intent → Worksheet | Worksheet Generator | None → Improve | Prepare |
| Intent → Quiz / exit check | Assessment / quiz generators | None → Improve | Prepare / Teach |
| Intent → PPT / slides | — | **Missing / New** | Prepare |
| Intent → Sketch notes | — | **Missing / New** | Prepare |
| Intent → Homework | LMS assignments + generators | Partial → Improve | Prepare |
| **Teacher Memory** (persistent profile) | Accounts / quotas; not pedagogical memory | **Missing / New** | Improve ↔ all stages |
| Memory: language, board, subjects, grades | Partial user/school fields | Improve → New profile | Substrate |
| Memory: difficulty, worksheet style, Bloom prefs | — | **Missing / New** | Substrate |
| Memory: learn from teacher edits | — | **Missing / New** | Improve |
| Memory: teacher-visible controls | — | **Missing / New** | Improve |
| **School Context** auto-inherit on every request | ERP modules exist; not unified AI inheritance | **Missing / New** | Substrate |
| Inherit school + calendar + timetable | ERP timetable / holidays | Improve → bind | Today / Prepare |
| Inherit curriculum + assessment policy | Partial board alignment in generators | **Improve → first-class** | Prepare / Assess |
| Inherit branding + language + ERP roster/exams/LMS | Partial | Improve | All |
| **Daily Loop** as product mental model | Implicit in journeys only | **New** (product IA) | Entire OS |
| **Teacher OS** IA: Today / Prepare / Teach / Assess / Improve / AI Assistant | Feature sprawl across surfaces | **New** (reorganize) | Navigation |

```text
Teaching Intent
      ↓
Prepare Tomorrow
      ↓
Lesson Plan · Worksheet · Quiz · PPT · Sketch Notes · Homework
```

---

## Layer 1 — Capabilities by Daily Loop stage

### Prepare

| Activity | Existing EduVijna Capability | Gap | OS section |
|----------|------------------------------|-----|------------|
| Create worksheet (service) | Worksheet Generator | None → Improve | Prepare |
| Create quiz / MCQ (service) | AI Quiz / Assessment Generator | None → Improve | Prepare |
| Competitive exam assessment | Exam assessment generation | Improve | Prepare / Assess |
| Generate from PDF / document | Document quiz / PDF extraction | Improve | Prepare |
| Generate from image / handwritten | Image / handwritten flows | Improve | Prepare |
| Generate from YouTube / website | YouTube / website quiz | Improve | Prepare |
| Create lesson plan (service) | Lesson plan generation | Partial → Improve | Prepare |
| Create flashcards | Flashcard generation | Improve | Prepare |
| Prepare PPT / slide deck | — | **Missing / New** | Prepare |
| Sketch notes | — | **Missing / New** | Prepare |
| Plan week from timetable + calendar | Timetable ERP; planning AI limited | **Missing / New** | Prepare |
| Plan academic year living syllabus | Academic setup ERP | **Missing / New** | Prepare |
| Content library of approved kits | Study materials / LMS fragments | Partial | Prepare |

### Teach

| Activity | Existing EduVijna Capability | Gap | OS section |
|----------|------------------------------|-----|------------|
| Deliver period with approved kit | Content + share links | Partial | Teach |
| Alternate explanations / examples | EduAsk / AI teacher assistant | Partial → Improve | Teach / AI Assistant |
| Cover / lost-period activity pack | — | **Missing / New** | Teach |
| Class roster / timetable in-period | ERP Timetable | Ops → Improve | Today / Teach |

### Observe

| Activity | Existing EduVijna Capability | Gap | OS section |
|----------|------------------------------|-----|------------|
| Quick formative / exit ticket | Quiz flows | Partial → Improve (in-period speed) | Teach |
| Live confusion / weak-signal capture | — | **Missing / New** | Teach |
| Attendance as presence signal | ERP Attendance | Ops → Improve | Today / Teach |
| Pastoral private cues | — | **Missing / New** | Teach / Improve |

### Assess

| Activity | Existing EduVijna Capability | Gap | OS section |
|----------|------------------------------|-----|------------|
| Create unit test paper | Assessment generator | Improve | Assess |
| Parallel-section variants | Re-gen only | Partial | Assess |
| Share / conduct quiz | OpenQuiz / share / notifications | Improve | Assess |
| Auto-score objective | Quiz attempt scoring | Improve | Assess |
| Assist subjective scoring | Grading assist signals | Partial → Improve | Assess |
| Answer key & explanations | Worksheet/quiz explanations | Improve | Assess |
| Marks entry | ERP Exams | Ops → Improve AI bind | Assess |
| Assign / review homework | LMS assignments | Improve | Assess |
| Differentiate homework | — | **Missing / New** | Prepare → Assess |

### Analyze

| Activity | Existing EduVijna Capability | Gap | OS section |
|----------|------------------------------|-----|------------|
| Class results analysis | Student AI analytics + dashboards | Partial → Improve | Assess |
| Concept heatmap / weak students | Analytics foundations | Improve | Assess |
| Department coverage narrative | Analytics partial | Partial | Assess |

### Improve

| Activity | Existing EduVijna Capability | Gap | OS section |
|----------|------------------------------|-----|------------|
| Suggest remediation plan | Analytics without closed loop | **Missing / New** | Improve |
| Re-pace after disruption | — | **Missing / New** | Improve |
| Parent message drafts (approve) | Parent portal / chat partial | **Missing / New** | Improve |
| PTM briefing cards | PTM scheduling partial | **Missing / New** | Improve |
| Evidence-based report remarks | Report generation partial | Partial → New | Improve |
| Write back to Teacher Memory | — | **Missing / New** | Improve |
| Holiday differentiated packs | — | **Missing / New** | Improve |
| New joiner diagnostic bridge | Admissions ERP admin | Partial → New | Improve |
| Handover pack next teacher | — | **Missing / New** | Improve |
| Publish to students safely | Share after create | Improve (**approval**) | All |

### Ops (support the loop; not the centre)

| Activity | Existing EduVijna Capability | Gap | OS section |
|----------|------------------------------|-----|------------|
| Take / reconcile attendance | ERP Attendance | Ops → Improve | Today |
| Notices | ERP Notices | Ops | Today |
| Invigilation / duty | Exams schedules partial | Ops | Assess |

---

## Example rows (updated)

| Activity | Existing EduVijna Capability | Gap |
|----------|------------------------------|-----|
| Teaching Intent / Prepare Tomorrow | Missing | **New** |
| Create Worksheet | Worksheet Generator | None → Improve (as *service under intent*) |
| Prepare PPT | — | Missing / New |
| Sketch Notes | — | Missing / New |
| Teacher Memory | — | Missing / New |
| School Context inheritance | ERP fragments | Missing as unified layer / New |
| Review Weak Students | Student analytics (partial) | Improve |
| Remediate → Prepare Again | — | Missing / New |

---

## Backlog epics (restructured)

### Epic 0 — Teacher OS Foundations *(new priority)*

- Teaching Intent contract  
- Teacher Memory  
- School Context inheritance  
- Daily Loop IA (Today / Prepare / Teach / Assess / Improve / AI Assistant)  

### Epic 1 — Prepare Tomorrow (flagship intent)

- One intent → lesson plan + worksheet + quiz + PPT + sketch notes + homework  
- Explainability + edit + approve  

### Epic 2 — Observe → Assess → Analyze

- In-period checks, conduct, score assist, heatmaps  

### Epic 3 — Improve → Prepare Again

- Remediation, pacing, memory write-back, PTM/parent drafts  

### Epic 4 — Teaching Ops Integrity

- No dual entry; ERP as context substrate  

---

## Prioritisation starter (amended)

| Rank | Backlog item | Why |
|------|--------------|-----|
| 0 | Teaching Intent + School Context bind + Teacher Memory MVP | Without these, AI stays a tool menu / first-time assistant |
| 1 | Prepare Tomorrow multi-artefact kit | Daily Loop Prepare; principle #3 |
| 2 | Observe + Analyze actionable heatmaps | Closes loop to Improve |
| 3 | Improve remediation + memory write-back | Prepare Again compounds |
| 4 | Explainability + approval ritual everywhere | Trust gate |
| 5 | Parent / PTM drafts | Emotional load |
| 6 | Assisted evaluation | Largest time sink; harder |
| 7 | PPT + sketch notes services | Complete the kit |
| 8 | Year pacing / disruption recovery | Continuity |

---

## Explicit non-backlog (for now)

- Replacing teachers  
- Autonomous parent messaging  
- Surveillance dashboards that increase teacher reporting burden without saving time  
- Generator menus that bypass Teaching Intent as the primary surface  

---

## Related

- `../vision/TEACHING_INTENT.md`  
- `../vision/DAILY_LOOP.md`  
- `../vision/TEACHER_OS.md`  
- `../memory/teacher-memory.md`  
- `../context/school-context.md`  
- `../opportunities/ai-opportunities.md`  
- `../metrics/success-metrics.md`
