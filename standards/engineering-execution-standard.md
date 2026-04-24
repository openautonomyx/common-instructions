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

## 10) Continuous improvement loops
- Every agent must run a feedback/self-improvement loop after major execution cycles.
- For design work, include a UI-improvement loop based on implementation and user feedback.
- Convert repeated issues into enforceable checks in standards/policies.

## 11) Memory and context loops
- Maintain a memory loop: capture durable lessons, decisions, and recurring fixes after each major cycle.
- Maintain a context loop: update active context state (priorities, blockers, assumptions, identifiers) continuously.
- Reuse existing memory/context before asking for repeated inputs.

## 12) Guardrails and dynamic context
- Enforce single active task context with explicit state and priority.
- Prefer clarification over guessing when ambiguity is material.
- Apply guardrail checks before risky actions and before merge/deploy.
- Keep context snapshots current at each task transition.
- Expand or shrink context window deliberately based on complexity and risk.

## 13) Testing and process improvement
- Improve test suites continuously across unit/integration/smoke/E2E layers.
- Include negative, boundary, regression, and recovery scenarios.
- Include usability testing, functional testing, and UX review before release for UI-facing products.
- Run post-release process reviews and convert repeated failures into automated checks.

## 14) Air-gapped readiness
- All agents and products must support an offline/air-gapped operating mode.
- Validate critical workflows in network-restricted simulation before release.
- Resolve dependencies from approved internal mirrors/registries.

## 15) Long-running orchestration capabilities
- Support LangGraph state-based orchestration for long-running workflows.
- Support HITL checkpoints and approvals on sensitive branches.
- Support loop/branch patterns with deterministic state transitions.
- Support tool approval gates before execution of privileged tools.
- Support RAG-backed retrieval for context enrichment.
- Support automatic skill and tool discovery via registry-first lookup.

## 16) Integration channels
- Support outbound notifications and email dispatch for workflow events.
- Support webhook triggers and webhook callbacks with signature verification.
- Expose API interfaces for orchestration and status access.
- Support MCP-based tool integrations for extensible agent operations.
