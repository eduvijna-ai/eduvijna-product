# Experience Principles

**ID:** PA-XP-001  
**Status:** Draft — PA-001  
**UX expansion of Product Principles — not visual design**

---

## Mapping from Product Principles

| Product Principle | Experience principle |
|-------------------|----------------------|
| Teacher First | Outcomes over tools |
| AI Assists, Teacher Decides | Teacher Control |
| One Intent, Many Services | One Conversation |
| Minimize Workload | Minimum Clicks |
| Explain Every AI Output | Always Explain AI |
| Human Approval Before Delivery | Never Surprise Users |
| Save Time Daily | Fast Review |
| Continuous Improvement / Memory | Progressive personalisation |
| Privacy by Design | Private by default |
| School-Aware AI | Context Awareness |
| Daily Loop Is the Product | Loop continuity |

---

## Experience principles (normative)

### 1. Mission First

Login opens Today's Mission briefing. Navigation is secondary to the day's load and Review CTA.

### 2. One Conversation

A Teaching Intent + Continuous Context is one conversation. Teachers should not restart context across six tools or lose Grade/topic on “make it harder.”

**ADR-047 / ADR-045 / ADR-044 / ADR-046 / ADR-048:** Primary language is outcomes (“Help me prepare tomorrow”), not “Generate Worksheet.” Generators remain capabilities behind Intent. UI calls stable product services only — never agents or MCP directly. Every Artifact shares one lifecycle. **Review Queue owns teacher judgement only** — not generation, editing-as-product, or orchestration.

### 3. Minimum Clicks

Defaults from Teacher Memory + School Context. Every extra required field must justify itself.

### 4. Always Explain AI

Every draft shows *why* (chapter, difficulty, Bloom, evidence). Explain is one tap from any Review Queue item.

### 5. Teacher Control

Review, approve, reject, regenerate (request), request explanation, open editor — always available in Review Queue before publish (**ADR-048**). The queue does not generate or orchestrate.

### 6. Never Surprise Users

No silent sends. Status badges are honest. Orchestration progress is visible. Mission copy is honest when AI is not fully ready.

### 7. Progressive Disclosure

Mission summary first; Review Queue list next; deep editors on demand.

### 8. Context Awareness

Chips show school/class/board/period **and** Continuous Context thread. Wrong context is easier to spot than to retype.

### 9. Fast Review

Review Queue optimised for “good enough with ≤2 edits.” Approve path beats download path.

### 10. Loop Continuity

Every Analyze view offers an Improve action. Every Improve draft enters Review Queue. Every Improve action can seed Prepare Again.

### 11. Calm under chaos

Mission and Cover flows prioritise recovery when the day breaks — not perfect plans.

### 12. Language dignity

Parent and teacher language preferences respected without shame or hidden English-only paths.

### 13. Reuse over rebuild

Library duplicate is celebrated; blank-page create is secondary.

### 14. One Queue to Publish

All AI outputs enter Review Queue (**ADR-048** — judgement only). Ready to Publish is explicit. No one-by-one file hunting as the primary path. No generate-in-queue.

---

## Anti-patterns

- Generator dashboards as home  
- Review Queue as a generator or orchestrator  
- Navigation-first login  
- Walls of unread AI prose  
- Hidden auto-assign to students  
- Forcing board entry every generate  
- Dead-end analytics  
- Mid-kit amnesia (“which class?”)  
- Download-as-approval  

---

## Related

- `../../vision/PRODUCT_PRINCIPLES.md`  
- `TODAYS_MISSION.md` · `CONTINUOUS_CONTEXT.md` · `REVIEW_QUEUE.md`  
- **ADR-048** Review Queue owns approval  
- Wireframes must cite these principles in page purposes
