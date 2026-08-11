# EBP-001.8 — Known Risks

| Risk | Mitigation | Residual |
|------|------------|----------|
| my-school 404 when user has no school_id | Non-blocking; school card shows — | Low |
| my-school network failure | Fallback `School #<id>`; no error page | Low |
| Super-admin without school_id | No hydrate; school null — expected | Accepted |
| Naming confusion with “Teacher Memory” | Docs + UI avoid Memory/Preferences claims | Process |
| Duplicate fetches if provider remounts | Provider is once under Teacher OS layout | Low |

## Non-risks

- No DB / API / MissionService / ContinuousContext blast radius  
- Feature flag OFF unchanged  
