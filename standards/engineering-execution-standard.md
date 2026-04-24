# Engineering Execution Standard (Concrete)

## 1) Pre-task gate (mandatory)
Before any implementation starts, publish:
- Recommended model (primary + fallback) with cost/speed/quality rationale.
- Task list with statuses: `pending`, `in_progress`, `blocked`, `done`.
- Priority order and current active task.

## 2) Pre-project research gate (mandatory)
Before any new project:
- Compare at least 2 architecture options.
- Record risk, cost, speed, and operational complexity tradeoffs.
- Select one approach with explicit rationale.

## 3) Execution discipline
- No context switching unless explicitly reprioritized.
- Maintain strict priority order.
- Long-running tasks must run in background; continue non-blocking foreground tasks.
- Rejoin background tasks only at checkpoints or when blocking.

## 4) Documentation and repository completeness
Each product repo must contain:
- PRD
- Design doc
- HLD
- DB schema docs
- Prompt registry/docs
- Seed data spec/scripts (if applicable)

## 5) Deployment policy
- Production deploys are CI/CD-only.
- No direct/manual production server deploys.
- Required gates: tests, vulnerability scan, smoke test, critical-path E2E.

## 6) Registry-first policy
- Resolve model/skill/prompt/service-image from registry first.
- If missing: register first, then use.
- Registry entries must include canonical IDs.

## 7) Traceability and IDs
Every review/action event must include:
- `review_id`
- `action_id` (unique per action)
- `trace_id`
- `agent_id`
- `version` (for mutable entities)
- `span_id` (if tracing enabled)

## 8) Security and config hygiene
- All env vars declared in env templates (for example `.env.example`).
- Secrets only in secret manager, never in git.
- Use immutable artifact tags for releases.

## 9) Multi-agent responsibilities
- `code-assist`: authors/maintains docs.
- `code-reviewer`: reviews PRD/HLD/LLD/code.
- `code-tester`: validates docs + testing outcomes.
- Reviews must include teaching-oriented feedback for subagent improvement.
