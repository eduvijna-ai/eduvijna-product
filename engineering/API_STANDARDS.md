# API Standards

**ID:** ENG-API-001  
**Parent:** ENGINEERING_CONSTITUTION.md  
**Applies to:** `eduvijna-api` (and web clients consuming it)

**Rule:** Reference and extend **existing** API conventions. Do not invent a parallel error/auth stack for Teacher OS.

---

## 1. Versioning

1. Public HTTP under **`/api/v1/`**.  
2. Additive changes preferred on v1.  
3. Breaking changes require version bump or explicit migration flag — never silent.  
4. Teacher OS aggregates (if needed): `/api/v1/teacher-os/*`.  
5. Reuse existing content/generation routes for Artifact create where possible (`POST /api/v1/content/generate`, content CRUD).

---

## 2. Error model

Align with existing platform envelope (`AppException` → ACP/`ErrorResponse` in `app/platform/exceptions.py`, `app/platform/responses.py`, and common schemas in `app/schemas/common_responses.py`).

Expectations for new endpoints:

| Requirement | Practice |
|-------------|----------|
| Stable `code` | Machine-readable (e.g. `not_found`, `validation_failed`) |
| Human `message` | Safe for UI display |
| `request_id` / correlation | Use existing request context / correlation id |
| Field errors | For 422 validation, structured field list |
| No stack traces to clients | Log server-side only |
| Retryable hint | When already supported by envelope |

Do **not** introduce a second Teacher-OS-only error JSON shape.

---

## 3. Pagination

1. Prefer existing list pagination patterns already used by content/list APIs (cursor or limit/offset — **match the nearest sibling endpoint**).  
2. Review Queue / Artifact lists must paginate; no unbounded dumps.  
3. Response includes enough metadata for UI “load more” / page controls.  
4. Default page sizes stay conservative for Mission/Queue performance (&lt;2s Mission budget).

---

## 4. Idempotency

1. Reuse existing idempotency patterns where present (e.g. content AI idempotency / `request_id` alignment in services).  
2. Approve / reject / publish transitions must be **safe to retry** (idempotent state transitions or explicit conflict responses).  
3. Generate endpoints: follow existing Generation Coordinator idempotency; do not double-create Artifacts on client retry without keys.  
4. Clients should send idempotency/request identifiers when the platform already expects them.

---

## 5. Validation

1. Request bodies validated via existing Pydantic/schema patterns.  
2. Reject unknown critical fields that would bypass lifecycle (e.g. client forcing `Published`).  
3. Lifecycle transitions validated server-side (In Review → Approved → Published per ADR-046).  
4. Tenant/school context required for platform Teacher OS operations (`require_platform_tenant` pattern).

---

## 6. Authorization

1. Use existing JWT `Authorize()` / role guards.  
2. Teachers only access Artifacts/Work for their school/classes.  
3. Approve/publish restricted to authorized teacher (or school policy roles).  
4. Never expose other teachers’ pending queues across tenant boundaries.  
5. Feature flags do not replace authZ.

---

## 7. Audit logging

1. Record Artifact lifecycle transitions (who, when, from→to, artifact_id, work_id).  
2. Record publish/assign/send events for compliance.  
3. No PII payloads in audit logs (see SECURITY + OBSERVABILITY).  
4. Prefer existing audit/logging facilities; extend rather than invent.

---

## 8. Teacher OS-specific list filters

Artifact list endpoints (new or extended) should support filters such as:

- `lifecycle_state`  
- `artifact_type`  
- `work_id`  
- time window (e.g. today) for Mission/Queue  

---

## Related

- Constitution § API / Preserve Architecture  
- `ARTIFACT_MODEL.md` · `INTENT_AND_WORK.md`  
