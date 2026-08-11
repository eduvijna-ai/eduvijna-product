# EBP-001.5 — Known Risks

| ID | Risk | Mitigation |
|----|------|------------|
| R-RQ-01 | Teams invent `Rejected` lifecycle | ADR-046 + reviewDecision field; unit asserts enum |
| R-RQ-02 | Approve confused with Publish | Explicit copy + banner; no Publish button |
| R-RQ-03 | Request Changes implies AI ran | Notice: request saved only; no regeneration |
| R-RQ-04 | Mock store resets on reload | Expected until real ArtifactService |
| R-RQ-05 | Mission pending count vs queue drift | Both seed from `MOCK_REVIEW_ARTIFACTS_SEED` |
