# Architecture - reliability-guardian

> Service Reliability Owners coordinate forecast error budget burn for shared platform dependencies, so game days create tracked reliability work.

**Pain:** Error budget burn is discussed after customers already feel the latency.  
**Success metric:** Convert every game day finding into an owned ticket within 5 minutes.

## Decision log

We chose K8s + go because the service needs to be deployed, observed, and rolled back under real production conditions. The architecture reflects the operational problem behind Service Reliability Owners coordinate forecast error budget burn for shared platform dependencies, so game days create tracked reliability work.: we need something that ships quickly, is observable, and can be recovered without hand-waving.

We also prioritized Reliability and safety go hand-in-hand: SLO guardrails, incident runbooks, and control-plane failure mode analysis. and We treat observability as a first-class citizen with alerts tuned to what actually matters in an outage. so the architecture is built around real operational signal, not just feature scope.

See `docs/architecture/ADR-001-runtime-choice.md`

## Components

- go service with health, readiness, and domain-specific endpoints for Service Reliability Owners coordinate forecast error budget burn for shared platform dependencies, so game days create tracked reliability work.
- Prometheus metrics and structured logging for operators
- Docker image with non-root runtime and secure defaults
- K8s Deployment + HPA 2-10, 70% CPU
- GitOps (FluxCD) and rollback scripts
- The operational stack implied by the project: Go, Prometheus, Grafana, Chaos Mesh, Argo Rollouts, OTel

## Trade-offs

| Choice | Why | Cost |
|---|---|---|
| K8s over serverless | team expertise, portability, predictable ops | more YAML |
| Self-hosted observability | lower cost than SaaS alternatives | we run it |
| RollingUpdate first | simpler for v0.1, canary later | faster shipping |

## Data flow

```
Client -> Ingress -> Service -> Pod
Pod -> /metrics -> Prometheus -> Alertmanager -> Slack
Domain actions -> API -> logs/metrics -> operators
```

## Scaling

HPA 2-10 pods. Stateless. 50m/64Mi request.

## Why not...

- **Serverless?** Cold start would hurt the main user flow and violate the reliability target.
- **Managed SaaS only?** The project must remain cost-effective and under operational control.
