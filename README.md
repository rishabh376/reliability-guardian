# reliability-guardian

> Service Reliability Owners coordinate forecast error budget burn for shared platform dependencies, so game days create tracked reliability work.

**Domain:** sre | **Complexity:** intermediate | **Stack:** Go, Prometheus, Grafana, Chaos Mesh, Argo Rollouts, OTel

| | |
|---|---|
| Use case | Service Reliability Owners coordinate forecast error budget burn for shared platform dependencies, so game days create tracked reliability work. |
| Pain point | Error budget burn is discussed after customers already feel the latency. |
| Success metric | Convert every game day finding into an owned ticket within 5 minutes. |
| Cost | $0/mo on Fly.io |

## Why this exists

Error budget burn is discussed after customers already feel the latency.. Service Reliability Owners coordinate forecast error budget burn for shared platform dependencies, so game days create tracked reliability work.

> This production platform is designed for reliability, error budgets, and repeatable recovery drills. For this implementation, the service is designed to remove the operational friction behind Service Reliability Owners coordinate forecast error budget burn for shared platform dependencies, so game days create tracked reliability work..

## What this product does

This project ships a production-oriented service that exposes health, readiness, observability, and domain-specific endpoints for Service Reliability Owners coordinate forecast error budget burn for shared platform dependencies, so game days create tracked reliability work.. The implementation is intended to be deployed behind Kubernetes with secure defaults, CI validation, and rollback-ready manifests.

## Quick start

```bash
docker build -t reliability-guardian:local .
docker run -p 8080:8080 reliability-guardian:local
curl http://localhost:8080/healthz
```

## Architecture

```
GitHub CI -> Container Registry -> Kubernetes -> Go -> Operators / SRE
```

See `docs/ARCHITECTURE.md`

## Infrastructure

Full spec: `terraform/INFRA_REQUIREMENTS.md`

TL;DR: K8s cluster, 2-10 pods HPA, $0 on Fly.io

## Docs

- `docs/ARCHITECTURE.md` - components, tradeoffs
- `docs/DESIGN_DISCUSSION.md` - how we decided to build this
- `docs/DEPLOYMENT.md` - GitOps, rollback
- `docs/SECURITY.md` - threat model
- `docs/TROUBLESHOOTING.md` - 3am runbook
- `terraform/INFRA_REQUIREMENTS.md` - **infra: CPU/RAM/storage/cost**

Interview prep: `interview/`
