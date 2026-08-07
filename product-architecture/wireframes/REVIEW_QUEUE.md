# Wireframe — Review Queue

**ID:** WF-REVIEW-QUEUE  
**Screen:** SCR-REVIEW-QUEUE  
**Signature experience**

---

## Purpose

One place to review and approve every AI output — not download files one by one.

## Queue (kit-grouped)

```text
┌──────────────────────────────────────────────────────────────────────────┐
│ Review Queue                    [ Today ▾ ] [ Needs review ] [ 5 items ] │
│ Continuous Context: Grade 8 · Science · Photosynthesis                   │
├──────────────────────────────────────────────────────────────────────────┤
│ KIT · Prepare Tomorrow · 7-B Photosynthesis                              │
│                                                                          │
│  ☐ Lesson Plan      Needs review    [Open]                               │
│  ☐ Worksheet        Needs review    [Open]  ← focused                    │
│  ☐ Quiz             Needs review    [Open]                               │
│  ☐ PPT              Needs review    [Open]                               │
│  ☐ Homework         Needs review    [Open]                               │
│  ☐ Answer Key       Needs review    [Open]                               │
│                                                                          │
│  [ Approve selected ]  [ Approve kit ]                                   │
├──────────────────────────────────────────────────────────────────────────┤
│ IMPROVE · Parent draft · 7-B weak set                                    │
│  ☐ Parent Draft     Needs review    [Open]                               │
├──────────────────────────────────────────────────────────────────────────┤
│ READY TO PUBLISH                                                         │
│  (empty until approved)                                                  │
│  [ Publish / Assign… ]  (disabled until items approved)                  │
└──────────────────────────────────────────────────────────────────────────┘
```

## Item open (with Continuous Context)

```text
┌──────────────────────────────────────────────────────────────────────────┐
│ Worksheet · Grade 8 · Photosynthesis              Thread active          │
│ [Explain] [Edit] [Regenerate] [Make harder] [Approve] [Back to queue]    │
├──────────────────────────────────────────────────────────────────────────┤
│ Preview …                                                                │
│                                                                          │
│ Follow-up: “Make worksheet harder”                                       │
│ → AI updates this worksheet in-thread; quiz untouched unless asked       │
└──────────────────────────────────────────────────────────────────────────┘
```

## After approvals

```text
READY TO PUBLISH
  ✓ Lesson Plan
  ✓ Worksheet
  ✓ Quiz
  ✓ PPT
  ✓ Homework
  ✓ Parent Draft
[ Assign to Period 3 ] [ Send parent drafts ] [ Done ]
```

## Entry / Exit

| Entry | Exit |
|-------|------|
| Today's Mission Review → | Publish flows; Teach; Prepare; Mission |
| After Generate | Same kit focused |
| Shell badge | Full queue |

## Principles

Teacher Control · Always Explain AI · Never Surprise · One Conversation · Fast Review
