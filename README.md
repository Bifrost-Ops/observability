# Bifrost Ops — Observability

Reference observability stack for Hubble, Prometheus and Grafana.

## Status
Documentation-first scaffold; no monitoring stack is deployed.

## Objectives
- Observe network flows and policy decisions with Cilium/Hubble.
- Monitor cluster and infrastructure metrics with Prometheus.
- Provide version-controlled Grafana dashboards and alert definitions.
- Keep retention, resource limits and data ownership explicit.

## Operational safeguards
Document metric retention, storage sizing, credential handling and dashboard provisioning. Back up persistent metrics if required; redeploying manifests does not restore historical data.

Follow the [central bootstrap and recovery runbooks](https://github.com/Bifrost-Ops/docs).
