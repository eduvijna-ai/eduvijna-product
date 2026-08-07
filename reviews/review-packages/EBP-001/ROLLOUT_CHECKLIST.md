---
id: EBP-001-ROLLOUT
title: EBP-001 — Rollout Checklist
---

# Rollout Checklist

## Preview

- [ ] API flags deployed and visible on `/health/meta`  
- [ ] Web Teacher OS module deployed with flags off by default  
- [ ] Enable `teacher_os_enabled` on Preview  
- [ ] Enable `today_dashboard_enabled`  
- [ ] Enable `review_queue_enabled`  
- [ ] Enable `continuous_context_enabled`  
- [ ] Smoke: login → Mission → Queue → approve  
- [ ] Smoke: flag off restores classic home  

## School Pilot

- [ ] Pilot schools identified  
- [ ] Entitlement / flag targeting configured  
- [ ] Champion teacher trained on Mission + Queue  
- [ ] Principle tests P-01–P-04 green on Pilot build  
- [ ] Support channel ready  
- [ ] Rollback owner named  

## Pre-GA (Wave 1 complete)

- [ ] Acceptance criteria all met  
- [ ] Rollback drill recorded  
- [ ] Performance Mission &lt; 2s  
- [ ] No publish-bypass incidents  
- [ ] Product Architecture + Engineering sign-off  
