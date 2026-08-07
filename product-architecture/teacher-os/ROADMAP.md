# Roadmap

**ID:** PA-ROAD-001  
**Status:** Draft — PA-001  
**Product phases — not sprint plans**

---

## Phase 1 — Teacher OS Foundation

**Outcome:** Teachers live in outcome nav; Prepare Tomorrow works as one Intent.

**Includes:**

- Shell: Today · Prepare · Teach · Assess · Improve · Library · AI Assistant · Settings  
- Teaching Intent model (flagship: Prepare Tomorrow)  
- School Context inheritance (core fields)  
- Teacher Memory MVP (manual + light learn-from-edit)  
- Kit review + approve + Library  
- Reuse worksheet, quiz, lesson, ingest under Intent  
- Feature flags: Preview → Pilot path  
- Legacy generator fallback  

**Exit criteria:** Prep time ↓; approval rate healthy; pilot activation gate met.

---

## Phase 2 — Teaching Assistant

**Outcome:** Daily Loop closes through Observe → Assess → Improve.

**Includes:**

- Teach live + Explain assist  
- Observe exit checks + confusion flags  
- Assess conduct/evaluate deepen  
- Analyze heatmaps actionable  
- Remediation Intent  
- Parent draft + PTM briefs  
- PPT + sketch notes in kits  
- Memory write-back confirmation UX  
- **Notification Center** — teacher workflow notifications (not chat); see `NOTIFICATION_CENTER.md`  

**Exit criteria:** Hours saved band emerging; remediation within 7 days rising; notifications deepen Mission/Today without distraction.

---

## Phase 3 — Student Intelligence

**Outcome:** Teacher-mediated personalisation at student level.

**Includes:**

- Richer student learning profiles visible to teachers  
- Differentiated homework/practice at scale  
- Stronger attempt insights feeding Improve  
- Student OS consumption of published kits (boundary respected)  

**Exit criteria:** Engagement ↑; follow-through ↑; teacher still in control.

---

## Phase 4 — School Intelligence

**Outcome:** Principals see teaching health without burdening teachers.

**Includes:**

- Principal OS academic aggregates from Teacher OS signals  
- Coverage vs mastery narratives  
- Adoption health of Teacher OS  
- Policy-level School Context completeness  

**Exit criteria:** School adoption + retention metrics; no surveillance backlash.

---

## Phase 5 — Parent Intelligence

**Outcome:** Parents get clarity; teachers do not drown.

**Includes:**

- Parent OS digests from approved teacher actions  
- Multilingual progress narratives  
- Reduced WhatsApp chaos via approved channels  
- PTM continuity  

**Exit criteria:** Parent clarity ↑; teacher after-hours messaging ↓ or stable.

---

## Dependency sketch (product)

```text
Phase 1 Foundation
    → Phase 2 Teaching Assistant (needs Intent+Memory+Context)
        → Phase 3 Student Intelligence (needs loop data)
            → Phase 4 School Intelligence (needs school-wide activation)
            → Phase 5 Parent Intelligence (needs Improve communicate maturity)
```

---

## Related

- `FEATURE_FLAGS.md`  
- `SUCCESS_METRICS.md`
