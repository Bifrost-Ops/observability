# Grafana as code

- `dashboards/bifrost-platform-overview.json` is a version-controlled starter dashboard.
- `provisioning/datasources/prometheus.example.yaml` is an example, **not production values**.

## Provisioning workflow
1. Deploy and validate Prometheus and kube-state-metrics/node-exporter.
2. Ensure each scraped series receives a reliable `cluster` label (`management` or `service`); otherwise the dashboard will show no data.
3. Replace the datasource placeholder and use TLS/authentication appropriate to the environment.
4. Provision dashboard JSON using a pinned Grafana Helm chart and ConfigMap/sidecar or Grafana's provisioning mechanism.
5. Verify queries and panel cardinality; capture a screenshot and alert validation.
6. Roll back by reverting the Git revision, reconciling the dashboard, and verifying no unexpected datasource changes.

Historical metrics live in storage, **not** in Git.
