# EBP-001.4 — Files Changed (Review Queue Entry)

## Quiz-React — added

| Path | Purpose |
|------|---------|
| `src/features/teacher-os/artifacts/types.ts` | ADR-046 lifecycle + ArtifactProgressItem / ArtifactService |
| `src/features/teacher-os/artifacts/adapters/mockArtifactService.ts` | Mock checklist source (`MOCK_PREPARING_ARTIFACTS`) |
| `src/features/teacher-os/review-entry/components/ArtifactProgressCard.tsx` | Single artifact row |
| `src/features/teacher-os/review-entry/components/ArtifactChecklist.tsx` | Data-driven checklist |
| `src/features/teacher-os/review-entry/components/ApprovalNotice.tsx` | Review-before-publish principle |
| `src/features/teacher-os/review-entry/components/OpenReviewButton.tsx` | CTA → `/teacher-os/review` |
| `src/features/teacher-os/review-entry/components/ReviewQueueEntryCard.tsx` | Entry card + EBP-001.5 notice |
| `src/features/teacher-os/review-entry/pages/PreparingKitPage.tsx` | PreparingYourKitPage |
| `src/features/teacher-os/review-entry/pages/ReviewQueuePlaceholderPage.tsx` | Placeholder only |
| `src/features/teacher-os/review-entry/styles/ReviewEntry.module.css` | Styles |
| `tests/teacherOs.reviewEntry.test.tsx` | Unit |
| `tests/e2e/teacher-os.review-entry.spec.ts` | Playwright |

## Quiz-React — modified

| Path | Purpose |
|------|---------|
| `src/App.tsx` | Routes: PREPARING_KIT, REVIEW → new pages |
| `src/features/teacher-os/constants/routes.ts` | `PREPARING_KIT` |
| `src/features/teacher-os/routes/paths.ts` | Alias for preparingKit |
| `src/features/teacher-os/index.ts` | Exports |
| `src/features/teacher-os/intent/components/IntentWizard.tsx` | Continue → preparing kit |
| `src/features/teacher-os/telemetry/TeacherTelemetry.ts` | Entry / preparing / opened events |
| `tests/teacherOs.intent.test.tsx` | Continue lands on preparing kit |
| `tests/teacherOs.paths.test.ts` | PREPARING_KIT + REVIEW constants |

## Product docs

| Path | Purpose |
|------|---------|
| `engineering/EBP-001/*.md` | Review package refresh for 001.4 |
| `reviews/review-packages/EBP-001/*` | Summary / checklist / changed files |
