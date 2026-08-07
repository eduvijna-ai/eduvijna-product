# Wireframe — AI Assistant

**ID:** WF-AI  
**Screen:** SCR-ASSISTANT-CHAT

---

## Purpose

Natural-language entry that **resolves to Teaching Intent or loop stage** — never a parallel product.

## Assistant

```text
┌─────────────────────────────────────────────────────────────┐
│ AI Assistant                                      [Minimize] │
│ Context chips: CBSE · Ananya · 7-B Science                   │
├─────────────────────────────────────────────────────────────┤
│ You: Prepare tomorrow photosynthesis for 7-B                 │
│                                                              │
│ Assistant: I can start Teaching Intent                       │
│   Type: Prepare Tomorrow                                     │
│   Class 7-B · Science · Tomorrow P3                          │
│   Artefacts: objectives, lesson, worksheet, quiz, homework…  │
│   [ Confirm & open Prepare ]  [ Adjust ]  [ Just explain ]   │
│                                                              │
│ You: Explain chlorophyll simpler for Grade 7                 │
│ Assistant: …explanation…  [ Pin to Teach ] [ Copy ]          │
│ Note: Not sent to students.                                  │
├─────────────────────────────────────────────────────────────┤
│ [ Type a teaching goal…                              Send ]  │
└─────────────────────────────────────────────────────────────┘
```

## Guardrails on wireframe

- Confirm before orchestration  
- “Not sent to students” on teacher-facing explains  
- Shortcuts: Prepare · Teach explain · Assess create · Improve draft  

## Principles

One Conversation · Never Surprise · Teacher Control · Context Awareness
