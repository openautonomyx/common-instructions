Before doing any work:

1. Save this prompt to:
   repo-prompts/fresh-start-common-instructions.md

2. Read the saved prompt back from GitHub.

3. Use the GitHub-stored version as the canonical prompt for execution.

4. Read the required Vision Document from GitHub:
   ../org-docs/vision/vision-document.md

5. Read the active repo guidance file if present:
   AGENTS.md

6. Then execute the task.

## Execution Identity

Org:
openautonomyx

Repo:
common-instructions

Executor:
Codex

## Repo Identity Rule

This is the only repo being operated on in this run.

Treat the current repository root as the working root.

Do not:
- create a nested `openautonomyx/` directory
- scaffold sibling repos such as `org-docs`, `shared-assets`, or `shared-repos` inside this repo
- treat this repo as a monorepo workspace

Only create and organize files at the root of the current repository.

## Source of Truth Order

1. GitHub-stored prompt
2. Vision Document
3. AGENTS.md
4. verified repo reality
5. older docs or comments

If any of these conflict:
- do not guess
- state the conflict explicitly
- make the smallest correction that improves alignment

## Execution Mode

foundation

## Non-Assumption Rule

Do not assume any prior structure in this repo is correct.
Treat this task as a fresh start for `openautonomyx/common-instructions`.

## Repo

common-instructions

## Prompt Path

repo-prompts/fresh-start-common-instructions.md

## Vision Document Path

../org-docs/vision/vision-document.md

## AGENTS Path

AGENTS.md

## Output Paths

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
- repo-prompts/
- reviews/fresh-start-common-instructions-review.md

## Review Path

reviews/fresh-start-common-instructions-review.md

## Task Objective

Build `openautonomyx/common-instructions` from a fresh start as the shared instructions repo for all platform orgs.

## Product Boundary

This task owns:
- shared boilerplates
- shared review/docs/audit prompts
- shared agent-role prompts
- shared validator prompts
- repo structure and documentation for this repo

This task does not own:
- actual vision or org documents
- platform-specific prompts
- platform code
- shared non-code assets
- shared code/config artifacts

## Current State

Verify the repo state, but do not preserve incorrect structure just because it already exists.
If there is bad or misleading structure, replace it with the correct one.

## Target State

The root of this repo should directly contain:

- README.md
- AGENTS.md
- _index.yaml
- boilerplates/
- review/
- docs/
- audit/
- agents/
- validators/
- repo-prompts/
- reviews/

## Required Work

1. Inspect the current repo state.
2. Remove or ignore any incorrect nested scaffolding if present.
3. Normalize the repo into the correct root-level structure.
4. Create or update:
   - README.md
   - AGENTS.md
   - _index.yaml
5. Create or normalize:
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
6. Make README.md explain:
   - why `common-instructions` exists
   - what belongs here
   - what does not belong here
   - how it relates to `shared-assets`, `shared-repos`, and `org-docs`
7. Make `_index.yaml` reflect the actual files present in this repo.
8. Create review notes at:
   - reviews/fresh-start-common-instructions-review.md

## Reuse Rule

Reuse valid existing files or wording only if they fit the correct structure.
Do not preserve incorrect layout just because it exists.

## Common Layer Improvement Rule

If execution exposes weak conventions, unclear boundaries, or missing shared instruction patterns:
- make the smallest useful correction now
- document larger follow-ups in the review note

Do not overengineer.

## Constraints

- do not store the actual Vision Document here
- do not store platform-specific product prompts here
- keep the structure small, explicit, and maintainable

## Required Deliverables

1. normalized repo structure
2. README.md
3. AGENTS.md
4. _index.yaml
5. shared instruction files
6. validator files
7. review note

## Review Note Must Include

- summary of changes
- files created, updated, or removed
- boundary issues found
- risks
- deferred items

## Final Output Format

1. Summary
2. Verified current state
3. Files created/updated
4. Boundary decisions made
5. Risks or conflicts
6. Deferred items
7. Common-layer improvements suggested or implemented
