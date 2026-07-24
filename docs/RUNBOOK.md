# Runbook

## Service

- Name: `source-api`
- Team: `Platform Engineering`
- Owner: `mooref068@gmail.com`
- Cost center: `platform-engineering`

## First Checks

```bash
kubectl get rollout source-api -n source-api-dev
kubectl get pods -l app.kubernetes.io/name=source-api -n source-api-dev
kubectl logs -l app.kubernetes.io/name=source-api -n source-api-dev
```

## Health

```bash
curl https://source-api.dev.platform.ohanyere.internal/healthz
curl https://source-api.dev.platform.ohanyere.internal/readyz
curl https://source-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo source-api -n source-api-dev
```

Escalate to `Platform Engineering` through `mooref068@gmail.com` if rollback does not restore service.
