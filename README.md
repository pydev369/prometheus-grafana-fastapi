# 🚀 FastAPI APM – Production Observability Stack

![Python 3.12+](https://img.shields.io/badge/Python-3.12%2B-blue?logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-0.104%2B-green?logo=fastapi)
![Prometheus](https://img.shields.io/badge/Prometheus-Metrics-orange?logo=prometheus)
![Grafana](https://img.shields.io/badge/Grafana-Dashboards-orange?logo=grafana)
![Podman](https://img.shields.io/badge/Podman-Containers-blue?logo=podman)
![License](https://img.shields.io/badge/License-MIT-purple)

> **End-to-end observability for FastAPI services** — metrics, alerts, and dashboards out of the box.  
> Built for **reliability**, **debuggability**, and **low operational overhead**.
 > Batteries included: Docker, testing, linting, and CI-ready structure.
>

(![Dashboard](https://pydev369.github.io/prometheus-grafana-fastapi/docs/dashboard.png))

## ✨ Features

- ✅ **Auto-instrumented HTTP metrics** (latency, errors, RPS)
- ✅ **Pre-configured Grafana dashboard** (RED method: Rate, Errors, Duration)
- ✅ **Critical alerts** (error rate >1.5%, p95 latency >800ms, service down)
- ✅ **Immutable containers** (Podman/Docker compatible)
- ✅ **One-command deployment** (`podman-compose up`)
- ✅ **Smoke tests + load testing script**

## 🚀 Quick Start

### Prerequisites
- Python 3.12+
- [Podman](https://podman.io) (or Docker) with Compose plugin
- [`uv`](https://docs.astral.sh/uv/) (recommended) or `pip`

### 🐳 Running the Stack

```bash
git clone https://github.com/yourname/fastapi-apm.git
cd fastapi-apm

# Install deps (optional for dev)
uv sync --all-extras

# Launch full observability stack

# Start all services
podman-compose up -d

# View logs
podman-compose logs -f

# Stop services
podman-compose down

# Stop and remove volumes
podman-compose down -v

# Verify
curl http://localhost:8000/health
open http://localhost:3000  # Grafana
```

## 📁 Project Structure
```bash
prometheus-grafana-fastapi/
├── .gitignore
├── README.md
├── pyproject.toml
├── Dockerfile
├── compose.yaml               # Podman/Docker compatible
├── prometheus.yml
├── alerts.yml
├── src/
│   └── app/
│       ├── __init__.py
│       ├── main.py
│       └── endpoints/
│           ├── health.py
│           └── compute.py
├── monitoring/
│   └── grafana/
│       └── provisioning/
│           ├── datasources/
│           │   └── prometheus.yaml
│           └── dashboards/
│               ├── provider.yaml
│               └── fastapi.json   # Pre-baked dashboard
├── tests/
│   └── test_smoke.py
└── scripts/
    └── load-test.sh

```

