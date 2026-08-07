# EBP-001 — Dependencies

**ID:** EBP-001-DEPS

---

## 1. Product / architecture dependencies

| Dependency | Location | Need |
|------------|----------|------|
| PA-001 Teacher OS | `product-architecture/` | Nav, Mission, Review Queue, Continuous Context |
| TLM-001 | research artefacts | Teacher principles, JTBD |
| Product Principles | `vision/PRODUCT_PRINCIPLES.md` | AI Assists, Teacher Decides |

Wave 1 implements **shell + queue + context**, not full Phase 1 Prepare Tomorrow depth from roadmap.

---

## 2. Application repositories

| Repo | Depends on |
|------|------------|
| `Quiz-React` (eduvijna-web) | Working auth, MainLayout, Platform AI routes, Vite env |
| `eduvijna-api` | JWT auth, content generate, content list/lifecycle, feature flags, Content AI sessions |

---

## 3. Runtime service dependencies

| Service | Used for |
|---------|----------|
| Auth / PostgREST JWT | Login |
| Platform content + generation coordinator | Worksheet/quiz/lesson artefacts |
| Existing LLM providers already wired | Generation (no new providers) |
| School/tenant context | School Context summary |
| Timetable / ERP APIs (if available) | Mission class counts — **soft dependency** (empty-safe) |
| Content AI sessions | Continuous Context backbone |

---

## 4. Soft vs hard dependencies

| Item | Type | If missing |
|------|------|------------|
| Platform AI generate | **Hard** | Wave 1 Review Queue cannot demonstrate real artefacts |
| Content approval states | **Hard** | Must exist or be minimally completed |
| Timetable/PTM APIs | Soft | Mission shows placeholders / zeros with honest copy |
| Teacher Memory store | Soft | Summary card shows onboarding defaults / profile fields only |
| PPT / Sketch Notes generators | Soft | Omit types from queue until available |

---

## 5. Cross-team dependencies

| Team | Need |
|------|------|
| Product | Flag cohort lists for Pilot schools |
| QA | Regression pack ownership |
| DevOps | Preview/Pilot env flag injection (`FEATURE_FLAGS_JSON`, `VITE_*`) |
| EAO (optional) | Cross-link blueprint in `eduvijna-architecture/blueprints/` if governance requires |

---

## 6. Sequencing constraints

1. Flags (T-001–T-003) before any Teacher OS UI merge to main.  
2. Review Queue API list/approve before claiming Mission “Review →” complete.  
3. Continuous Context after Queue exists (otherwise refine has nowhere to land).  
