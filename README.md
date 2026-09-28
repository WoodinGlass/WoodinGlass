### ML Infrastructure, Data Engineering & AI Systems

Building **differentiable pipelines**, **deterministic ETL**, and **production-minded RAG/agent backends**.<br>
Mathematical transforms · Physics-based distortion · Streaming · PyTorch · Retrieval · Agents · Reproducible ML

<br>

<div align="center">

<a href="https://github.com/WoodinGlass/rag-agent-platform">
  <img src="https://img.shields.io/badge/🤖_rag--agent--platform-0a1410?style=for-the-badge&logo=github&logoColor=e8e0d5" alt="RAG Agent Platform"/>
</a>
<a href="https://github.com/WoodinGlass/math-render-pipeline">
  <img src="https://img.shields.io/badge/🧮_math--render--pipeline-0a1410?style=for-the-badge&logo=github&logoColor=e8e0d5" alt="Math Render Pipeline"/>
</a>
<a href="https://github.com/VynJustHumant/distortion-library">
  <img src="https://img.shields.io/badge/🦴_distortion--library-0a1410?style=for-the-badge&logo=github&logoColor=e8e0d5" alt="Distortion Library"/>
</a>
<a href="https://www.upwork.com/freelancers/YOUR_ID">
  <img src="https://img.shields.io/badge/Upwork-14a800?style=for-the-badge&logo=upwork&logoColor=white" alt="Upwork"/>
</a>

</div>

---

## 🧩 What I Build

**Production-grade pipelines where math, ML, data engineering, and AI meet.**<br>
Deterministic rendering · Physics-based distortion · RAG + agent backends · Batch + streaming ETL · Observability · Tested.

| Project | Description | Stack |
|---|---|---|
| [rag-agent-platform](https://github.com/WoodinGlass/rag-agent-platform) | Production-minded RAG + AI agent backend. Tool-calling, structured JSON output, streaming ingestion, evaluation, benchmarks, full CI. Runs offline by default. | FastAPI, Pydantic, LangGraph, Qdrant, OpenTelemetry, Docker |
| [math-render-pipeline](https://github.com/WoodinGlass/math-render-pipeline) | Deterministic math → PNG + structured metadata. Batch + streaming, observability, multi-cloud IaC, benchmarks. Live demo. | NumPy, Airflow, dbt, Kafka, Postgres, Grafana, Terraform, Streamlit |
| [distortion-library](https://github.com/VynJustHumant/distortion-library) | Physics-based image degradation for CV robustness. Differentiable, reproducible. | PyTorch |

## 🛠 Tech Stack

<div align="center">

**AI / LLM**

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white)
![Anthropic](https://img.shields.io/badge/Anthropic-191919?style=flat-square&logo=anthropic&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-DC244C?style=flat-square&logo=qdrant&logoColor=white)

**ML / Compute**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)

**Data Engineering**

![Airflow](https://img.shields.io/badge/Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694B?style=flat-square&logo=dbt&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![Postgres](https://img.shields.io/badge/Postgres-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Parquet](https://img.shields.io/badge/Parquet-50ABF1?style=flat-square&logo=apacheparquet&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

**Observability**

![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-425CC7?style=flat-square&logo=opentelemetry&logoColor=white)

**Infrastructure**

![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![GCP](https://img.shields.io/badge/GCP-4285F4?style=flat-square&logo=googlecloud&logoColor=white)

**Quality**

![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Hypothesis](https://img.shields.io/badge/Hypothesis-BD1C2B?style=flat-square&logo=python&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

</div>

## ⭐ Featured

### 🤖 rag-agent-platform

> A **production-minded backend** whose payload happens to be RAG + agents.

- **Deterministic core** — idempotent ingestion on `sha256(content) + chunker_version`; re-ingest is a no-op
- **Structured output** — `AgentOutput` enforced via Pydantic v2 (`extra="forbid"`); invalid LLM output hard-fails with a correlation id
- **Two agent backends** — state machine (default) + LangGraph, behind one `AgentBackend` protocol, parity-tested
- **Three vector stores** — Memory / Chroma / Qdrant behind one `VectorStore` ABC, selected by env
- **Streaming ingestion** — `EventSource` protocol with memory / Kafka / S3 adapters, at-least-once + bounded dedup, parallel partitions with consumer-group rebalance hooks
- **Observability** — structured JSON logs, `/metrics` (JSON) + `/metrics/prom` (Prometheus), OpenTelemetry traces (opt-in)
- **Opt-in multi-tenant + limits** — API-key auth with tenant-scoped doc ids; token-bucket rate limit + body size cap
- **Evaluation** — offline retrieval metrics on every PR; Ragas via LLM judge on weekly/manual runs
- **Benchmarks** — 12-doc baseline + 1k-doc synthetic scale; reranker delta with real cross-encoder
- **CI** — lint + type + coverage (`fail_under=89`, ~92% total) + docker smoke + provider smoke (Groq free tier)
- **Docs** — architecture, runbooks, exactly-once, kafka-rebalance, provider-smoke, limitations, portfolio-notes

### 🧮 math-render-pipeline

> Not "math art". A **pipeline** whose payload happens to be math art.

- **Deterministic** — `formula_hash = sha256(spec)` ⇒ byte-identical PNGs
- **Four formulas** — polar harmonics · Cartesian harmonics · moiré interference · damped Lissajous
- **Batch + streaming** — Airflow DAG + Kafka/Redpanda consumer, idempotent on `render_id` with DLQ
- **Data quality** — schema + freshness + volume + integrity tiers; GE-style suite
- **Observability** — JSON logs with `correlation_id`, Prometheus `/metrics`, OpenTelemetry spans, Grafana alerts, 5 runbooks
- **Lineage** — OpenLineage events viewable in Marquez (best-effort, no-op when unset)
- **Benchmarked** — batch/streaming/scale/backfill + cost model ($ per 1000 renders)
- **Multi-cloud IaC** — Terraform for AWS (S3 + RDS) and GCP (GCS + Cloud SQL)
- **Spot batch** — AWS Batch SPOT compute env, ~70% cheaper than on-demand
- **Live demo** — [math-render-pipeline.streamlit.app](https://math-render-pipeline-3kvjtr8gsh8rtpxsg4fwtc.streamlit.app)

## 🌿 Fun Projects

Smaller pieces where the goal is exploration, not production.

- [**math-aug**](https://github.com/VynJustHumant/math-aug) — deterministic mathematical art from algebraic formulas (vortices, particles, fractals). NumPy + PyTorch, purely for fun.

<div align="center">

<sub>🧠 Built with rigor. 🧮 Shipped as data. 🌿 Explored for fun. 🦴</sub>

</div>
