# Contributing to EduVijna Product

Contributions to this Product Office repository must preserve product-intelligence integrity, traceability, and reviewability.

These rules mirror the contribution rules of [eduvijna-architecture](https://github.com/eduvijna-ai/eduvijna-architecture), adapted for product research and product architecture (not EAO governance directories).

## Rules

### No implementation code

Do not add application source code, scripts that implement product behaviour, infrastructure-as-code for product runtimes, executable services, React/UI code, APIs, databases, prompts, or AI workflow implementations.

This repository is for **product intelligence** and **product architecture** artefacts only.

### Pull Request required

All changes land through a pull request to the default branch. Direct commits to `main` are not permitted under normal process.

### Product Architecture Review required

Material changes to product architecture, Teacher OS models, capability orchestration, roadmaps, success metrics definitions, or review packages require **Product Architecture Review** before approval.

Material changes to research foundations (personas, journeys, JTBD, pain points, opportunities) require Product Office review; treat them as inputs that may trigger a follow-on PA review if architecture must change.

Editorial corrections may follow a lighter review path when they do not alter meaning.

### Stable artifact IDs

Assigned artefact identifiers (e.g. `TLM-001`, `PA-001`, `PERSONA-TEACHER-001`, `JTBD-A1`) are stable. Do not reuse, renumber, or silently repurpose IDs. If an artefact is superseded, retain history and mark status appropriately.

### Markdown quality

- Use clear headings and concise prose
- Prefer tables where they improve scanability
- Ensure links resolve within the repository
- Prefer document headers with `id`, `status`, `version`, and ownership where established by existing packages

### Cross references

Link related artefacts by stable ID and path. Prefer repository-relative links. Keep terminology aligned with Teacher OS vocabulary (Teaching Intent, Teacher Memory, School Context, Daily Learning Loop).

### Versioning expectations

- Update artefact `version` when meaning changes
- Record consumer-visible repository changes in `CHANGELOG.md` when that file is present
- Do not silently rewrite approved review outcomes

## Workflow

1. Open an issue for non-trivial work.
2. Create a descriptive branch from `main`.
3. Make focused changes within the correct directory.
4. Update review packages when delivering a reviewable unit of work.
5. Open a pull request using the PR template.
6. Request review from owners in `CODEOWNERS`.
7. Merge only after required approvals.

## Contribution types

| Type | Process |
|------|---------|
| Product research (personas, journeys, JTBD, pains, opportunities) | PR + Product Office review |
| Product architecture / Teacher OS / orchestration | PR + Product Architecture Review |
| Review packages (`TLM-*`, `PA-*`) | PR + Product Architecture Review when material |
| Metrics / roadmap definitions | PR + Product Architecture Review |
| Editorial | Lightweight PR |

## Review checklist

Reviewers verify:

- Correct directory placement and ownership
- No implementation code introduced
- Stable IDs preserved
- Cross-references and terminology consistency
- Markdown quality and working links
- Product Architecture Review completed when required
- Constraints respected (no UI/API/DB/prompt/implementation leakage)

## Questions

Use a General or Product change issue template, or contact the EduVijna Product Office through EduVijna leadership channels.
