# Coding Standards

**ID:** ENG-CODE-001  
**Parent:** ENGINEERING_CONSTITUTION.md  
**Applies to:** `Quiz-React` · `eduvijna-api`

---

## 1. Folder conventions

### Web (`Quiz-React`)

```text
src/features/teacher-os/
  routes/
  components/
  hooks/
  api/
  context/          # Continuous Context
  types/            # Artifact, Work, Intent types
src/config/teacherOsFeature.ts
```

- Teacher OS code lives in `features/teacher-os/` — not scattered into unrelated legacy folders.  
- Deep-link existing generators in `features/platform-ai/` — **do not copy** generator engines.  
- Shared primitives stay in existing component libraries.

### API (`eduvijna-api`)

```text
app/api/v1/…                 # versioned HTTP
app/domain/…                 # lifecycle / rules
app/platform/feature_flags.py
tests/…                      # mirror package paths
```

- Prefer extending content / generation platform over parallel stacks.  
- Teacher OS aggregates only when needed: `/api/v1/teacher-os/*`.

---

## 2. Naming conventions

| Kind | Convention | Example |
|------|------------|---------|
| React components | PascalCase | `TodaysMission.tsx` |
| Hooks | `use` + camelCase | `useReviewQueue` |
| Feature flags | snake_case | `teacher_os_enabled` |
| API paths | kebab-case | `/api/v1/teacher-os/mission` |
| Types | PascalCase | `Artifact`, `Work` |
| Tests | `*.test.ts(x)` / pytest modules | `review_queue.test.tsx` |
| Telemetry | `domain.action` | `artifact.approved` |

---

## 3. Code structure rules

1. Screens thin; logic in hooks/services.  
2. Domain vocabulary matches product (Artifact / Work / Intent).  
3. No publish-to-students from generator UI — always Artifact approval path.  
4. Prefer small PRs that complete a vertical slice.  
5. Do not drive-by refactor unrelated modules in Teacher OS PRs.  
6. Secrets never committed; use existing env patterns.

---

## 4. TypeScript / Python

- Follow existing project lint/format tooling (ESLint/Prettier, ruff/black or project default).  
- Avoid `any` / untyped escapes in new Teacher OS code without justification.  
- API handlers stay thin; business rules in domain/services.

---

## 5. Comments

- Comment *why*, not *what*.  
- Link PA/EBP IDs when encoding architectural constraints (e.g. “D-016 Artifact lifecycle”).  
