# Screen Hierarchy

**ID:** PA-SCR-001  
**Status:** Draft — PA-001  
**Note:** Conceptual screens only — no UI implementation

For every screen: Purpose · Primary user · Entry · Exit · Key actions · Dependencies · AI opportunities

---

## 0. Home / Shell

### SCR-HOME — Teacher OS Shell

| Field | Definition |
|-------|------------|
| Purpose | Persistent chrome: primary nav, school/teacher identity, global continue |
| Primary user | Teacher |
| Entry | App launch / deep link |
| Exit | Any primary destination |
| Key actions | Navigate; open AI Assistant; view notifications |
| Dependencies | Auth, School Context, Teacher Memory (light) |
| AI opportunities | None in chrome; Assistant entry only |

*Wireframe:* `../wireframes/HOME.md`

---

## 1. Today

### SCR-TODAY-OVERVIEW

| Field | Definition |
|-------|------------|
| Purpose | Day orientation: periods, kit readiness, alerts |
| Primary user | Teacher |
| Entry | Default login; nav Today |
| Exit | Period detail; Prepare; Teach; Assess; Improve; notice detail |
| Key actions | Continue Prepare; Open Teach for period; Review observe alert; Mark attendance shortcut |
| Dependencies | Timetable, calendar, kit statuses, notices, attendance ops |
| AI opportunities | “What should I do next?” ranking; overnight brief |

### SCR-TODAY-PERIOD

| Field | Definition |
|-------|------------|
| Purpose | Single period card: class, topic, kit state, quick actions |
| Primary user | Teacher |
| Entry | Today overview |
| Exit | Teach live; Prepare kit; Assess exit-check results |
| Key actions | Open kit; Start exit check; Open roster |
| Dependencies | Period metadata, intent kit, roster |
| AI opportunities | Suggest cover activity if kit missing |

*Wireframe:* `../wireframes/TODAY.md`

---

## 2. Prepare

### SCR-PREPARE-HUB

| Field | Definition |
|-------|------------|
| Purpose | Start or resume Teaching Intents; see in-progress kits |
| Primary user | Teacher |
| Entry | Nav Prepare; Today continue; AI Assistant |
| Exit | Intent composer; Kit review; Week plan |
| Key actions | New Intent; Resume draft; Duplicate past kit |
| Dependencies | Memory, School Context, Library history |
| AI opportunities | Suggest next Prepare Tomorrow from timetable |

### SCR-INTENT-COMPOSER

| Field | Definition |
|-------|------------|
| Purpose | Capture Teaching Intent in teacher language |
| Primary user | Teacher |
| Entry | Prepare hub; Assistant; deep link |
| Exit | Kit assembly / review; cancel |
| Key actions | Choose intent type; set topic/class/when; select artefacts; attach sources; Generate draft kit |
| Dependencies | Intent catalogue, Memory defaults, School Context inheritance |
| AI opportunities | Prefill from Memory/Context; recommend artefact set |

### SCR-KIT-REVIEW

| Field | Definition |
|-------|------------|
| Purpose | Review orchestrated artefacts as one kit; edit; approve |
| Primary user | Teacher |
| Entry | After orchestration; Library open kit |
| Exit | Approved → Teach/Library; regenerate piece; abandon |
| Key actions | Edit artefact; regenerate one; explain why; approve kit; schedule for period |
| Dependencies | Capability outputs, explainability, lifecycle |
| AI opportunities | Per-artefact regenerate; consistency check across kit |

### SCR-ARTEFACT-EDITOR

| Field | Definition |
|-------|------------|
| Purpose | Deep-edit one artefact (worksheet, quiz, lesson, PPT outline, homework, etc.) |
| Primary user | Teacher |
| Entry | Kit review |
| Exit | Back to kit; approve artefact |
| Key actions | Edit items; change difficulty; add/remove; save |
| Dependencies | Artefact type capabilities |
| AI opportunities | Local regenerate section; Bloom adjust |

### SCR-SOURCE-ATTACH

| Field | Definition |
|-------|------------|
| Purpose | Attach PDF/image/YouTube/website/handwritten as intent inputs |
| Primary user | Teacher |
| Entry | Intent composer |
| Exit | Back to composer/kit |
| Key actions | Add source; preview extract summary |
| Dependencies | Existing ingest capabilities |
| AI opportunities | Summarise source; propose questions |

### SCR-WEEK-PLAN

