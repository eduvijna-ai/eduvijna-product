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

### Today's Mission (login landing — not a nav peer)

- **Job:** Mission briefing  
- **Default landing** after every login  
- Surfaces: greeting, day counts (classes / assessments / PTM), AI readiness line, **Review →**  
- Hands off to Review Queue (hero), Today schedule (secondary)  
- See `TODAYS_MISSION.md`

### Today

- **Job:** Full day workspace (schedule, period cards, notices, continue)  
- Surfaces: timetable strip, readiness of kits, observe alerts  
- Does **not** replace Mission as first viewport  

### Prepare

- **Job:** Intent → orchestration → **Review Queue**  
- Primary: Teaching Intent composer  
- After Generate: land in Review Queue for that kit (Continuous Context active)  
- Secondary: week/unit plan, source attach  

### Teach

- **Job:** Live period support + Observe  
- Primary: current/next period kit, explain assist, exit check, cover pack  

### Assess

- **Job:** Evidence create / conduct / evaluate / analyze  
- Primary: assessments, attempts, scoring review, heatmaps  
- New AI drafts still enter Review Queue before student publish  

### Improve

- **Job:** Act and compound  
- Primary: remediation, pacing, parent/PTM/remarks drafts, memory insights  
- Drafts enter Review Queue  

### Review Queue (signature surface)

- **Job:** Review and approve all AI outputs in one place  
- Entry: Mission **Review →**, post-Generate, shell badge  
- See `REVIEW_QUEUE.md`  

### Library

- **Job:** Find and reuse  
- Approved kits, artefacts, uploaded sources, favorites  
- Create new only by starting an Intent (routes to Prepare)  

### AI Assistant

- **Job:** Conversational entry that resolves to Intent or loop stage  
- Shares **Continuous Context** with active Intent/thread  
- Never silent-publish — outputs enter Review Queue  

### Settings

- **Job:** Teacher Memory controls, notification preferences, language, account, feature previews  
- Not a feature warehouse  

---

## Cross-nav rules

| Rule | Meaning |
|------|---------|
| Mission first | Login opens Today's Mission, not a nav menu |
| Single primary home | Each capability has one canonical nav parent |
| Review is the cockpit | All AI outputs pass Review Queue before publish |
| Continuous Context | Related follow-ups stay in one thread |
| Deep links allowed | Assess may open a quiz created in Prepare without moving ownership |
| Status travels | Artefact lifecycle + queue state visible wherever opened |
| Intent continuity | Starting Intent from AI Assistant opens Prepare → Queue |
| No generator nav | Worksheet/Quiz/PPT never appear as peer top-level items |

---

## Mobile vs desktop (product expectation)

| Context | Expectation |
|---------|-------------|
| Phone | Mission briefing + Review Queue dominate; Teach quick actions |
| Desktop / laptop | Full kit review in Queue; Analyze; Library browsing |
| Low connectivity | Last approved kits + Mission counts from cache (product requirement) |

---

## Entry after login

1. **Always** → Today's Mission briefing  
2. Hero CTA → Review Queue (today filter)  
3. Secondary → Today schedule / continue Intent  

---

## Related

- Wireframes: `../wireframes/HOME.md`, `REVIEW_QUEUE.md`, `TODAY.md`  
- Screen hierarchy: `SCREEN_HIERARCHY.md`
