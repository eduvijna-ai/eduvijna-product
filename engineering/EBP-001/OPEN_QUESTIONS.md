# EBP-001.4 — Open Questions (Review Queue Entry)

Prior Intent decisions (EBP-001.3) remain in force. Updates for this slice:

---

## Q1 — Custom Goal free-text

**Prior decision:** Add free-text for Custom in EBP-001.4.

**This slice:** Not implemented — EBP-001.4 scope was **Review Queue Entry** only (mock preparing kit + placeholder).

**Status:** Still open for a follow-up Intent polish slice (or fold into EBP-001.5 if product prefers).

---

## Q2 — Default Context

**Decision:** Unchanged — no timetable autofill.

---

## Q3 — Continue destination

**Decision:** Implemented — Continue → Preparing kit → Open Review Queue → `/teacher-os/review` placeholder.

**Not** orchestration. **Not** full Review Queue.

---

## Still deferred

- **EBP-001.5** — Review Queue (approval cockpit)
- **ADR-047** — Prepare Tomorrow multi-artifact orchestration
- Custom goal free-text
- Real ArtifactService / generation / progress polling
- Timetable-driven defaults
- Backend AI platform internals (ADR-044)
