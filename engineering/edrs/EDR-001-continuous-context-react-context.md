# EDR-001 — Use React Context for session-scoped Continuous Context

**ID:** EDR-001  
**Title:** Use React Context for session-scoped Continuous Context  
**Status:** Accepted  
**Date:** 2026-08-10  
**Authors:** EduVijna Product Office / Engineering  
**Related:** PA-001 Continuous Context · EBP-001 Sprint 3 · `product-architecture/teacher-os/CONTINUOUS_CONTEXT.md`

---

## Architecture impact

- [x] **Does not change architecture**  
- [ ] Would change architecture → ADR instead  

PA-001 defines Continuous Context as a **session/Intent thread**, distinct from Teacher Memory and School Context. This EDR only selects the **web implementation mechanism**.

---

## Context

Wave 1 needs Continuous Context so follow-ups (“make worksheet harder”) retain Grade, topic, and focused Artifact without re-prompting.

Options exist for client state (React Context, Redux, Zustand, URL-only, React Query cache alone).

---

## Decision

**Use React Context** (feature-scoped provider under `src/features/teacher-os/context/`) for **session-scoped** Continuous Context in `Quiz-React`.

Persist durable Work/Artifact state via existing API/content sessions as designed in EBP-001 — Context holds the active thread, not long-term Memory.

---

## Reason

- Matches PA-001 session scope without unnecessary global app state  
- Keeps Teacher OS state colocated in `features/teacher-os/`  
- Avoids introducing a new global store dependency for one session concern  
- Aligns with existing React patterns in the codebase  

---

## Consequences

**Positive:** Simple, testable provider; clear teardown on logout / new Intent.  
**Negative:** Deep tree may need the provider placed at Teacher OS layout shell (not only one page).  
**Follow-up:** If cross-tab sync or very large thread graphs appear later, revisit via new EDR — still without changing PA session semantics unless PA is updated first.

---

## Alternatives considered

1. **Redux / global store** — heavier; implies app-wide coupling for session data.  
2. **URL query only** — insufficient for Artifact focus + recent directives.  
3. **React Query alone** — excellent for server Artifacts/Work; does not replace in-session directive/focus thread.  

---

## Supersedes

None.
