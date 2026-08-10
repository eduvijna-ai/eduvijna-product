# Engineering Decision Records (EDRs)

**ID:** ENG-EDR-PROCESS  
**Parent:** ENGINEERING_CONSTITUTION.md (v1.0)  
**Purpose:** Document **implementation** decisions that do **not** change approved architecture

---

## Why EDRs exist

Architecture Decisions (ADRs) live under EAO / product architecture governance.

**EDRs** record how engineers implement within that architecture — without diluting architectural governance.

| Record | Changes architecture? | Where |
|--------|----------------------|-------|
| **ADR** (or PA decision / architecture ADR) | Yes — product/system architecture | Architecture / Product Architecture process |
| **EDR** | No — implementation choice only | `engineering/edrs/` |

**Rule:** If an implementation choice would change architecture, it **must** become an ADR (or Product Architecture update) — **not** an EDR.

---

## When to write an EDR

Write an EDR when the choice:

- Affects multiple files/sprints and future engineers need the rationale  
- Selects among valid options that all preserve PA-001  
- Is non-obvious (e.g. Context vs Redux vs query cache for session scope)

Skip EDRs for trivial local choices (variable names, obvious library defaults already in CODING_STANDARDS).

---

## Lifecycle statuses

| Status | Meaning |
|--------|---------|
| Proposed | Under discussion |
| Accepted | Binding for implementation |
| Superseded | Replaced by a later EDR (link it) |
| Deprecated | No longer recommended; migration noted |

---

## Process

1. Author `engineering/edrs/EDR-NNNN.md` from the template.  
2. Confirm explicitly: **does not change architecture**.  
3. Engineering review (can be part of the implementing PR).  
4. Mark **Accepted** when merged.  
5. Reference EDR id in PR description and code comments where helpful.

---

## Template

See [`TEMPLATE.md`](TEMPLATE.md).

---

## Index

| ID | Title | Status |
|----|-------|--------|
| [EDR-001](EDR-001-continuous-context-react-context.md) | Use React Context for session-scoped Continuous Context | Accepted |

---

## Related

- Constitution: Preserve Architecture; Constitutional Freeze  
- ADRs: `eduvijna-architecture` decisions (EAO) · Product Architecture decisions in PA review packages  
