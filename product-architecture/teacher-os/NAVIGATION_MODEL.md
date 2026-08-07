# Navigation Model

**ID:** PA-NAV-001  
**Status:** Draft — PA-001

---

## Primary navigation (always available)

```text
Today | Prepare | Teach | Assess | Improve | Library | AI Assistant | Settings
```

**Order rationale:** mirrors Daily Learning Loop energy (start of day → prepare → teach → evidence → improvement), then reuse (Library), help (AI Assistant), control (Settings).

---

## Destination contracts

### Today

- **Job:** Orient and continue  
- **Default landing** after login on school days  
- Surfaces: timetable strip, readiness of kits, observe alerts, notices, continue actions  
- Does **not** create deep artefacts (hands off to Prepare/Teach/Assess)

### Prepare

- **Job:** Intent → kit  
- Primary: Teaching Intent composer + kit review  
- Secondary: week/unit plan, source attach  

### Teach

- **Job:** Live period support + Observe  
- Primary: current/next period kit, explain assist, exit check, cover pack  

### Assess

- **Job:** Evidence create / conduct / evaluate / analyze  
- Primary: assessments, attempts, scoring review, heatmaps  

### Improve

- **Job:** Act and compound  
- Primary: remediation, pacing, parent/PTM/remarks drafts, memory insights  

### Library

- **Job:** Find and reuse  
- Approved kits, artefacts, uploaded sources, favorites  
- Create new only by starting an Intent (routes to Prepare)  

### AI Assistant

- **Job:** Conversational entry that resolves to Intent or Loop stage  
- Never silent-publish  

### Settings

- **Job:** Teacher Memory controls, notification preferences, language, account, feature previews  
- Not a feature warehouse  

---

## Cross-nav rules

| Rule | Meaning |
|------|---------|
| Single primary home | Each capability has one canonical nav parent |
| Deep links allowed | Assess may open a quiz created in Prepare without moving ownership |
| Status travels | Artefact lifecycle status visible wherever opened |
| Intent continuity | Starting Intent from AI Assistant opens Prepare kit flow |
| No generator nav | Worksheet/Quiz/PPT never appear as peer top-level items |

---

## Mobile vs desktop (product expectation)

| Context | Expectation |
|---------|-------------|
| Phone | Today + Teach + quick Approve dominate; Prepare review possible |
| Desktop / laptop | Full Prepare kit review, Assess evaluation, Library browsing |
| Low connectivity | Today roster/attendance and previously approved kits remain usable offline-first *as product requirement* (implementation later) |

---

## Entry after login

1. If school day and next period within N minutes → **Today** focused on that period  
2. Else if incomplete kit for tomorrow → **Prepare** continue  
3. Else → **Today** overview  

---

## Related

- Wireframes: `../wireframes/`  
- Screen hierarchy: `SCREEN_HIERARCHY.md`
