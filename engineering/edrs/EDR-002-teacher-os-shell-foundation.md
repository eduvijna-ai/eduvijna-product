# EDR-002 — Teacher OS Shell Foundation

**ID:** EDR-002  
**Title:** Teacher OS Shell Foundation (implementation choices)  
**Status:** Accepted  
**Date:** 2026-08-10  
**Authors:** EduVijna Engineering  
**Related:** PA-001 · EBP-001 · EBP-000 · **ADR-042** (Shell owns UX) · EDR-001 (Continuous Context — separate concern)

> **Note:** EDR-001 already records React Context for session Continuous Context. This EDR covers the **Teacher OS Shell** foundation choices. Numbering is sequential; content matches the requested “Teacher OS Shell Foundation” record.

---

## Architecture impact

- [x] **Does not change architecture** (required for EDR)  
- [ ] Would change architecture → **STOP** — open ADR / Product Architecture change instead  

PA-001 IA, Artifact Model, Intent/Work, and Review Queue boundaries are unchanged. **ADR-042** now states architecturally that the Shell owns UX only; this EDR records *how* that shell is built inside existing repositories.

---

## Context

EBP-001 ships the permanent Teacher OS chrome (shell, nav, flag, placeholders) inside `Quiz-React` and `eduvijna-api`. Engineers needed durable implementation choices so later slices do not fork layout, invent new flag plumbing, or replace classic EduVijna prematurely.

---

## Decision

1. **React Context for shell-scoped selection (`TeacherOsContext`)**  
   Hold `currentTeacher`, `school`, `selectedAcademicYear`, `selectedClass`, `selectedSubject` only — no AI, Intent, or Memory.  
   Aligns with Constitution “no new state-management library” and with EDR-001’s Context preference for session-scoped UI state (different domain: Continuous Context vs shell selection).

2. **Feature flag provider (`TeacherOsFlagProvider`)**  
   Resolve `teacher_os_enabled` from `/health/meta` when available, with `VITE_TEACHER_OS_ENABLED` fallback. Gate routes via `FeatureFlagGuard` (redirect, not CSS-hide). Default **false**.

3. **Retain existing `MainLayout`**  
   Classic EduVijna chrome remains the default experience when the flag is off. Teacher OS uses a dedicated `TeacherShell` only on Teacher OS routes. MainLayout gains a single gated **Teacher OS** entry for discoverability when the flag is on.

4. **Preserve existing routes**  
   No renames or removals of classic routes. Teacher OS paths are additive (`/teacher-os/*`, `/library`). Dynamic quiz-nav registration excludes these static paths to avoid collisions.

5. **Supporting foundation (same EDR scope)**  
   - `TeacherOsRoutes` constants — no literal route strings in UI  
   - `TeacherNavigation` config array — extend nav without editing shell JSX  
   - Empty extension slots: `HeaderActions`, `SidebarFooter`, `PageToolbar`, `PageActions`  
   - `TeacherTelemetry` façade over existing `__EDUVIJNA_TELEMETRY__` sink  

---

## Reason

| Choice | Why |
|--------|-----|
| Context | Adequate for shell selections; Redux/Zustand would violate “no new state library” and overfit this slice |
| Flag provider | Constitution + FEATURE_FLAG_STANDARDS: API source of truth, default off, no regression |
| Keep MainLayout | Rollback = disable flag; teachers keep classic app; no big-bang chrome swap |
| Preserve routes | Repository strategy / no parallel app; additive Teacher OS only |
| Extension slots | Prevent repeated shell edits as Mission, Queue, Assistant land |

---

## Consequences

**Positive**

- Later slices plug into slots/config/context without redesigning chrome  
- Flag-off path is the production-safe default  
- Telemetry and routes stay consistent  

**Negative / follow-ups**

- Dual chrome until Mission becomes default landing (product decision: after Mission is production-quality)  
- School `name` on shell context may be enriched later from school services  
- Wire `TeacherTelemetry` callers only; do not invent a second sink  

---

## Alternatives considered

1. **Replace MainLayout entirely when flag on** — Rejected: higher regression risk; Constitution prefers additive gated rollout.  
2. **Redux / new global store for shell** — Rejected: forbidden by engineering standards for this need.  
3. **CSS-hide Teacher OS without route guards** — Rejected: FEATURE_FLAG_STANDARDS require behavioural gates.  
4. **Hardcoded nav JSX in shell** — Rejected: blocks config-driven extension.

---

## Open question resolutions (product)

Recorded for implementers (not architectural changes):

1. Mission as default landing — **eventually yes**; not in this shell slice.  
2. Review badge — **remain inert** until Review Queue exists.  
3. Library path — **`/library`** (platform capability).  
4. Classic entry label — **“Teacher OS”** approved.  
5. Telemetry — **existing EduVijna sink only**.
