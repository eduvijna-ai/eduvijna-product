# EBP-001 — Feature Flags

**ID:** EBP-001-FLAGS  
**Aligned with:** PA-001 `FEATURE_FLAGS.md` · API `feature_flags.py` pattern

---

## 1. Catalogue (Wave 1)

| Flag key | Purpose | Default (prod) | Depends on |
|----------|---------|----------------|------------|
| `teacher_os_enabled` | Master switch for Teacher OS shell/nav entry | `false` | — |
| `today_dashboard_enabled` | Mission + Today Dashboard landing | `false` | `teacher_os_enabled` |
| `review_queue_enabled` | Review Queue UI + pending badge + Mission CTA | `false` | `teacher_os_enabled` |
| `continuous_context_enabled` | Session thread / follow-up refine | `false` | `teacher_os_enabled` |

Optional finer flags (if needed during hardening):

| Flag | Purpose |
|------|---------|
| `teacher_os_legacy_nav_visible` | Keep classic feature nav visible alongside OS |
| `teacher_os_mission_aggregates` | Enable live timetable/PTM counts vs placeholders |

---

## 2. API configuration

Extend existing platform feature flag system:

- Prefer `FEATURE_FLAGS_JSON` override, e.g.

```json
{
  "teacher_os_enabled": true,
  "today_dashboard_enabled": true,
  "review_queue_enabled": true,
  "continuous_context_enabled": true
}
```

- Expose resolved flags on `GET /health/meta` (or dedicated flags endpoint if already patterned).

---

## 3. Web configuration

- `VITE_TEACHER_OS_ENABLED` (and optional child envs) **or**  
- Fetch `/health/meta` and derive UI gates (preferred for single source of truth).

File suggestion: `Quiz-React/src/config/teacherOsFeature.ts` (mirror `chatFeature.ts`).

---

## 4. Rollout stages

| Stage | Flag state | Audience |
|-------|------------|----------|
| Preview | all true on Preview env | Internal + invited |
| School Pilot | true for pilot school tenants | Pilot schools |
| GA | true default for entitled teacher roles | All entitled |
| Rollback | all false | Everyone |

Tenant-aware targeting (if available): evaluate school_id allowlist in API flag resolver — **only if existing pattern supports it**; otherwise env-per-deploy for Pilot.

---

## 5. Behaviour matrix

| `teacher_os_enabled` | Child flags | Teacher experience |
|----------------------|-------------|--------------------|
| false | * | Classic EduVijna (HomePage, legacy/Platform AI nav) |
| true | dashboard false | Shell/nav may show; landing stays classic |
| true | dashboard true, queue false | Mission without Review CTA / stub message |
| true | dashboard + queue true | Full Wave 1 Mission → Queue loop |
| true | + context true | Follow-up refine in session |

---

## 6. Engineering rules

1. New Teacher OS code paths **must** check flags.  
2. Defaults **false** in production until Pilot/GA decision.  
3. PRs include flag documentation in description.  
4. E2E covers flag off and flag on.  
5. No “half-shipped” Teacher OS without `teacher_os_enabled` gate.

---

## 7. Mapping to PA flags

| PA name | EBP-001 key |
|---------|-------------|
| Teacher OS Preview / shell | `teacher_os_enabled` |
| Today / Mission | `today_dashboard_enabled` |
| Review Queue | `review_queue_enabled` |
| Continuous Context | `continuous_context_enabled` |
