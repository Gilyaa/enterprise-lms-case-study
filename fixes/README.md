# Fixes & Adjustments

Fixes to OWL modules that were already running, outside of new feature development.

## 1. Final Status of Assessment Results When Time Runs Out

**Module:** Assessment

**Problem:** When a learner was in the middle of an assessment and the time limit ran out, the `final` status on the assessment result data (`assessment_results`) did not change to `true`, so the learner's result could be considered unfinished by the system.

**Fix:** An auto-finalize mechanism was added as a command, `assessment:finalize-expired-drafts`, which checks active draft attempts (`final = 0`) and finalizes drafts whose working duration or access period has expired, so the `final` value in `assessment_results` becomes `true`. The learner-side views were also adjusted to no longer show drafts that are no longer valid (draft fallback).

**Result:** Fixed and re-verified (verified November 9, 2026): assessments that run out of time are now recorded as completed with `final = true`.

<!-- Add screenshots to the images/ folder if available, then reference them here,
     e.g.: ![Assessment](images/assessment.png) -->
