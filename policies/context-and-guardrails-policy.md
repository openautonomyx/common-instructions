# Context and Guardrails Policy

## Purpose
Define strict context management and guardrail behavior so agents stay accurate, safe, and prioritized.

## Context management rules
- Maintain a single active task context with explicit `task_id`, `priority`, `state`, and `owner`.
- Before asking clarifying questions, check existing memory/context artifacts first.
- Reuse prior decisions when still valid; avoid re-requesting known inputs.
- If context is missing or conflicting, ask a focused clarification instead of guessing.
- On each major action, append a short context update including current state and next step.

## Dynamic context rules
- Load only required context for the current task step.
- Keep a rolling context window with goals, constraints, assumptions, blockers, identifiers, and latest decisions.
- Persist durable decisions to memory; keep transient details in task state.
- Do not switch context unless reprioritization is explicitly recorded.

## Dynamic context window expansion
- Start with minimal relevant context and expand incrementally when complexity or ambiguity increases.
- Expansion order: current task state -> linked decisions/memory -> dependent specs/docs -> external constraints.
- Shrink context after decision checkpoints to keep execution focused and reduce drift.
- Log each expansion/reduction event with reason and affected artifacts.

## Guardrail rules
- Never execute destructive actions without explicit confirmation.
- Never expose or store secrets in code, logs, docs, or commit messages.
- Use registry-first resolution for models, prompts, skills, and service artifacts.
- Block deployment when required quality/security gates fail.
- Prefer deterministic, auditable workflows over ad hoc/manual steps.

## Enforcement checklist
- Context snapshot updated for each task transition.
- Clarifications asked when ambiguity is material.
- Guardrail checks passed before merge/deploy.
- Violations logged with `action_id`, `trace_id`, and remediation owner.

## Long-running flow controls
- Maintain explicit workflow state for loops, branches, and retries.
- Require HITL approval for high-risk branches and privileged tools.
- Enforce tool-approval checkpoints before sensitive operations.
- Use RAG only from approved indexed sources with provenance.
- Auto-discovery of tools/skills must be registry-scoped and policy-filtered.

## Integration guardrails
- Notifications/email/webhooks must use approved providers and signed secrets.
- API and MCP integrations must be authenticated, authorized, and auditable.
- Webhook and API failures must produce retry-safe events and traceable logs.
