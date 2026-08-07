# Feature Boundaries

**ID:** PA-BOUND-001  
**Status:** Draft — PA-001  
**Prevent overlapping responsibilities**

---

## OS map

```text
Teacher OS     — teaching work & Daily Learning Loop
Student OS     — learning, practice, attempts, student materials
Parent OS      — visibility, schedules, approved communications
Principal OS   — school academic health, adoption, oversight
Admin Console  — ERP master data, roles, billing, school configuration
```

---

## Teacher OS (this architecture)

**Owns:** Teaching Intents, kits, prepare/teach/observe/assess/analyze/improve loop, Teacher Memory, teacher-facing orchestration, Library of teaching artefacts, approval gates.

**Does not own:** Fee collection, transport routes, payroll, admissions CRM, school-wide user provisioning (may deep-link).

---

## Student OS

**Owns:** Taking assigned quizzes, viewing published materials, practice, student-facing AI tutor **within teacher/school policy**, personal learning view.

**Does not own:** Creating assessments for the class, publishing to peers, editing Teacher Memory, parent broadcasts.

**Boundary rule:** Students only see **Published/Assigned** artefacts from Teacher OS.

---

## Parent OS

**Owns:** Attendance visibility, timetable, approved notices, fee views (if product includes), PTM booking, reading teacher-approved messages/reports.

**Does not own:** Drafting teacher messages, changing marks, accessing other students’ data.

**Boundary rule:** All teacher→parent content passes Teacher OS **Publish/Send** approval.

---

## Principal OS

**Owns:** School-level academic dashboards, syllabus coverage aggregates, teacher adoption health, inspection-ready summaries, policy toggles at school level (with Admin).

**Does not own:** Doing a teacher’s Prepare Tomorrow for them; silent access to private Memory pedagogical notes without policy.

**Boundary rule:** Oversight without turning Teacher OS into surveillance that increases teacher burden (TLM principle).

---

## Admin Console

**Owns:** School tenancy, roles, ERP modules (admissions, fees, HR, transport, inventory…), academic setup master data, branding assets, feature entitlements, integrations.

**Does not own:** Teaching Intent UX, kit review UX, Daily Loop coaching.

**Boundary rule:** Admin supplies **School Context**; Teacher OS consumes it.

---

## Shared objects (controlled)

| Object | Producer | Consumers |
|--------|----------|-----------|
| Roster | Admin / ERP | Teacher, Student, Parent, Principal |
| Timetable | Admin / ERP | Teacher Today, Student, Parent |
| Assessment attempt | Student OS | Teacher Assess |
| Approved message | Teacher OS | Parent OS |
| Marks | Teacher confirm | Principal aggregates, Parent report views |

---

## Anti-overlap checklist

- [ ] No second quiz creator in Student OS  
- [ ] No parent chat that bypasses Teacher approval  
- [ ] No Admin “generate worksheet” competing with Teacher Prepare  
- [ ] No Principal editing kits silently  
- [ ] Generator tools not exposed as peer products outside Teacher OS Intent  

---

## Related

- IA: `INFORMATION_ARCHITECTURE.md`
