# Information Architecture

**ID:** PA-IA-001  
**Status:** Draft — PA-001  
**Outcome focus:** Teacher jobs — not generators

---

## Design rule

Organise Teacher OS around **outcomes in the Daily Learning Loop**.

Generators (worksheet, quiz, PPT, lesson plan, etc.) are **capabilities**, not top-level destinations.

---

## Top-level destinations

| Nav / surface | Outcome for the teacher |
|---------------|-------------------------|
| **Today's Mission** (login landing) | Know today's load; one CTA to Review |
| **Today** | Work the full school-day schedule |
| **Prepare** | Turn Teaching Intent into orchestrated drafts |
| **Teach** | Deliver the period and observe understanding live |
| **Assess** | Create, conduct, evaluate, and analyse evidence |
| **Improve** | Act on insight; remediate; communicate; compound memory |
| **Review Queue** (signature) | Approve all AI outputs in one place |
| **Library** | Find and reuse approved artefacts, kits, and sources |
| **AI Assistant** | Ask in natural language; lands in Intent + Continuous Context |
| **Settings** | Control Memory, preferences, notifications, and account |

---

## IA layers

```text
Layer A — Mission + Navigation (outcomes)
Layer B — Teaching Intent + Continuous Context (thread)
Layer C — Capability services (worksheet, quiz, lesson, PPT, …)
Layer D — Substrate (Teacher Memory + School Context + ERP facts)
Layer E — Review Queue + Lifecycle (Draft → Review → Approve → Publish → Archive)
```

Teachers live in A, B, and E.  
C is invoked by orchestration.  
D is invisible unless editing Settings / Memory.  

---

## Mapping existing capabilities into IA (no duplicates)

| Existing capability | Primary home | Notes |
|---------------------|--------------|-------|
| Worksheet generator | Prepare → Review Queue | Not a top nav |
| Quiz / assessment generator | Prepare/Assess → Review Queue | Conduct lives in Assess |
| Lesson plan | Prepare → Review Queue | |
| Flashcards | Prepare → Review Queue / Library | |
| PDF / image / YouTube / website / handwritten ingest | Prepare (intent inputs) | |
| OpenQuiz / share / attempts | Assess (conduct); Teach (exit check) | After Approve |
| Scoring / explanations | Assess | |
| Student analytics / heatmaps | Assess (Analyze) → Improve | |
| EduAsk / AI Teacher Assistant | AI Assistant (+ Teach assist) | Continuous Context aware |
| LMS assignments / homework | Prepare → Queue · Assess (review) | |
| Attendance | Today / Teach | Ops |
| Timetable | Today's Mission counts + Today | |
| Notices | Today | |
| Parent communications / PTM | Improve → Review Queue | |
| Exams / marks ERP | Assess | |
| Reports / remarks | Improve → Review Queue | |
| Study materials | Library | |
| Quotas / account | Settings | |
| School admin ERP modules (fees, HR, transport…) | **Out of Teacher OS** | Boundary |

---

## Anti-patterns forbidden by this IA

1. Login landing that is only a sidebar of destinations  
2. Top-level “Generators” or “AI Tools” hub that bypasses Intent  
3. Downloading AI files one-by-one as the primary approval path  
4. Follow-ups that forget Grade/topic mid-kit (no Continuous Context)  
5. Duplicate “Create Quiz” in both Prepare and Assess as separate products  
6. Analytics orphaned from Improve actions  
7. Parent messaging outside Review Queue approval  
8. Settings used as a dumping ground for features  

---

## Related

- `TODAYS_MISSION.md` · `CONTINUOUS_CONTEXT.md` · `REVIEW_QUEUE.md`  
- `NAVIGATION_MODEL.md`  
- `SCREEN_HIERARCHY.md`  
- `FEATURE_BOUNDARIES.md`
