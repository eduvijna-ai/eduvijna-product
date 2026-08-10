# EBP-001.3 — Known Risks (Teaching Intent)

| Risk | Severity | Mitigation |
|------|----------|------------|
| “Lesson Plan” / “Assessment” cards may be read as generators | Medium | Descriptions are goal-oriented; ADR-045 review copy; never list engines |
| Continue raises expectation of generation | Low | **Decided:** Continue → Review Queue **entry** (not orchestration); replace deferred stub in EBP-001.4 |
| Context not persisted across sessions | Accepted | No DB by design this slice |
| Custom goal has no free-text field yet | Low | **Decided:** free-text in EBP-001.4 |
| Context not auto-filled from timetable | Accepted | **Decided:** TeacherOsContext only until AI Platform stage |
