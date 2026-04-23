# Fresh Start Review: common-instructions

## Summary of changes
- Initialized repo into normalized root-level structure for shared instruction assets.
- Added foundational shared prompt files, agent role prompts, validator templates, and index.
- Added explicit boundary and ownership documentation in `README.md` and `AGENTS.md`.

## Files created, updated, or removed
### Created
- README.md
- AGENTS.md
- _index.yaml
- boilerplates/codex-boilerplate.md
- review/review-prompt.md
- docs/docs-prompt.md
- audit/repo-audit-prompt.md
- agents/architect-agent.md
- agents/repo-builder-agent.md
- agents/docs-agent.md
- agents/reviewer-agent.md
- validators/decision-principle-validator.md
- validators/execution-review-template.md
- repo-prompts/fresh-start-common-instructions.md
- reviews/fresh-start-common-instructions-review.md

### Updated
- none

### Removed
- none

## Boundary issues found
- Could not retrieve canonical prompt from GitHub raw URL (HTTP 403), so local saved prompt was used as fallback canonical input.
- Required vision document path `../org-docs/vision/vision-document.md` is not present in current environment.

## Risks
- Missing vision document may leave higher-level strategic alignment partially unverified.
- If remote GitHub prompt differs from local saved prompt, minor alignment drift is possible.

## Deferred items
- Re-run alignment check once GitHub prompt access is available.
- Reconcile against vision document once `../org-docs/vision/vision-document.md` is available.

## Common-layer improvements
- Implemented: Added explicit shared-repo boundary guidance and index maintenance rule.
- Suggested follow-up: Add lightweight lint/check script to validate `_index.yaml` file existence entries.
