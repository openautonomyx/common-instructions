# Air-Gapped Operation Policy (All Agents)

## Purpose
Ensure all agents can operate in restricted or disconnected environments without relying on external network access.

## Mandatory requirements
- Every agent workflow must define an air-gapped execution mode.
- Prefer local mirrors/registries for packages, models, images, and artifacts.
- Support offline configuration for model, prompt, skill, and policy resolution.
- Bundle required dependencies and reference data as versioned internal artifacts.
- Fail fast with actionable guidance when a required offline dependency is missing.

## Implementation standards
- No hard dependency on live internet for critical-path execution.
- Provide fallback paths for telemetry, notifications, and integrations in offline mode.
- Use deterministic build inputs and pinned versions for reproducibility.
- Maintain an offline bootstrap document and validation checklist per product.

## Validation and gates
- CI must include an air-gapped simulation stage (network-disabled or mocked mirrors).
- Release is blocked if air-gapped smoke checks fail for critical workflows.
- Record test evidence and trace IDs for air-gapped validation runs.
