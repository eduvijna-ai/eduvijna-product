# Today's Mission

**ID:** PA-MISSION-001  
**Status:** Draft — PA-001 Amendment  
**Role:** Login landing — mission briefing, not navigation

---

## Problem

If the first screen after login is a navigation rail, the teacher must *hunt* for work.

Teachers need a **briefing**: what the day demands, what AI already prepared, and one clear next action.

---

## Definition

**Today's Mission** is the first experience after login.

It is a calm, scannable briefing that answers:

1. What do I owe today?  
2. What is already prepared?  
3. What should I review right now?

Navigation remains available — but it is **secondary** to the mission.

---

## Product behaviour on login

```text
Teacher logs in
      ↓
Greeting (time-aware)
      ↓
Today's Mission briefing
      ↓
Primary CTA: Review →  (opens Review Queue filtered to today's ready items)
```

The teacher should **not** land on an empty dashboard of icons.

---

## Mission briefing content

### Required

| Element | Example | Source |
|---------|---------|--------|
| Greeting | Good Morning | Time of day + teacher name (Memory) |
| Title | Today's Mission | Fixed label |
| Day load summary | 4 Classes · 2 Assessments · 1 PTM | Timetable + Assess schedule + calendar (School Context) |
| AI readiness line | AI prepared everything | Orchestration status for today's intents/kits |
| Primary CTA | Review → | Deep-link to Review Queue (today's ready set) |

### Supporting (progressive disclosure)

| Element | Example |
|---------|---------|
| Period readiness strip | P1 Ready · P3 Needs review · P5 Cover risk |
| Alerts | Exit check waiting · Parent draft pending |
| Secondary CTA | Open Today schedule · Continue last Intent |

---

## Example briefing (canonical)

```text
Good Morning, Ananya

Today's Mission

4 Classes
2 Assessments
1 PTM

AI prepared everything

[ Review → ]
```

---

## Rules

1. **Mission first, nav second** — chrome may be present but visually quiet; mission owns the first viewport.  
2. **Counts are factual** — drawn from School Context (timetable, exams, PTM), not vanity.  
3. **“AI prepared everything”** means: all *requested* today-related kits reached Ready for Review or Approved; if not, copy becomes honest (“3 of 4 periods ready”).  
4. **Review →** is the hero action — never “Create Worksheet.”  
5. **Never surprise** — Review opens items for approval; nothing is published by opening Mission.  
6. After Review, teacher may enter Teach / Assess / Improve as needed.

---

## Relationship to Today nav

| Surface | Role |
|---------|------|
| **Today's Mission** (Home landing) | Briefing + CTA |
| **Today** (nav destination) | Full day schedule, period cards, notices, continue actions |

Mission is the *front door*. Today is the *day workspace*.

---

## Signature test

If the first viewport could be mistaken for a generic SaaS sidebar home, Mission has failed.

---

## Related

- Wireframe: `../wireframes/HOME.md`, `../wireframes/TODAY.md`  
- Review Queue: `REVIEW_QUEUE.md`  
- Continuous Context: `CONTINUOUS_CONTEXT.md`
