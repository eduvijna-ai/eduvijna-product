# EBP-001.8 — Architecture Compliance (Teacher / School Context Read Surface)

| Requirement | Result |
|-------------|--------|
| Repository | ✅ Existing `Quiz-React` |
| TeacherOsContext | ✅ Preserved (identity + shell selection + school.name hydrate) |
| ContinuousContext | ✅ Unchanged |
| MissionService | ✅ Unchanged |
| School source | ✅ Existing `GET /api/v1/school-management/my-school` |
| Teacher identity | ✅ Existing auth/profile |
| Teacher Memory | ❌ Not implemented |
| Teacher preferences | ❌ Not implemented |
| Inferred personalization | ❌ Not implemented |
| Database | ❌ No changes |
| New backend API | ❌ None |
| AI | ❌ Not implemented |
| Agents | ❌ Not implemented |
| MCP | ❌ Not implemented |
| Orchestration | ❌ Not implemented |
| Feature flag | ✅ `teacher_os_enabled` only |
| Breaking changes | ❌ None |

## Authorization pre-check

| Check | Result |
|-------|--------|
| Route | `GET /api/v1/school-management/my-school` |
| Auth | `Depends(Authorize())` — any authenticated user (not super-admin-only) |
| Tenancy | `current_user.school_id` from JWT only |
| Arbitrary school_id | ❌ Not accepted (no query/path school override) |
| Instructor (role_id=3) | ✅ Allowed when JWT has school_id |