| Field | Definition |
|-------|------------|
| Purpose | Map topics to periods for the week with buffers |
| Primary user | Teacher |
| Entry | Prepare hub |
| Exit | Intent from a slot; Today |
| Key actions | Adjust plan; create Intent from slot |
| Dependencies | Timetable, calendar, syllabus |
| AI opportunities | Calendar-aware rebalance |

*Wireframe:* `../wireframes/PREPARE.md`

---

## 3. Teach

### SCR-TEACH-LIVE

| Field | Definition |
|-------|------------|
| Purpose | Run current period with approved kit at hand |
| Primary user | Teacher |
| Entry | Today period; nav Teach |
| Exit | Exit check; Explain assist; period end → Observe summary |
| Key actions | View lesson arc; open materials; launch exit check; request alternate explanation |
| Dependencies | Approved kit, roster, period clock |
| AI opportunities | Alternate examples; pacing nudge |

### SCR-TEACH-EXPLAIN

| Field | Definition |
|-------|------------|
| Purpose | Teacher-facing alternate explanation / analogy |
| Primary user | Teacher |
| Entry | Teach live; AI Assistant |
| Exit | Back to live |
| Key actions | Request simpler/harder/local analogy; copy to board notes |
| Dependencies | Topic context, Memory style, EduAsk-like capability |
| AI opportunities | Levelled explanations |

### SCR-TEACH-OBSERVE

| Field | Definition |
|-------|------------|
| Purpose | Capture who is confused; run micro-check |
| Primary user | Teacher |
| Entry | Teach live; Today alert |
| Exit | Assess results; Improve remediation seed |
| Key actions | Launch 3–5 Q check; flag students; note concept |
| Dependencies | Quiz conduct, roster |
| AI opportunities | Instant concept flags |

### SCR-TEACH-COVER

| Field | Definition |
|-------|------------|
| Purpose | Meaningful activity when period lost / substitution |
| Primary user | Teacher |
| Entry | Today disruption; Teach |
| Exit | Kit approve light; back to Today |
| Key actions | Generate cover pack; approve; start |
| Dependencies | Intent “Recover Lost Period” |
| AI opportunities | Instant filler aligned to subject |

*Wireframe:* `../wireframes/TEACH.md`

---

## 4. Assess

### SCR-ASSESS-HUB

| Field | Definition |
|-------|------------|
| Purpose | Assessments in draft/live/completed; start assess intents |
| Primary user | Teacher |
| Entry | Nav Assess |
| Exit | Create intent; conduct; evaluate; analyze |
| Key actions | New assessment Intent; open live attempt monitor; open results |
| Dependencies | Class list, prior kits |
| AI opportunities | Suggest test from taught topics |

### SCR-ASSESS-CONDUCT

| Field | Definition |
|-------|------------|
| Purpose | Share/monitor student attempts |
| Primary user | Teacher |
| Entry | Hub; Teach exit check |
| Exit | Evaluate; Analyze |
| Key actions | Share link/notify; watch completion; close attempt window |
| Dependencies | OpenQuiz/share, roster, notifications |
| AI opportunities | Anomaly / low-attempt nudges (teacher-facing) |

### SCR-ASSESS-EVALUATE

| Field | Definition |
|-------|------------|
| Purpose | Review scores; confirm assisted marking; feedback |
| Primary user | Teacher |
| Entry | Conduct complete; hub |
| Exit | Analyze; Improve |
| Key actions | Confirm auto-scores; edit subjective drafts; publish marks to record (approval) |
| Dependencies | Scoring capabilities, ERP marks bind |
| AI opportunities | Objective auto-score; subjective draft feedback |

### SCR-ASSESS-ANALYZE

| Field | Definition |
|-------|------------|
| Purpose | Concept heatmap, weak students, section fairness |
| Primary user | Teacher |
| Entry | After evaluate; hub |
| Exit | Improve remediation; Prepare Again |
| Key actions | Filter concepts; select students; send to Improve |
| Dependencies | Analytics capabilities |
| AI opportunities | Heatmap; “teach next” suggestions |

*Wireframe:* `../wireframes/ASSESS.md`

---

## 5. Improve

### SCR-IMPROVE-HUB

| Field | Definition |
|-------|------------|
| Purpose | Action queue from Analyze + communication + memory |
| Primary user | Teacher |
| Entry | Nav Improve; Assess analyze CTA |
| Exit | Remediation kit; message draft; PTM; remarks; memory |
| Key actions | Start remediation Intent; draft parent update; open PTM briefs |
| Dependencies | Analyze outputs, parent channels |
| AI opportunities | Prioritised action list |

