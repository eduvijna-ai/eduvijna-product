---
id: TLM-001-CAP
title: TLM-001 — Capability Map Digest
owner: EduVijna Product Office
status: draft
version: 0.2.0
created: 2026-08-07
---

# Capability Map Digest

Canonical source: `capability-mapping/teacher-capabilities.md`.

## Abstraction first (not activities first)

```text
Teaching Intent
      ↓
Prepare Tomorrow
      ↓
Lesson Plan · Worksheet · Quiz · PPT · Sketch Notes · Homework
```

| Capability | Gap |
|------------|-----|
| Teaching Intent API | **New** |
| Teacher Memory | **New** |
| School Context inheritance | **New** (ERP exists as fragments) |
| Daily Loop / Teacher OS IA | **New** |
| Worksheet / Quiz services | None → Improve (under Intent) |
| PPT / Sketch notes | Missing / New |
| Remediation → Prepare Again | Missing / New |

## Teacher OS homes

Today · Prepare · Teach · Assess · Improve · AI Assistant

## Epic order (amended)

0. Foundations (Intent + Memory + School Context + OS IA)  
1. Prepare Tomorrow kit  
2. Observe → Assess → Analyze  
3. Improve → Prepare Again  
4. Ops integrity (no dual entry)
