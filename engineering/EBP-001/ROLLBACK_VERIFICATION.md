# EBP-001.8 — Rollback Verification

## Flag rollback

`teacher_os_enabled = false` → classic dashboard; Teacher OS shell not shown.

## Code rollback

Revert TeacherOsContext school hydration + context card label tweaks.

Expected after revert:

- School card returns to `School #<id>` only  
- No DB/API/migration rollback  
- ContinuousContext / MissionService unchanged  

## Compatibility

Hydration removal is additive-safe; Teacher OS remains functional with fallback naming.
