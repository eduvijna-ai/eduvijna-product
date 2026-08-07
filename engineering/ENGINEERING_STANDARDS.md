# Engineering Standards

**ID:** ENG-STD-001  
**Status:** Mandatory before Sprint 0 (EBP-001)  
**Role:** Engineering constitution for EduVijna Teacher OS contributors  
**Applies to:** `Quiz-React` (eduvijna-web) · `eduvijna-api` · future app repos under EduVijna

Not bureaucracy — **consistency as an accelerator** once multiple engineers contribute.

---

## 1. Guiding laws

1. **Vertical-slice first** — User Story → React → API → Tests → Review → Deploy (flagged).  
2. **AI Assists, Teacher Decides** — no student/parent delivery without Artifact approval.  
3. **Everything is an Artifact** — unified lifecycle; generic Review Queue.  
4. **Intent is stateless; Work is stateful** — persist Work/Artifacts, not Intents.  
5. **Reuse before rewrite** — orchestrate existing generators.  
6. **Flags by default** — new Teacher OS behaviour behind feature flags.  
7. **No merge without automated tests** for the slice.

Canonical product decisions: `../product-architecture/teacher-os/ARTIFACT_MODEL.md`, `INTENT_AND_WORK.md`.

---

## 2. Folder conventions

### Web (`Quiz-React`)

```text
src/features/teacher-os/          # Teacher OS feature module
  routes/
  components/
  hooks/
  api/                            # thin clients for teacher-os endpoints
  context/                        # Continuous Context provider
  types/
src/config/teacherOsFeature.ts    # flags
```

- Do **not** dump Teacher OS into unrelated legacy folders.  
- Shared UI primitives stay in existing design/component libraries.  
- Deep-link to `src/features/platform-ai/` for generators — do not fork generators into teacher-os.

### API (`eduvijna-api`)

```text
app/api/v1/…                      # versioned HTTP
app/domain/…                      # lifecycle / artifact rules where owned
app/platform/feature_flags.py     # flags
tests/…                           # mirror package paths
```

- Prefer extending `content` / platform generation over parallel “teacher_os_worksheet” stacks.  
- New Teacher OS aggregate endpoints under `/api/v1/teacher-os/*` only when composition requires it.

---

## 3. Naming conventions

| Kind | Convention | Example |
|------|------------|---------|
| React components | PascalCase | `TodaysMission.tsx`, `ReviewQueuePage.tsx` |
| Hooks | `use` + camelCase | `useContinuousContext`, `useReviewQueue` |
| Feature flags | snake_case keys | `teacher_os_enabled` |
| API paths | kebab-case resources | `/api/v1/teacher-os/mission` |
| Types | PascalCase | `Artifact`, `Work`, `ArtifactLifecycleState` |
| Test files | `*.test.ts(x)` / pytest modules | `review_queue.test.tsx` |
| Telemetry events | domain.action | `artifact.approved`, `mission.viewed` |

Prefer **Artifact / Work / Intent** vocabulary in code comments and public types — avoid new synonyms (`item`, `doc`, `job`) for the same concepts.

---

## 4. Component rules (React)

1. Screens are thin; logic in hooks/services.  
2. No direct student publish from generator components — always route through Artifact approval.  
3. Loading/error/empty states required on Mission, Queue, Dashboard.  
4. Progress indicators for any generate lasting &gt; ~300 ms.  
5. Accessibility: semantic headings, keyboard actions, labelled icon buttons.  
6. Do not add new global CSS frameworks; follow existing Tailwind patterns.  
7. Feature-flag gates at route and nav boundaries.

---

## 5. API versioning

1. Public Teacher OS HTTP under **`/api/v1/`**.  
2. No undocumented breaking changes on v1 without version bump or flag.  
3. Additive fields preferred; deprecate with notice.  
4. Auth: existing JWT `Authorize()` / tenant patterns.  
5. List endpoints support Artifact filters: `lifecycle_state`, `artifact_type`, `work_id`.

---

## 6. Testing standards

