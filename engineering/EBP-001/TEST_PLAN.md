# EBP-001 — Test Plan

**ID:** EBP-001-TEST  
**Rule:** No feature merges without automated validation

---

## 1. Required test types (every vertical slice)

| Type | Web | API | Purpose |
|------|-----|-----|---------|
| Unit | Vitest | pytest | Flags, reducers, mappers, domain rules |
| Integration | API client + MSW/mocked server where used | httpx/pytest against app | generate → queue → approve |
| UI / E2E | Playwright | — | Mission, nav, queue happy paths |
| Accessibility | Playwright a11y / axe on new surfaces | — | Mission, Queue, nav |
| Regression | Playwright + Vitest smoke | pytest platform/generation packs | Login, generators, flag-off paths |

---

## 2. Wave 1 acceptance test matrix

| Criterion | Automated proof |
|-----------|-----------------|
| Teacher OS shell accessible | E2E: flag on → nav + `/teacher-os` |
| Outcome navigation | E2E: all 8 destinations reachable |
| Today's Mission functional | E2E: greeting + counts region + Review CTA |
| Review Queue + existing generators | Integration + E2E: Platform AI generate → pending → approve |
| Continuous Context in session | E2E: follow-up refine without restating class/topic |
| Generators remain operational | Regression: `/platform-ai/*` + critical legacy paths |
| No workflow regression | Regression pack green |
| Feature flags safe rollout | E2E: flag off restores prior landing/nav |

---

## 3. Critical principle tests (block Pilot)

| ID | Assertion |
|----|-----------|
| P-01 | Generate does **not** auto-publish to students |
| P-02 | Share/assign disabled or blocked until Approved |
| P-03 | Approve then publish is explicit second step (when publish UI present) |
| P-04 | Flag off: no Teacher OS nav leakage for standard teachers |

---

## 4. Performance checks

| Check | Target | Method |
|-------|--------|--------|
| Mission/Dashboard load | &lt; 2s | Playwright timing / Lighthouse CI optional |
| Nav interaction | &lt; 100 ms perceived | UI responsiveness smoke |
| AI status update | &lt; 500 ms | Unit/integration around status polling/ws if used |
| Long generate | Progress visible | E2E asserts progress indicator present |

---

## 5. Accessibility checklist (new UI)

- [ ] Correct landmark/headings on Mission and Queue  
- [ ] Keyboard reachability for Review CTA, queue actions, nav  
- [ ] Focus visible  
- [ ] Contrast on Mission hero CTA  
- [ ] Screen-reader labels on badge counts  

---

## 6. Commands (current repos)

### Web (`Quiz-React`)

```text
npm run test:unit
npm run test:e2e
```

### API (`eduvijna-api`)

```text
pytest
```

(Use project’s documented subset markers if full suite is long; Wave 1 PRs must run Teacher OS + generation/lifecycle related tests.)

---

## 7. PR merge gate

| Gate | Required |
|------|----------|
| Unit tests for touched modules | Yes |
| Integration or E2E for user-visible behaviour | Yes |
| Regression smoke | Yes |
| a11y on new interactive views | Yes |
| Flag default safe (off in prod until Pilot) | Yes |

---

## 8. Evidence for EBP-001 review package

Before Wave 1 “complete” declaration, attach:

- CI run links / local summarized results  
- List of new test files  
- Rollback drill result  
- Performance smoke notes  
