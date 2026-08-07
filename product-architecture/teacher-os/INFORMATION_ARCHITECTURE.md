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

| Nav item | Outcome for the teacher |
|----------|-------------------------|
| **Today** | Know what matters *this school day* and continue the right job |
| **Prepare** | Turn Teaching Intent into an approved kit |
| **Teach** | Deliver the period and observe understanding live |
| **Assess** | Create, conduct, evaluate, and analyse evidence |
| **Improve** | Act on insight; remediate; communicate; compound memory |
| **Library** | Find and reuse approved artefacts, kits, and sources |
| **AI Assistant** | Ask in natural language; always lands in an intent or stage |
| **Settings** | Control Memory, preferences, notifications, and account |

---

## IA layers

```text
Layer A — Navigation (outcomes)
Layer B — Teaching Intent (product↔orchestration contract)
Layer C — Capability services (worksheet, quiz, lesson, PPT, …)
Layer D — Substrate (Teacher Memory + School Context + ERP facts)
Layer E — Lifecycle (Draft → Review → Approve → Publish → Archive)
```

Teachers live in A and B.  
C is invoked by orchestration.  
D is invisible unless editing Settings / Memory.  
E is visible as status on every artefact.

---

## Mapping existing capabilities into IA (no duplicates)

| Existing capability | Primary home | Notes |
|---------------------|--------------|-------|
| Worksheet generator | Prepare (via Intent) / Library (reuse) | Not a top nav |
| Quiz / assessment generator | Prepare or Assess (via Intent) | Conduct lives in Assess |
| Lesson plan | Prepare | |
| Flashcards | Prepare / Library | |
| PDF / image / YouTube / website / handwritten ingest | Prepare (intent inputs) | |
| OpenQuiz / share / attempts | Assess (conduct); Teach (exit check) | One capability, two entry contexts |
| Scoring / explanations | Assess | |
| Student analytics / heatmaps | Assess (Analyze) → Improve | |
| EduAsk / AI Teacher Assistant | AI Assistant (+ Teach assist) | |
| LMS assignments / homework | Prepare (design) · Assess (review) | |
| Attendance | Today / Teach | Ops, not AI centre |
| Timetable | Today (+ School Context) | |
| Notices | Today | |
| Parent communications / PTM | Improve | |
| Exams / marks ERP | Assess | |
| Reports / remarks | Improve | |
| Study materials | Library | |
| Quotas / account | Settings | |
| School admin ERP modules (fees, HR, transport…) | **Out of Teacher OS** — Admin / school systems | Boundary |

---

## Anti-patterns forbidden by this IA

1. Top-level “Generators” or “AI Tools” hub that bypasses Intent  
2. Duplicate “Create Quiz” in both Prepare and Assess as separate products  
3. Analytics orphaned from Improve actions  
4. Parent messaging living in chat chaos outside Improve  
5. Settings used as a dumping ground for features  

---

## Related

- `NAVIGATION_MODEL.md`  
- `SCREEN_HIERARCHY.md`  
- `FEATURE_BOUNDARIES.md`