| Layer | Tool | Required when |
|-------|------|----------------|
| Unit | Vitest / pytest | Pure logic, flags, mappers, domain transitions |
| Integration | pytest / API+client | generate → Artifact Teacher Review → Approved |
| UI/E2E | Playwright | Mission, nav, Queue happy paths |
| Accessibility | axe/Playwright a11y | New interactive Teacher OS surfaces |
| Regression | Existing packs | Generators, auth, flag-off |

**Merge gate:** slice user-visible behaviour without automated proof = blocked.

Principle tests (block Pilot):

- Generate does not auto-publish  
- Share/assign blocked until Approved  
- Flag off restores classic experience  

---

## 7. Accessibility requirements

1. Mission and Queue pass keyboard-only flows.  
2. Focus visible; CTA contrast sufficient.  
3. Live regions for Queue badge updates where appropriate.  
4. Do not convey state by colour alone.  
5. Landmark structure: main, nav labelled.

---

## 8. Feature flag policy

1. New Teacher OS behaviour requires a flag (or inherits `teacher_os_enabled`).  
2. Defaults **false** in production until Pilot/GA.  
3. API `/health/meta` (or equivalent) is preferred source of truth.  
4. Document every new flag in `engineering/EBP-*/FEATURE_FLAGS.md` or this file’s appendix.  
5. E2E covers flag on and flag off.  
6. Rollback = flags first (see EBP-001 `ROLLBACK_PLAN.md`).

Wave 1 keys: `teacher_os_enabled`, `today_dashboard_enabled`, `review_queue_enabled`, `continuous_context_enabled`.

---

## 9. Logging standards

1. No PII in logs (student names, full message bodies, tokens).  
2. Correlate with `request_id` / `work_id` / `artifact_id` where available.  
3. Log lifecycle transitions at info: `artifact.lifecycle_changed`.  
4. Errors: structured message + code; no stack traces to clients.  
5. Do not log raw LLM prompts/responses in production by default.

---

## 10. Telemetry events (minimum)

| Event | When |
|-------|------|
| `mission.viewed` | Teacher opens Today's Mission |
| `mission.review_cta_clicked` | Review → |
| `artifact.generated` | AI Generated state entered |
| `artifact.review_opened` | Opened from Queue |
| `artifact.approved` | Teacher approved |
| `artifact.rejected` | Teacher rejected |
| `artifact.published` | Published to audience |
| `work.continued` | Continue existing Work |
| `context.followup` | Continuous Context refine (“make harder”) |
| `flag.evaluated` | (debug/sampled) Teacher OS flag state |

Emit properties: `artifact_type`, `lifecycle_state`, `school_id` (non-PII), `flag_cohort`.

---

## 11. Error handling

1. User-facing errors are calm and actionable (“Couldn’t load Review Queue — retry”).  
2. Partial kit failure: show succeeded Artifacts + retry failed types.  
3. Never leave Artifact stuck invisible after generate — always Queue or explicit error.  
4. Timeouts show progress + cancel where feasible.  
5. API: consistent error envelope already used by platform; do not invent a third shape.

---

## 12. Code review checklist

Reviewers verify:

- [ ] Vertical slice (UI + API + tests) or justified docs-only  
- [ ] Feature flag gated  
- [ ] Artifact lifecycle respected (no publish bypass)  
- [ ] Intent not used as durable store; Work/Artifact persistence clear  
- [ ] Reuses generators/platform content where applicable  
- [ ] Naming/folders match this standard  
- [ ] Tests: unit + integration/E2E as appropriate  
- [ ] a11y considered for new UI  
- [ ] Logging/telemetry without PII  
- [ ] Rollback path via flags documented in PR  
- [ ] No new application repo / no major unrelated refactor  

---

## 13. PR description minimum

1. User story / slice id (EBP-001 task id)  
2. Flags touched  
3. Test evidence  
4. Screenshots or clip for UI slices  
5. Risk notes (especially approval/publish)

---

## 14. Amendments

Changes to this constitution require Product + Engineering lead acknowledgement and a short note in `engineering/README.md` / CHANGELOG when present.

**Sprint 0 of EBP-001 must not start until this file is accepted.**
