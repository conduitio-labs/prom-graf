# Prometheus and Grafana Deployment for Conduit

This repository contains a simple Docker Compose configuration containing
Prometheus and Grafana.

Prometheus is pre-configured to collect metrics from a local instance of
Conduit running on `localhost:8080`. The scrape target can be adjusted in the
[Prometheus config](https://github.com/conduitio-labs/prom-graf/blob/aaa2fb1364d7e2b140cf49145eb2f236ee53f94c/prometheus/config/prometheus.yml#L31).

Grafana is pre-configured to attach to the Prometheus instance and contains
dashboards for monitoring Conduit specific metrics as well as generic [Go
runtime metrics](https://pkg.go.dev/runtime/metrics).

Note that this is only meant to be used for development purposes.

## How to use

Simply run the docker compose config:

```sh
docker compose up
```

Prometheus is reachable under `localhost:9090`, Grafana is reachable under
`localhost:9091`. To log into the Grafana UI use the username `admin` and
password `admin`.
