# Product Offering

## Open-Core Model
- Core application code: open source.
- `common-instructions`, premium policy packs, and continuous improvement loops: closed source.
- Self-hosting with customer API key is supported.

## Plan Matrix

| Capability | Community | Pro | Team | Enterprise |
|---|---|---|---|---|
| Open-source core code | Yes | Yes | Yes | Yes |
| BYO API key | Yes | Yes | Yes | Yes |
| Closed-source `common-instructions` | No | Yes | Yes | Yes |
| Continuous improvement updates | No | Monthly | Weekly | Custom |
| Tools/skills access | Limited | Standard | Advanced | Full + custom |
| Policy enforcement | No | Yes | Yes | Yes |
| SSO | No | No | Optional add-on | Yes |
| Traces/trace pipeline | No | Yes | Yes | Yes |
| LLM gateway | No | Yes | Yes | Yes |
| Code-reviewer model gateway + auto-route policy | No | Yes | Yes | Yes |
| Air-gapped/offline bundle | No | No | No | Yes (or custom contract) |
| Notifications/email/webhooks/API/MCP | Limited | Yes | Yes | Yes |
| Mandatory pre-prod demo + HITL sign-off | No | Yes | Yes | Yes |
| Support | Community | Email | Priority + SLA | Dedicated + SLA |

## Pricing
- Community: `$0`
- Pro: `$49/month` per workspace
- Team: `$199/month` per workspace (up to 10 users)
- Enterprise: custom (`starting at $999/month`)

## Governance and Enforcement
- Production deployment: CI/CD-only.
- Registry-first for models, prompts, skills, and service artifacts.
- Unique IDs and traces for actions/reviews in paid tiers.
- Issue tracking and deterministic auto-assignment required.

## Testing and Quality
- Required test layers: unit, integration, smoke, E2E.
- UI-facing releases require functional testing, usability testing, and UX review.
- Security and vulnerability checks are release gates.

## Long-Running Orchestration Support
- LangGraph state-based flows
- HITL checkpoints
- Loop/branch orchestration
- Tool approval gates
- RAG context enrichment
- Auto skill/tool discovery (registry-scoped)

## Contract Boundary
- This file is an operational product summary.
- Final legal and commercial terms are governed by signed agreements.
