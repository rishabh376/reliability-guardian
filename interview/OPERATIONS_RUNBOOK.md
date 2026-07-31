# Operations Runbook - reliability-guardian

Service Reliability Owners coordinate forecast error budget burn for shared platform dependencies, so game days create tracked reliability work.

**On-call? Read this first.**

## Deploy
```
kubectl apply -k k8s/ -n reliability-guardian
kubectl rollout status deploy/reliability-guardian -n reliability-guardian
```

## Rollback (when things go red)
```
./scripts/rollback.sh
# usually < 30sec
```

## Scale up NOW
```
kubectl scale deploy/reliability-guardian --replicas=10 -n reliability-guardian
```

## Logs
```
kubectl logs -l app=reliability-guardian -n reliability-guardian -f --tail=200
```

## Crashloop?
```
kubectl describe pod -l app=reliability-guardian -n reliability-guardian
kubectl logs <pod> --previous -n reliability-guardian
```
90% of the time: missing env var in ConfigMap.

## Metrics
`curl localhost:8080/metrics` or Grafana dashboard in `monitoring/`

## DR / Failover
See `docs/DISASTER_RECOVERY.md` - RTO 15m

We actually tested this. 11 min.