### SCR-IMPROVE-REMEDIATE

| Field | Definition |
|-------|------------|
| Purpose | Group students by weak concept; approve remediation pack |
| Primary user | Teacher |
| Entry | Hub; Analyze |
| Exit | Prepare Again / Assign |
| Key actions | Edit groups; approve pack; schedule |
| Dependencies | Capability orchestration, Memory |
| AI opportunities | Differentiated practice kits |

### SCR-IMPROVE-COMMUNICATE

| Field | Definition |
|-------|------------|
| Purpose | Draft parent / class messages for approval |
| Primary user | Teacher |
| Entry | Hub; Today escalation |
| Exit | Sent (after approve) or discard |
| Key actions | Generate draft; edit tone/language; approve send |
| Dependencies | School Context language; parent portal/channels |
| AI opportunities | Fact-based multilingual drafts |

### SCR-IMPROVE-PTM

| Field | Definition |
|-------|------------|
| Purpose | Per-student briefing cards for PTM |
| Primary user | Class teacher |
| Entry | Hub; calendar PTM |
| Exit | Message follow-up |
| Key actions | Review card; annotate; export talking points |
| Dependencies | Attendance, assessments, homework patterns |
| AI opportunities | Briefing synthesis |

### SCR-IMPROVE-REMARKS

| Field | Definition |
|-------|------------|
| Purpose | Evidence-based report remark drafts |
| Primary user | Teacher |
| Entry | Report window |
| Exit | Approved remarks to reporting flow |
| Key actions | Generate; edit each; approve batch |
| Dependencies | Marks, analytics evidence |
| AI opportunities | Personalised remark drafts |

### SCR-IMPROVE-MEMORY

| Field | Definition |
|-------|------------|
| Purpose | View/edit what Teacher Memory believes |
| Primary user | Teacher |
| Entry | Improve hub; Settings |
| Exit | Settings; back |
| Key actions | Correct preferences; reset category |
| Dependencies | Teacher Memory model |
| AI opportunities | Show “learned from your edits” explanations |

*Wireframe:* `../wireframes/IMPROVE.md`

---

## 6. Library

### SCR-LIBRARY-BROWSE

| Field | Definition |
|-------|------------|
| Purpose | Search/filter approved kits, artefacts, sources |
| Primary user | Teacher |
| Entry | Nav Library |
| Exit | Open kit (read-only or duplicate to Prepare); open source |
| Key actions | Search; favorite; duplicate as new Intent; archive |
| Dependencies | Content lifecycle, branding |
| AI opportunities | “Similar to this topic” retrieval |

### SCR-LIBRARY-ITEM

| Field | Definition |
|-------|------------|
| Purpose | Artefact/kit detail with provenance and status |
| Primary user | Teacher |
| Entry | Browse |
| Exit | Duplicate → Prepare; share if already approved policy allows |
| Key actions | Preview; duplicate; download/print |
| Dependencies | Lifecycle status |
| AI opportunities | Refresh kit for new class using Memory |

---

## 7. AI Assistant

### SCR-ASSISTANT-CHAT

| Field | Definition |
|-------|------------|
| Purpose | Natural-language help that resolves to Intent or stage |
| Primary user | Teacher |
| Entry | Nav; global entry |
| Exit | Opens Prepare/Teach/Assess/Improve screens with prefill |
| Key actions | Ask; confirm suggested Intent; open explanation |
| Dependencies | Memory, Context, Intent catalogue |
| AI opportunities | Intent detection; EduAsk; never auto-publish |

*Wireframe:* `../wireframes/AI_ASSISTANT.md`

---

## 8. Settings

### SCR-SETTINGS-ROOT

| Field | Definition |
|-------|------------|
| Purpose | Preferences, Memory, notifications, account, feature flags visibility |
| Primary user | Teacher |
| Entry | Nav Settings |
| Exit | Memory editor; notification prefs |
| Key actions | Edit Memory; toggle preview features (if entitled); language |
| Dependencies | Auth, flags, Memory |
| AI opportunities | None required |

### SCR-SETTINGS-MEMORY

| Field | Definition |
|-------|------------|
| Purpose | Full Teacher Memory control surface |
| Primary user | Teacher |
| Entry | Settings; Improve memory |
| Exit | Root |
| Key actions | Edit fields; export/reset (policy permitting) |
| Dependencies | Memory model |
| AI opportunities | Explain why a preference was inferred |

---

## Screen count sanity

Primary destinations covered; deep editors support Intent/kit without becoming top-level nav.
