# EBP-001.5 — Files Changed (Review Queue)

## Quiz-React — added

| Path | Purpose |
|------|---------|
| `src/features/teacher-os/review/pages/ReviewQueuePage.tsx` | Review Queue page |
| `src/features/teacher-os/review/hooks/useReviewQueue.ts` | Load / filter / actions |
| `src/features/teacher-os/review/components/*` | Filters, list, detail |
| `src/features/teacher-os/review/styles/ReviewQueue.module.css` | Styles |
| `tests/teacherOs.reviewQueue.test.tsx` | Unit |
| `tests/e2e/teacher-os.review-queue.spec.ts` | Playwright |

## Quiz-React — modified

| Path | Purpose |
|------|---------|
| `artifacts/types.ts` | ReviewArtifact, reviewDecision, filters, service ops |
| `artifacts/adapters/mockArtifactService.ts` | Mock queue + approve/reject/requestChanges |
| `App.tsx` | REVIEW → `ReviewQueuePage` |
| `index.ts` | Exports |
| `telemetry/TeacherTelemetry.ts` | Review events |
| `mission/.../PendingReviewsCard.tsx` | Link to queue |
| `mission/adapters/mockMissionAdapter.ts` | Pending count from seed |
| `review-entry/.../ReviewQueueEntryCard.tsx` | Opens live queue |
| Prior intent/review-entry tests | Expect real queue |

## Architecture / Product

| Path | Purpose |
|------|---------|
| `ADR-048-…` | Implementation note for EBP-001.5 + reject modeling |
| `engineering/EBP-001/*` | Review package refresh |
