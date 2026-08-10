# Accessibility Standards

**ID:** ENG-A11Y-001  
**Parent:** ENGINEERING_CONSTITUTION.md  
**Applies to:** All Teacher OS UI

---

## 1. Requirements

1. **Keyboard:** All primary flows (Mission → Review → Approve) completable without a pointer.  
2. **Focus:** Visible focus indicator on interactive elements; focus order logical.  
3. **Semantics:** Correct headings, landmarks (`main`, `nav`), button vs link roles.  
4. **Labels:** Icon-only controls have accessible names; Queue badge counts announced appropriately.  
5. **Contrast:** Text and primary CTAs meet WCAG AA contrast as a target.  
6. **State not by colour alone:** Lifecycle badges include text/icon.  
7. **Motion:** Respect reduced-motion preferences where animations are added.  
8. **Errors:** Error text associated with fields/actions for AT.

---

## 2. Surfaces that must be checked

- Today's Mission  
- Review Queue (list + item actions)  
- Teacher OS primary navigation  
- Continuous Context controls (if interactive)  
- Loading/empty/error states on the above  

---

## 3. Validation

- Automated axe (or equivalent) in Playwright for new pages.  
- Manual keyboard pass on Mission + Queue before Pilot.  
- a11y failures block merge for new Teacher OS UI unless waived with Product lead + ticket.

---

## 4. Related

- `UI_STANDARDS.md`  
- `TESTING_STANDARDS.md`  
