# Grafana Dashboards for Grafana

> **Work in progress.** These dashboards are under active development. Layouts, panel queries, and field references may change without notice.

Grafana dashboards for monitoring Grafana itself. Designed for use with an Elasticsearch backend datasource and data collected by standard Elastic Agent integrations (Fleet-managed).

## Dashboards

| ID | Title | Description |
|---|---|---|
| GF-00 | Service Overview | Grafana instance health, uptime, request rates |
| GF-01 | Grafana Metrics | Internal Grafana metrics, API performance, active sessions |
| GF-02 | Host Metrics | CPU, memory, disk, network for the Grafana host |

## Data Sources

These dashboards use template variables for datasource selection, so they work with any Elasticsearch datasource name or UID. The expected data comes from:

- **Elastic Agent** `system` integration (host-level metrics for GF-02)

Some dashboards also use the [Infinity datasource](https://grafana.com/grafana/plugins/yesoreyeram-infinity-datasource/) to query the Grafana HTTP API directly for health status, org info, and other metadata not available through the metrics pipeline. These panels are optional — dashboards work without them but will show empty panels where Infinity is not configured.

## Installation

Copy the JSON files from `dashboards/` into Grafana via the UI import, the HTTP API, or the [grafana-dashboards-role](https://github.com/Oddly/grafana-dashboards-role) Ansible role.
