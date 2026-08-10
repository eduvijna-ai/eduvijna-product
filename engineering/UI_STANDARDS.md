# UI Standards

**ID:** ENG-UI-001  
**Parent:** ENGINEERING_CONSTITUTION.md  
**Applies to:** Teacher OS surfaces in `Quiz-React`  
**Nature:** Engineering guidance — **not** a full design-system implementation

---

## 1. Page layout

1. **Mission first** on login — briefing owns the first viewport; nav is secondary (PA Today's Mission).  
2. Outcome nav: Today · Prepare · Teach · Assess · Improve · Library · AI Assistant · Settings.  
3. Review Queue is the approval cockpit — reachable from Mission CTA and shell badge.  
4. One primary CTA per view when possible (e.g. Mission → Review).  
5. Respect existing MainLayout patterns; additive Teacher OS section, not a parallel app chrome.

---

## 2. Spacing & typography

1. Follow existing Tailwind spacing scale used in the app — do not invent a new scale.  
2. Preserve established heading hierarchy (`h1` Mission title, section `h2`s).  
3. Avoid dense walls of AI text; prefer scannable summaries with progressive disclosure.  
4. Type labels (worksheet/quiz) are secondary to Artifact status.

---

## 3. Loading states

1. Initial route load: page-level loading consistent with app patterns.  
2. Prefer **skeletons** for Mission counts and Queue lists over blank screens.  
3. Inline actions (approve, regenerate): button busy state + disable double-submit.  
4. Never block the entire shell for a single Queue item action.

---

## 4. Skeletons

1. Mission: skeleton for greeting block + count rows + CTA.  
2. Review Queue: skeleton rows matching final list density.  
3. Skeletons should approximate final layout to reduce shift (CLS).

---

## 5. Empty states

| Surface | Empty copy guidance |
|---------|---------------------|
| Review Queue | Calm “Nothing to review” + link to Prepare |
| Mission counts | Honest zeros; never fake “AI prepared everything” |
| Library | Guide to create via Intent / Prepare |

Empty states include one clear next action.

---

## 6. Error states

1. User-facing, non-technical messages.  
2. Retry where safe.  
3. Partial failure: show succeeded Artifacts + failed types with retry.  
4. Do not lose the teacher in a dead end — always path back to Mission/Queue.

---

## 7. AI progress indicators

1. Any generate &gt; ~300 ms shows progress (determinate if known, otherwise indeterminate + label).  
2. Multi-artifact orchestration: per-Artifact status in Queue (Assembling / AI Generated).  
3. Continuous Context follow-ups (“make harder”) show which Artifact is updating.  
4. Never silent hang.

---

## 8. Keyboard navigation

1. All primary actions reachable by keyboard.  
2. Visible focus rings.  
3. Queue: move between items, open, approve without pointer-only traps.  
4. See `ACCESSIBILITY_STANDARDS.md`.

---

## 9. Responsive behavior

1. Mobile: Mission + Review Queue dominate; nav may collapse to bottom/more pattern already used.  
2. Desktop: Queue list + preview pane acceptable.  
3. Touch targets adequately sized on phone.  
4. Do not hide Approve behind hover-only controls.

---

## 10. Non-goals

- New brand redesign or token system in Wave 1  
- Pixel-perfect Figma implementation requirement  
- Chat-style notification UI (Wave 2 Notification Center is separate)
