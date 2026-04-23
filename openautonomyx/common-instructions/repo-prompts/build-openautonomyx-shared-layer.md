# build-openautonomyx-shared-layer

## Source of Truth Order
1. GitHub-stored prompt
2. PRD
3. AGENTS.md
4. verified repo reality
5. older docs or comments

## Execution Mode
foundation

## Non-Assumption Rule
Do not assume files, prompts, services, prior code, prior outputs, or prior structure exist unless verified in repos.

## Repos in Scope
- openautonomyx/common-instructions
- openautonomyx/shared-assets
- openautonomyx/shared-repos
- openautonomyx/org-docs

## Prompt Registry Path
openautonomyx/common-instructions/repo-prompts/build-openautonomyx-shared-layer.md

## PRD Path
openautonomyx/org-docs/prd/high-level-prd.md

## Task Objective
Build and normalize the entire shared OpenAutonomyX layer across common-instructions, shared-assets, shared-repos, and org-docs. Make OpenAutonomyX the clean shared control layer above OpenDataWorld and AgentNxt.

## Product Boundary
Owns shared instructions, shared assets/templates, shared code/config/deploy artifact structure, org-wide docs structure, PRD placement, and explicit repo boundaries.

Does not own OpenDataWorld or AgentNxt product apps or platform-specific prompt registries.

## Required Work
1. Inspect all 4 repos and verify current structure.
2. Normalize each repo to intended responsibility.
3. Create/update README.md in each repo.
4. Create/update _index.yaml in common-instructions, shared-assets, shared-repos.
5. Create/normalize required folder structures.
6. Remove/avoid duplicated shared content.
7. Make boundaries explicit and non-overlapping.
8. Move or document misplaced content.
9. Create review notes at openautonomyx/org-docs/reviews/build-openautonomyx-shared-layer-review.md.

## Constraints
- do not duplicate shared files across repos
- do not store actual PRD in common-instructions
- do not put platform-specific product prompts in openautonomyx repos
- do not invent product features for OpenDataWorld or AgentNxt
- keep structure small, explicit, maintainable

## Required Deliverables
- normalized structures for all 4 repos
- README.md for all 4 repos
- _index.yaml for common-instructions, shared-assets, shared-repos
- shared instruction files in common-instructions
- starter structures for shared-assets and shared-repos
- org docs structure in org-docs
- review note in org-docs/reviews
