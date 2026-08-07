# Success Metrics

**ID:** METRICS-TEACHER-001  
**Status:** Draft — TLM-001  
**Owner:** EduVijna Product Office

---

## Purpose

Define measurable success for teacher value — aligned to `vision/NORTH_STAR.md`.

Metrics below are **product outcome metrics**, not engineering KPIs.

---

## North Star

**Hours returned to teaching per teacher per week.**

Twin trust metric: **% of AI outputs approved with ≤2 edits.**

---

## Metric dictionary

### 1. Teacher preparation time

| Attribute | Definition |
|-----------|------------|
| Statement | Median time for a teacher to produce an approved, period-ready preparation pack |
| Pack includes | Lesson outline + at least one practice/assessment artefact intended for that period |
| Start | Intent stated (topic/chapter selected) |
| End | Teacher marks pack approved for use |
| Unit | Minutes |
| Baseline capture | Diary study / instrumented timing in pilot schools |
| Target direction | ↓ 50%+ vs personal baseline within 1 term of habitual use |
| Guardrail | Approval quality / teacher-rated readiness ≥ baseline |

---

### 2. Assessment creation time

| Attribute | Definition |
|-----------|------------|
| Statement | Median time to create a board-aligned quiz/worksheet ready for teacher review completion |
| End | Teacher completes review (approve or approve-with-edits) |
| Unit | Minutes |
| Target direction | ↓ |
| Guardrail | % rejected for syllabus misalignment stays low and falling |

---

### 3. Weekly hours saved

| Attribute | Definition |
|-----------|------------|
| Statement | Estimated non-teaching academic hours saved per week (prep + assess create + evaluate assist + comms drafts) |
| Methods | Mixed: instrumentation where possible + validated teacher pulse survey |
| Unit | Hours/week |
| Target direction | ↑ saved (aim band: 8–12 hrs/week for active class teachers at maturity) |
| Guardrail | No rise in after-hours parent messaging volume caused by product |

---

### 4. Teacher satisfaction

| Attribute | Definition |
|-----------|------------|
| Statement | Teacher satisfaction / NPS for EduVijna teaching support |
| Cadence | Monthly pulse in active schools; deep dive termly |
| Target direction | ↑ |
| Qualitative companion | “I feel more prepared” agreement rate |

---

### 5. Student engagement

| Attribute | Definition |
|-----------|------------|
| Statement | Completion / attempt rates on teacher-assigned digital practice & assessments |
| Unit | % attempts started; % completed; on-time rate |
| Target direction | ↑ |
| Guardrail | Engagement without gambling-like dark patterns |

---

### 6. Learning follow-through

| Attribute | Definition |
|-----------|------------|
| Statement | % of identified weak concepts with a remediation assignment within 7 days |
| Target direction | ↑ |
| Notes | Requires insight → action loop capability |

---

### 7. Feature adoption

| Attribute | Definition |
|-----------|------------|
| Statement | % licensed teachers active in priority capabilities each week |
| Priority set (initial) | Prepare/generate; Assign/assess; Review insight; Communicate (draft) |
| Healthy adoption | ≥3 days/week for prepare or assess among activated teachers |
| Target direction | ↑ meaningful adoption, not drive-by clicks |

---

### 8. Retention

| Attribute | Definition |
|-----------|------------|
| Teacher | Month-8 retention of monthly active teachers |
| School | Annual renewal; expansion of teacher seats |
| Target direction | ↑ |

---

### 9. School adoption

| Attribute | Definition |
|-----------|------------|
| Statement | % of schools reaching ≥60% teacher activation within 90 days of onboarding |
| Activation | Teacher completes ≥3 approved generations or equivalent core actions |
| Target direction | ↑ |

---

### 10. Trust & control metrics

| Metric | Definition | Direction |
|--------|------------|-----------|
| Approval rate | % AI outputs approved vs discarded | ↑ (with quality) |
| Light-edit rate | % approved with ≤2 edits | ↑ |
| Unauthorised send rate | Student/parent deliveries without approval | → 0 (default policy) |
| Explainability open rate | % generations where rationale viewed in early usage | Monitor (education → decline as trust grows) |

---

## Scorecard (quarterly review)

| Theme | Metrics |
|-------|---------|
| Time | Preparation time, assessment creation time, weekly hours saved |
| Trust | Light-edit rate, unauthorised send rate, TSAT |
| Learning | Student engagement, learning follow-through |
| Growth | Feature adoption, teacher retention, school adoption |

---

## Measurement principles

1. Prefer **approved outcomes** over raw generation counts  
2. Segment by role (class teacher vs subject-only) and connectivity context  
3. Never optimise a metric that increases teacher surveillance burden  
4. Pair every efficiency metric with a quality/trust guardrail  
5. Pilot baselines before declaring targets as commitments  

---

## Leading vs lagging

| Leading | Lagging |
|---------|---------|
| Weekly active prepare/assess days | Term exam outcome shifts |
| Light-edit approval rate | Annual school renewal |
| Remediation within 7 days | Year-end achievement gaps |

---

## Related

- North Star: `../vision/NORTH_STAR.md`  
- Capability map: `../capability-mapping/teacher-capabilities.md`
