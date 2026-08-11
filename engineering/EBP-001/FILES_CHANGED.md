# EBP-001.8 — Files Changed

## Quiz-React — modified

| Path | Purpose |
|------|---------|
| `src/features/teacher-os/context/TeacherOsContext.tsx` | One-shot `my-school` hydrate → `school.name`; optional test `fetchMySchool` |
| `src/features/teacher-os/mission/components/SchoolContextCard.tsx` | Authoritative name + Current* labels |
| `src/features/teacher-os/mission/components/TeacherContextCard.tsx` | Current* labels (no Memory) |
| `src/features/teacher-os/index.ts` | Export provider prop types |
| `tests/teacherOs.context.test.tsx` | Hydration / failure / card tests |
| `tests/e2e/teacher-os.school-context.spec.ts` | Playwright scenarios 1–4 |

## Unchanged (by design)

| Area | Note |
|------|------|
| MissionService / mock adapter | No school payload |
| ContinuousContext | Untouched |
| eduvijna-api | No new API; my-school reused |
| Database | No migrations |

## Product docs

| Path | Purpose |
|------|---------|
| `engineering/EBP-001/*` | EBP-001.8 review package |
