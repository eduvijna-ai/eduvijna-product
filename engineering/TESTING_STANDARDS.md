# Testing Standards

**ID:** ENG-TEST-001  
**Parent:** ENGINEERING_CONSTITUTION.md  
**Rule:** No merge without automated validation appropriate to the change

---

## 1. Required test types

| Type | Web | API | When |
|------|-----|-----|------|
| **Unit** | Vitest | pytest | Logic, flags, mappers, lifecycle transitions |
| **Integration** | Client + mocked/real API as project practice | httpx/pytest | generate → Teacher Review → Approved |
| **End-to-end** | Playwright | — | Mission, nav, Review Queue happy paths; Continuous Context refine |
| **Accessibility** | axe / Playwright a11y | — | New interactive Teacher OS surfaces |
| **Regression** | Existing smoke packs | Platform/generation packs | Auth, generators, flag-off classic flows |

---

## 2. Principle tests (block Pilot)

| ID | Assertion |
|----|-----------|
| P-01 | Generate does **not** auto-publish to students |
| P-02 | Share/assign blocked until Artifact **Approved** |
| P-03 | Explicit publish/assign step after approval (when publish UI exists) |
| P-04 | Flag off restores classic home/nav |

---

## 3. Slice DoD

A vertical slice is not done until:

- [ ] Unit coverage for new logic  
- [ ] Integration or E2E for the teacher-visible behaviour  
- [ ] Regression smoke relevant to touched paths  
- [ ] a11y checks if new UI  
- [ ] Evidence linked in PR  

---

## 4. Commands (current repos)

**Web:** `npm run test:unit` · `npm run test:e2e`  
**API:** `pytest` (Teacher OS + generation/lifecycle related scope minimum on PRs)

---

## 5. Flaky tests

- Quarantine with ticket; do not ignore silently.  
- Prefer deterministic fakes for LLM generate in E2E (mocked generate → Queue).

---

## 6. Related

- EBP-001 `TEST_PLAN.md`  
- `ACCESSIBILITY_STANDARDS.md`  
- `REVIEW_CHECKLIST.md`  
