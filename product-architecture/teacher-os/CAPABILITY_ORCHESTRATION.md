# Capability Orchestration

**ID:** PA-CAP-ORCH-001  
**Status:** Draft — PA-001  
**Reuse existing EduVijna capabilities; do not duplicate**

---

## Pattern

```text
Intent
  ↓
Capabilities (services)
  ↓
Kit artefacts
```

---

## Intent → capability maps

### Prepare Tomorrow

| Capability service | Artefact produced | Existing? |
|--------------------|-------------------|-----------|
| Learning objectives composer | Learning objectives | Improve / derive from curriculum |
| Lesson plan generation | Lesson plan | Partial — reuse |
| Worksheet generator | Worksheet | **Reuse** |
| Assessment / quiz generator | Quiz / exit check | **Reuse** |
| PPT / slides service | PPT | **Missing — new service** |
| Sketch notes service | Sketch notes | **Missing — new service** |
| Homework designer | Homework | Partial — reuse LMS + generate |
| Answer key / explanations | Answer key | **Reuse** (worksheet/quiz explain) |
| Source ingest (optional) | Grounding | **Reuse** PDF/image/YT/web/handwritten |

### Prepare Exam Week

| Capability | Artefact | Existing? |
|------------|----------|-----------|
| Exam/assessment generator | Practice papers | **Reuse** |
| Variant generator | Section variants | Partial |
| Flashcards | Revision cards | **Reuse** |
| Revision planner | Day plan | New/partial |
| Answer key | Keys | **Reuse** |

### Create Remediation

| Capability | Artefact | Existing? |
|------------|----------|-----------|
| Analytics weak-concept select | Grouping input | Partial — reuse analytics |
| Differentiated practice generate | Practice sets | New orchestration on generators |
| Mini lesson outline | Re-teach | Lesson plan reuse |
| Short check quiz | Check | **Reuse** quiz |
| Parent note draft | Message | New |

### Review Class

| Capability | Artefact | Existing? |
|------------|----------|-----------|
| Analytics narrative | Class review | Partial |
| Attendance + homework patterns | Evidence | ERP reuse |
| Action list | Improve queue | New |
| PTM bullets | Brief seeds | New |

### Plan Revision

| Capability | Artefact | Existing? |
|------------|----------|-----------|
| Week planner | Revision calendar | New |
| Mixed practice | Papers/worksheets | **Reuse** generators |
| Sketch notes | Summaries | New service |

### Communicate Parents

| Capability | Artefact | Existing? |
|------------|----------|-----------|
| Message drafter | Draft | New |
| Multilingual render | Localized text | Partial |
| Evidence bullets | Facts from ERP/analytics | Reuse data |

### Recover Lost Period

| Capability | Artefact | Existing? |
|------------|----------|-----------|
| Compact activity pack | Activity + mini-check | New orchestration on existing generators |

### Create Assessment

| Capability | Artefact | Existing? |
|------------|----------|-----------|
| Quiz / exam assessment | Paper | **Reuse** |
| Ingest to questions | From sources | **Reuse** |
| Answer key | Key | **Reuse** |

### Ingest to Assets

| Capability | Artefact | Existing? |
|------------|----------|-----------|
| Document/image/YT/web/handwritten pipelines | Quiz/worksheet/summary | **Reuse** |

---

## Reuse mandate

| Do | Do not |
|----|--------|
| Call Worksheet Generator inside Prepare Tomorrow | Build a second worksheet product in Teach |
| Use OpenQuiz for Observe exit checks and Assess conduct | Fork a separate “exit ticket app” |
| Use analytics for Analyze → Remediation | Build vanity dashboards without Improve handoff |
| Place EduAsk in AI Assistant / Teach explain | Duplicate Q&A in every section |

---

## Kit completeness checklist (Prepare Tomorrow)

- [ ] Learning objectives  
- [ ] Lesson plan  
- [ ] Worksheet  
- [ ] Quiz / exit check  
- [ ] PPT (when flag on)  
- [ ] Sketch notes (when flag on)  
- [ ] Homework  
- [ ] Answer key  

Teacher may disable optional rows before Generate.

---

## Related

- TLM capability map: `../../capability-mapping/teacher-capabilities.md`  
- `TEACHING_INTENT_MODEL.md`
