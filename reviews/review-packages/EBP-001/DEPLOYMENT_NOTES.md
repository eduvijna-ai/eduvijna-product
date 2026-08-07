---
id: EBP-001-DEPLOY
title: EBP-001 — Deployment Notes
---

# Deployment Notes

## Order

1. **eduvijna-api** — feature flags + review list/approve endpoints + session continuity hooks  
2. **Quiz-React (eduvijna-web)** — Teacher OS module, Mission, Queue, nav  
3. **Enable flags** on Preview only  
4. Expand to Pilot tenants  
5. GA decision separate from Wave 1 engineering complete  

## Configuration

| Variable / key | Where |
|----------------|-------|
| `FEATURE_FLAGS_JSON` (teacher_os_*) | API |
| `VITE_TEACHER_OS_ENABLED` (if used) | Web build |
| Existing generate/LLM configs | Unchanged |

## Verification after deploy

```text
1. GET /health/meta → flags present
2. Login as teacher (flag off) → classic home
3. Enable flags → Mission landing
4. Generate via Platform AI → Review Queue item
5. Approve → not auto-visible to students without publish step
6. Disable flags → classic restored
```

## Monitoring

- Mission load time  
- Queue pending count / approval rate  
- Error rate on content generate  
- Any share/publish without approval (alert = page)

## Rollback

See `engineering/EBP-001/ROLLBACK_PLAN.md` — flag-first.
