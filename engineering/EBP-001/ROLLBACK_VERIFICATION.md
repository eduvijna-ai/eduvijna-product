# EBP-001.5 — Rollback Verification

1. Disable `teacher_os_enabled` (API flag / env override).  
2. Confirm `/teacher-os/review` does not render Review Queue UI.  
3. Confirm classic dashboard / Platform AI paths still work.  
4. No DB migration to reverse.  
5. No new feature flag to disable separately — master flag only.
