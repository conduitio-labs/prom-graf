# Prometheus and Grafana Deployment for Conduit

This repository contains a simple Docker Compose configuration containing
Prometheus and Grafana.

Prometheus is pre-configured to collect metrics from:

* a local instance of Conduit running on `localhost:8080`.
* a local Node exporter instance running on `localhost:9100`

The scrapes target can be adjusted in the
[Prometheus config](prometheus/config/prometheus.yml#L31).

Grafana is pre-configured to attach to the Prometheus instance and contains
dashboards for monitoring Conduit specific metrics,
generic [Go runtime metrics](https://pkg.go.dev/runtime/metrics), and node
metrics (CPU usage, memory usage, disk I/O, etc.) through
Prometheus' [Node exporter](https://github.com/prometheus/node_exporter).

Note that this is only meant to be used for development purposes.

## How to use

Simply run the docker compose config:

```sh
docker compose up
```

Prometheus is reachable under `localhost:9090`, Grafana is reachable under
`localhost:9091`. To log into the Grafana UI use the username `admin` and
password `admin`.
