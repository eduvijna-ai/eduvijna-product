# Daily Learning Loop

**ID:** PA-LOOP-001  
**Status:** Draft — PA-001  
**Central mental model of Teacher OS**

---

## The loop

```text
Prepare
   ↓
Teach
   ↓
Observe
   ↓
Assess
   ↓
Analyze
   ↓
Improve
   ↓
Prepare Again
```

Every Teacher OS feature must declare its **primary loop stage** and its **handoff**.

---

## Stage contracts

| Stage | Teacher outcome | Primary nav | Handoff to |
|-------|-----------------|-------------|------------|
| Prepare | Approved kit ready | Prepare | Teach |
| Teach | Period delivered with materials | Teach | Observe |
| Observe | Know who/what is unclear *now* | Teach (Observe screens) | Assess / Improve |
| Assess | Fair evidence collected & scored | Assess | Analyze |
| Analyze | Know concepts/students to act on | Assess | Improve |
| Improve | Next action approved (remediate, message, pace) | Improve | Prepare Again |

---

## Capability → Loop map

### Prepare

| Capability | Fit | Gap |
|------------|-----|-----|
| Teaching Intent / Prepare Tomorrow | Core | New |
| Lesson plan | Service | Improve |
| Worksheet | Service | Reuse |
| Quiz creation | Service | Reuse |
| PPT | Service | Missing |
| Sketch notes | Service | Missing |
| Homework design | Service | Improve |
| Flashcards | Service | Reuse |
| Source ingest | Input | Reuse |
| Week / year plan | Support | Missing / New |
| Answer key / objectives | Kit parts | Reuse / Improve |

### Teach

| Capability | Fit | Gap |
|------------|-----|-----|
| Approved kit playback | Core | Partial |
| Alternate explanations (EduAsk-like) | Support | Improve |
| Cover / lost-period pack | Support | Missing |
| Timetable / roster | Ops | Reuse |

### Observe

| Capability | Fit | Gap |
|------------|-----|-----|
| Exit ticket / micro-check | Core | Improve speed |
| Live confusion flags | Core | Missing |
| Attendance presence | Signal | Ops reuse |

### Assess

| Capability | Fit | Gap |
|------------|-----|-----|
| Conduct / OpenQuiz / share | Core | Reuse |
| Auto-score objective | Core | Improve |
| Subjective scoring assist | Support | Partial |
| Marks entry ERP | Ops | Bind |
| Formal unit/exam papers | Core | Reuse |

### Analyze

| Capability | Fit | Gap |
|------------|-----|-----|
| Student analytics / heatmaps | Core | Improve actionability |
| Weak-student lists | Core | Improve |
| Section comparison | Support | Partial |

### Improve

| Capability | Fit | Gap |
|------------|-----|-----|
| Remediation planner | Core | Missing |
| Parent message drafts | Core | Missing |
| PTM briefs | Core | Missing |
| Report remarks | Support | Partial |
| Pacing after disruption | Support | Missing |
| Teacher Memory write-back | Core | Missing |
| Prepare Again suggestions | Core | New |

---

## Missing capabilities (loop completeness)

1. Unified Teaching Intent + kit object  
2. Observe confusion capture  
3. Remediation orchestration  
4. Memory write-back from Improve  
5. PPT + sketch notes  
6. Calendar-aware re-pacing  
7. PTM / parent draft intents as first-class  

Without these, the loop breaks into disconnected generators (the failure mode TLM-001 rejected).

---

## Example pass (product story)

**Photosynthesis · 7-B**

1. **Prepare** — Intent Prepare Tomorrow → kit approved  
2. **Teach** — lesson + worksheet in period  
3. **Observe** — exit check: 12 miss chlorophyll role  
4. **Assess** — short quiz next day confirms  
5. **Analyze** — heatmap isolates concept + names  
6. **Improve** — remediation Intent approved; Memory notes diagram-first  
7. **Prepare Again** — next kit biased to diagrams + chlorophyll practice  

---

## Related

- TLM: `../../vision/DAILY_LOOP.md`  
- Nav: `NAVIGATION_MODEL.md`
