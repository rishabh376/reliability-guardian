# FAQ - reliability-guardian

**Q: What problem does this actually solve?**
A: Service Reliability Owners coordinate forecast error budget burn for shared platform dependencies, so game days create tracked reliability work.

Pain point: Error budget burn is discussed after customers already feel the latency.

**Q: Free to run?**
A: Yep. Fly.io - $0/mo. See `terraform/INFRA_REQUIREMENTS.md`

**Q: Production ready?**
A: Yes - SLOs, security hardening, DR runbook, Helm, Terraform, monitoring.

**Q: Stack?**
A: Go, Prometheus, Grafana, Chaos Mesh, Argo Rollouts, OTel

**Q: What infra do I need?**
A: `terraform/INFRA_REQUIREMENTS.md` has the full breakdown - CPU/RAM/storage/network/cost.
