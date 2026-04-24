# Policy Skill: Identity, OpenFGA, OPA, Decision Logs

## Purpose
Define a reusable policy skill for AutonomyX-style decision intelligence systems.

## Scope
- Identity-aware authorization
- OpenFGA relationship-based access control
- OPA policy evaluation and guardrails
- Decision log capture for audit and replay

## 1) Identity baseline
- Every request must carry a verifiable identity context (`subject_id`, `tenant_id`, `session_id`).
- Identity must be bound to agent and workload context before policy evaluation.
- Anonymous or unverifiable identities must be denied by default.

## 2) OpenFGA authorization model
- Use OpenFGA for relationship checks (`can_read`, `can_write`, `can_approve`, `can_route`).
- Store tuples by canonical object IDs and versioned relation schema.
- Enforce least privilege and explicit delegation expiry.
- Require tuple-level traceability for high-risk actions.

## 3) OPA policy enforcement
- OPA is the decision policy engine for runtime guardrails.
- Evaluate allow/deny plus required obligations (HITL, escalation, evidence).
- Policy packages must be versioned and signed before production use.
- Deny by default when policy data is missing or stale.

## 4) Decision logs
- Every decision event must be logged with:
  - `decision_id`
  - `trace_id`
  - `subject_id`
  - `resource_id`
  - `action`
  - `fga_result`
  - `opa_result`
  - `policy_version`
  - `timestamp`
- Logs must support replay and forensic review.
- Tamper evidence and retention policy are mandatory.

## 5) HITL and approval binding
- High-risk decisions must require HITL approval before execution.
- Approval event must link to the original policy decision and trace.
- Missing approval evidence blocks production action.

## 6) Operational controls
- CI gate: policy unit tests + schema validation + deny-by-default checks.
- Pre-prod gate: demo with HITL sign-off and decision-log evidence.
- Production gate: enforce OPA + OpenFGA + logging health checks.

## 7) Minimum APIs
- `POST /authorize` -> returns FGA + OPA merged decision.
- `POST /decisions/log` -> writes immutable decision log entries.
- `GET /decisions/{decision_id}` -> returns decision trace and evidence.

## 8) Policy skill output contract
- Decision outcome (`allow|deny|require_hitl`)
- Reason codes
- Required obligations
- Audit payload (IDs + versions + signatures)
