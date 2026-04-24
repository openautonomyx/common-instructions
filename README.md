# common-instructions

Shared instruction layer for `openautonomyx` repositories.

## Why this repo exists

`common-instructions` centralizes reusable instruction assets (prompts, agent role guides, validators, and boilerplates) so teams can stay aligned without duplicating guidance across many repos.

## What belongs here

- Shared boilerplates for instruction-driven execution
- Shared review, docs, and audit prompts
- Shared agent role prompts (architect, builder, docs, reviewer)
- Shared validator prompts and review templates
- Small, explicit documentation about this repo's structure and boundaries

## What does **not** belong here

- Vision docs or org strategy source documents
- Platform/product-specific prompts
- Application or infrastructure code
- Binary or design asset libraries
- Shared executable code/config artifacts managed elsewhere

## Relationship to sibling repositories

- `org-docs`: source-of-truth organizational vision/policy docs. This repo references those docs but does not duplicate them.
- `shared-assets`: non-code shared assets (media, templates, brand files), not instruction prompts.
- `shared-repos`: reusable code/config packages; this repo stores instruction content only.

## Repository layout

- `boilerplates/` reusable base prompt boilerplates (execution + deployment templates)
- `review/` review prompt assets
- `docs/` documentation prompt assets
- `audit/` audit prompt assets
- `agents/` role-specific agent prompts
- `validators/` validation and execution review templates
- `repo-prompts/` run-specific canonical prompt captures
- `reviews/` execution review notes

## Maintenance principles

- Keep the structure flat and explicit at root.
- Prefer small, composable prompt files.
- Update `_index.yaml` whenever files are added/removed.
- Record execution deltas and follow-ups in `reviews/`.

## Key boilerplates

- `boilerplates/codex-boilerplate.md`
- `boilerplates/deployment-instructions-template.md`


## Standards
- `standards/engineering-execution-standard.md`


## Agent presets
- `agents/document-agent.md`
- `agents/design-agent.md`

- `agents/technical-writer-agent.md`
- `agents/product-designer-agent.md`


## Policies
- `policies/technical-writer-policy.md`
- `policies/product-designer-policy.md`
