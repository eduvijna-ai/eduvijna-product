# Wireframe — Home / Today's Mission

**ID:** WF-HOME  
**Screens:** SCR-HOME shell + SCR-TODAYS-MISSION (login landing)  
**Fidelity:** Markdown structural wireframe only

---

## Purpose

First viewport after login is a **mission briefing**, not a navigation menu.

## Login landing (first viewport)

```text
┌──────────────────────────────────────────────────────────────────────────┐
│ EduVijna                                    [School]  [Ananya]  [🔔 5]   │
├──────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│                         Good Morning, Ananya                             │
│                                                                          │
│                         Today's Mission                                  │
│                                                                          │
│                         4 Classes                                        │
│                         2 Assessments                                    │
│                         1 PTM                                            │
│                                                                          │
│                         AI prepared everything                           │
│                                                                          │
│                         [  Review →  ]                                   │
│                                                                          │
│              Schedule · Continue last Intent · Review queue (5)          │
│                                                                          │
├──────────┬───────────────────────────────────────────────────────────────┤
│ TODAY    │  (nav quiet until teacher leaves mission)                     │
│ PREPARE  │                                                               │
│ …        │                                                               │
└──────────┴───────────────────────────────────────────────────────────────┘
```

## If AI is not fully ready (honest copy)

```text
AI prepared 3 of 4 periods
[ Review ready → ]   [ Finish remaining ]
```

## Mobile

```text
┌─────────────────────┐
│ Good Morning        │
│ Today's Mission     │
│                     │
│ 4 Classes           │
│ 2 Assessments       │
│ 1 PTM               │
│                     │
│ AI prepared         │
│ everything          │
│                     │
│ [ Review → ]        │
│                     │
│ Schedule · Queue    │
├─────────────────────┤
│ Today Prepare Teach │
└─────────────────────┘
```

## Key behaviours

| Element | Behaviour |
|---------|-----------|
| Review → | Opens Review Queue filtered to today's Needs review / Approved-ready |
| Schedule | Opens Today workspace |
| Bell badge | Count of queue + alerts |
| Nav | Available but not the hero |

## Principles

Mission first · Fast Review · Never Surprise · Minimum Clicks

## Non-goals

No generator shortcuts on the first viewport.
