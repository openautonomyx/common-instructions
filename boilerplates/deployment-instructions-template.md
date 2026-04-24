# Deployment Instructions Template

## Objective
Define a repeatable deployment runbook for a single service/repo.

## In scope
- Service-specific deployment steps.
- Runtime environment variables required for startup.
- Health check endpoint and expected response contract.
- Domain and TLS requirements for public exposure.

## Out of scope
- Organization-wide policy and governance.
- DNS provider account automation scripts.
- Multi-service platform orchestration unless explicitly requested.

## Required sections
1. Deployment target
- Runtime platform (for example: Coolify, Kubernetes, ECS).
- Artifact source (image/repo/tag).

2. Runtime settings
- Container/app port.
- Required env vars.
- Persistent volumes/state paths (if any).

3. Networking and security
- Public hostname.
- TLS mode/certificate resolver.
- Ingress/reverse proxy assumptions.

4. Health and verification
- Health endpoint path.
- Expected HTTP status/body.
- Post-deploy verification command.

5. Rollback
- Previous stable tag/artifact reference.
- Minimal rollback steps.

## Output contract
- Final deployment configuration values (explicit, copy-paste ready).
- Exact commands or exact UI fields to set.
- Verification result and known risks.
