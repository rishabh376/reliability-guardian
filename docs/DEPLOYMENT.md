# Deployment - reliability-guardian

**Use case:** Service Reliability Owners coordinate forecast error budget burn for shared platform dependencies, so game days create tracked reliability work.

## Infra requirements
→ `terraform/INFRA_REQUIREMENTS.md` - CPU/RAM/storage/network/cost breakdown

## GitOps
Flux watches `main` and reconciles changes automatically.

## Rollback
```
./scripts/rollback.sh
kubectl rollout undo deploy/reliability-guardian -n reliability-guardian
```
Usually < 30 sec.

## Cost
Fly.io - $0/mo

Reliability and safety go hand-in-hand: SLO guardrails, incident runbooks, and control-plane failure mode analysis.
