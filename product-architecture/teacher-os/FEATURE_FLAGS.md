# Feature Flags (Rollout Strategy)

**ID:** PA-FLAGS-001  
**Status:** Draft — PA-001  
**No implementation — product rollout model only**

---

## Stages

```text
Teacher OS Preview
        ↓
School Pilot
        ↓
General Availability
        ↓
Legacy fallback / Migration complete
```

---

## Flag cohorts

| Stage | Who | Product behaviour |
|-------|-----|-------------------|
| **Preview** | Internal + invited power teachers | Teacher OS nav visible; Intent Prepare Tomorrow; legacy generators still reachable via Library/Advanced |
| **School Pilot** | Whole pilot school(s) | Default landing = Today; Intent-first Prepare; Memory onboarding; School Context bind required |
| **General Availability** | All entitled schools | Teacher OS is default teacher experience |
| **Legacy fallback** | Entitled during migration | Old generator entry points available; dual-run with clear “classic” label |
| **Migration complete** | Flag off | Classic generator top-level removed; capabilities only via Intent/Library |

---

## Capability flags (examples)

| Flag | Purpose |
|------|---------|
| `teacher_os_shell` | New navigation chrome |
| `todays_mission` | Mission-first login briefing |
| `continuous_context` | Session/Intent thread |
| `review_queue` | Signature approval queue |
| `teaching_intent_prepare_tomorrow` | Flagship intent |
| `teacher_memory_v1` | Memory profile |
| `school_context_bind` | Auto-inherit context |
| `kit_ppt` | PPT in kit |
| `kit_sketch_notes` | Sketch notes in kit |
| `observe_exit_check` | Teach Observe |
| `improve_remediation` | Remediation intent |
| `improve_parent_drafts` | Parent message drafts |
| `legacy_generator_nav` | Show classic tools during migration |

---

## Migration principles

1. **No big-bang** without pilot evidence on hours saved + approval rate  
2. **Reuse capabilities** — flags change *surface*, not underlying worksheet/quiz value  
3. **Teacher can find old path** until Migration complete  
4. **School admin entitlements** gate Pilot/GA  
5. **Rollback** = disable `teacher_os_shell` → classic surfaces restore without data loss of approved artefacts  

---

## Success gates to advance stage

| From → To | Gate |
|-----------|------|
| Preview → Pilot | Light-edit approval rate healthy; no silent-publish incidents |
| Pilot → GA | Weekly hours saved signal; ≥60% teacher activation in pilot schools |
| GA → Legacy off | Support tickets stable; Library+Intent cover prior generator jobs |

---

## Related

- `ROADMAP.md`  
- `SUCCESS_METRICS.md`
