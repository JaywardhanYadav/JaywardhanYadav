<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="./light.svg">
    <img alt="Jaywardhan Yadav - AI Engineer Hero Banner" src="./dark.svg" width="100%" />
  </picture>
</div>

---

## 👨‍💻 About Me

I am an **AI & Machine Learning Engineer** passionate about architecting autonomous **Multi-Agent Orchestration Platforms (LangGraph, MCP)**, high-precision **Retrieval-Augmented Generation (RAG)** systems, and scalable production MLOps pipelines. Backed by solid foundations in distributed backend engineering and low-latency microservices (FastAPI, PostgreSQL, Redis, Docker), I specialize in turning complex LLM workflows into deterministic, budget-reconciled, and benchmark-verified enterprise applications with measurable business impact.

---

## 🚀 Flagship AI Engineering Projects

### ✈️ 1. [PlanMyTrip AI](https://github.com/JaywardhanYadav/PlanMyTrip-AI) — Enterprise Multi-Agent Travel Orchestration Platform
> *An enterprise-grade multi-agent orchestration engine built with **LangGraph**, **FastAPI**, **PostgreSQL 16**, **Redis 7**, and the **Model Context Protocol (MCP)**—delivering 2-stage parallel domain fan-out, live travel API tool calls, deterministic financial reconciliation, and real-time SSE progress telemetry.*

```
                     ┌──────────────────────────────────────────────┐
                     │    User Intake & Supervisor (HITL / SSE)     │
                     │          (LangGraph State Machine)           │
                     └──────────────────────┬───────────────────────┘
                                            │
               ┌────────────────────────────┴───────────────────────────┐
               ▼ (Stage 1: Parallel Fan-Out via asyncio.gather)         ▼ (Stage 2: Spatial Anchor)
    ┌─────────────────────┐   ┌─────────────────────┐   ┌─────────────────────┐
    │     FlightAgent     │   │     PlacesAgent     │   │     HotelAgent      │
    │  (Live Schedules)   │   │  (Daytime Clusters) │   │ (Base Stay & Dining)│
    └──────────┬──────────┘   └──────────┬──────────┘   └──────────┬──────────┘
               │                         │                         │
               └─────────────────────────┼─────────────────────────┘
                                         ▼
                     ┌───────────────────────────────────────┐
                     │   Model Context Protocol (MCP) Hub    │
                     │  (FlightAPI • SerpApi • Open-Meteo)   │
                     └───────────────────┬───────────────────┘
                                         ▼
                     ┌───────────────────────────────────────┐
                     │ N-Day Output Guardrail & Verification │
                     │   (Decimal.Decimal Budget Engine)     │
                     └───────────────────────────────────────┘
```

- **Two-Stage Multi-Agent Orchestration (LangGraph):** Executes an asynchronous 2-stage graph avoiding naive single-prompt bottlenecks. Stage 1 triggers parallel domain fan-out (`FlightAgent`, `PlacesAgent`, `DayPlannerAgent` via `asyncio.gather`), extracting daytime activity hubs to feed Stage 2 (`HotelAgent`) for spatially anchored base stays and curated dining.
- **Single-Base Stay Continuity & N-Day Verification Guardrail:** Implements an automated luggage-free base hotel strategy for intermediate nights (Days 2 to $N-1$) with Day $N$ concierge baggage hold. A post-generation verification loop mathematically enforces inclusive calendar math ($D_{end} = D_{start} + N - 1$), complete $N$-day continuity, and grounded hotel rates.
- **Deterministic Budget Reconciliation (Zero Float Drift):** Built with Python `decimal.Decimal` and ISO-4217 tracking, eliminating floating-point rounding errors and strictly reconciling multi-tier budgets (Budget, Moderate, Luxury) against hard ceilings ($Total \le Budget_{max}$).
- **Decoupled MCP Microservice Topology:** Interfaces worker agents with 3 standalone **Model Context Protocol (MCP)** servers (`FlightAPI.io`, `SerpApi Google Hotels`, `Open-Meteo`, and `Tavily`) backed by Redis 7 caching and credit-safe rate limiting.
- **Enterprise Benchmark Metrics & Unit Economics:** Evaluated via an automated 4-dimensional benchmark suite ([evaluations/](https://github.com/JaywardhanYadav/PlanMyTrip-AI/blob/main/evaluations)) achieving a **96.2% Composite Production Score**:
  - **96.0% Adversarial Safety & Jailbreak Defense** (24/25 injection attacks blocked).
  - **96.8% Budget Compliance** & **95.5% Structural Quality** across complex multi-day circuits.
  - **11.4s p50 Latency (18.2s p95)** across parallel distributed MCP tool calls.
  - **~$0.018 (~₹1.50 INR) Cost / Trip:** Token-optimized with strict context pruning on `gpt-4o-mini` (55,000+ comprehensive multi-day itineraries per $1,000 LLM spend).
- **Human-in-the-Loop (HITL) Checkpoints & Security:** Persists interactive state checkpoints via PostgreSQL 16 `AsyncPostgresSaver` with authenticated JWT thread ownership and real-time Server-Sent Events (SSE) telemetry.
- **Tech Stack:** `Python 3.12` • `LangGraph` • `FastAPI` • `Model Context Protocol (MCP)` • `PostgreSQL 16` • `Redis 7` • `Docker Compose` • `Server-Sent Events (SSE)` • `SerpApi` • `FlightAPI.io` • `Tavily`

---

### ⚖️ 2. [LegalDrishti AI](https://github.com/JaywardhanYadav/LegalDrishti-AI) — Two-Stage RAG Legal Intelligence & Document Research Platform
> *An enterprise-grade legal intelligence and consultation platform engineered for the Indian legal system (BNS, BNSS, BSA 2023) using a high-precision Two-Stage RAG pipeline backed by OpenAI and Weaviate.*

```
┌──────────────────┐     ┌─────────────────────┐     ┌────────────────────────┐
│  28 Indian Acts  │ ──> │ Recursive Chunking  │ ──> │ Weaviate HNSW Index    │
│  & Client Vault  │     │ + OpenAI Embeddings │     │ (Hybrid Dense + BM25)  │
└──────────────────┘     └─────────────────────┘     └───────────┬────────────┘
                                                                 │
┌──────────────────┐     ┌─────────────────────┐     ┌───────────▼────────────┐
│ Verified Legal   │ <── │ Dual-Stream Prompt  │ <── │ Cross-Encoder Reranker │
│ Strategy & Cites │     │ + GPT-4o Synthesis  │     │ (Top-5 Precision Chunks│
└──────────────────┘     └─────────────────────┘     └────────────────────────┘
```

- **Two-Stage Hybrid Retrieval:** Integrates an upstream **Statute Router (Regex + Weighted N-Grams)** with **Weaviate Hybrid Search** ($\alpha=0.5$ dense vectors + BM25) to isolate relevant statutory codes before vector retrieval.
- **Cross-Encoder Reranking (`FlashRank`):** Filters raw candidate pools (top-20) down to top-5 precision chunks, boosting **MRR@5 from 0.384 to 0.762 (+98.4%)** and achieving **86.8% Hit Rate @ 5** at **~68ms latency**.
- **Dual-Stream Context Synthesis:** Concurrently contextualizes codified statutes alongside private client evidence in **GPT-4o** with strict citation traceability (Act, Section, Page number).
- **Tech Stack:** `Python 3.12` • `FastAPI` • `OpenAI GPT-4o / Embeddings` • `Weaviate (HNSW)` • `PostgreSQL 17` • `Docker` • `Streamlit`

---

### 🏥 3. [Insurance Premium Prediction MLOps](https://github.com/JaywardhanYadav/Insurance-premium-prediction-mlops) — Production MLOps with Automated Drift Monitoring
> *An end-to-end production MLOps pipeline featuring ensemble regression (XGBoost + LightGBM), Optuna hyperparameter tuning, MLflow experiment tracking, MSSQL inference logging, and Evidently AI data drift detection.*

```
┌──────────────────┐     ┌─────────────────────┐     ┌────────────────────────┐
│ Streamlit UI /   │ ──> │ FastAPI Backend API │ ──> │ Inference Logging      │
│ Client Request   │     │ (Pydantic Schemas)  │     │ (MSSQL Server DB)      │
└──────────────────┘     └──────────┬──────────┘     └───────────┬────────────┘
                                    │                            │
                         ┌──────────▼──────────┐                 │
                         │ MLflow Model Store  │                 ▼
                         │ (XGBoost + LightGBM)│     ┌────────────────────────┐
                         └─────────────────────┘     │ Evidently AI Monitor   │
                                                     │ (Data & Concept Drift) │
                                                     └────────────────────────┘
```

- **Ensemble Modeling & Optimization:** Blends **XGBoost** and **LightGBM** regressors optimized via **Optuna** to predict risk-adjusted premiums with automated validation scoring.
- **Experiment Tracking & Model Registry:** Centrally versions hyperparameters, clinical feature pipelines, and serialized model artifacts powered by **MLflow**.
- **Automated Data Drift Detection:** Employs **Evidently AI** to continuously evaluate live inference payloads against parquet reference baselines, logging statistical drift alerts into **MSSQL**.
- **Multi-Container Orchestration:** Fully containerized with **Docker Compose**, seamlessly orchestrating FastAPI inference, Streamlit dashboard, MSSQL database, and scheduled drift monitoring jobs.
- **Tech Stack:** `Python 3.12` • `FastAPI` • `MLflow` • `Docker Compose` • `Evidently AI` • `MSSQL` • `XGBoost` • `LightGBM` • `DVC` • `Streamlit`

---

## 🛠️ Technical Arsenal

<div align="center">

| Domain | Technologies & Frameworks |
| :--- | :--- |
| **Agentic & Generative AI** | `Agentic AI` • `LangGraph` • `Model Context Protocol (MCP)` • `LangChain` • `CrewAI` • `RAG (Dense/Sparse)` • `Function Calling` • `Prompt Engineering` |
| **LLMs & Embedding Models** | `OpenAI GPT-4o` • `Claude 3.7` • `DeepSeek-R1` • `Hugging Face Transformers` • `Sentence-Transformers` • `Ollama` |
| **Vector Stores & Databases** | `Qdrant` • `Pinecone` • `ChromaDB` • `PostgreSQL (pgvector)` • `Redis` • `SQLite` |
| **Machine Learning & Core** | `Python` • `PyTorch` • `Scikit-Learn` • `NumPy` • `Pandas` • `NLP` • `Feature Engineering` |
| **Backend & Architecture** | `FastAPI` • `REST APIs` • `Pydantic` • `System Design` • `AsyncIO` • `Microservices` |
| **MLOps & Infrastructure** | `Docker` • `AWS (EC2, S3)` • `DVC` • `DagsHub` • `MLflow` • `CI/CD Pipelines` • `Git` • `Linux` |
</div>

<br/>

<div align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/LangGraph-000000?style=for-the-badge&logo=diagram-next&logoColor=white" alt="LangGraph" />
  <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=chainlink&logoColor=white" alt="LangChain" />
  <img src="https://img.shields.io/badge/Agentic_AI-F59E0B?style=for-the-badge&logo=openai&logoColor=white" alt="Agentic AI" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Pydantic-E92063?style=for-the-badge&logo=pydantic&logoColor=white" alt="Pydantic" />
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/Redis-DC2626?style=for-the-badge&logo=redis&logoColor=white" alt="Redis" />
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/DVC-945DD6?style=for-the-badge&logo=dvc&logoColor=white" alt="DVC" />
  <img src="https://img.shields.io/badge/DagsHub-1565C0?style=for-the-badge&logo=dagshub&logoColor=white" alt="DagsHub" />
  <img src="https://img.shields.io/badge/MLflow-0194E2?style=for-the-badge&logo=mlflow&logoColor=white" alt="MLflow" />
  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS" />
  <img src="https://img.shields.io/badge/CI%2FCD-06B6D4?style=for-the-badge&logo=githubactions&logoColor=white" alt="CI/CD" />
</div>

---

## 🌐 Connect & Collaborate

I am actively open to **AI/ML Engineering roles**, **GenAI / Multi-Agent consulting**, and **innovative open-source collaborations**.

<div align="center">
  <a href="https://jaywardhanportfolio.netlify.app/">
    <img src="https://img.shields.io/badge/Website-Portfolio-22D3EE?style=for-the-badge&logo=safari&logoColor=black" alt="Portfolio" />
  </a>
  &nbsp;
  <a href="https://www.linkedin.com/in/jaywardhanyadav/">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  &nbsp;
  <a href="mailto:jaywardhan.tech@gmail.com">
    <img src="https://img.shields.io/badge/Email-jaywardhan.tech@gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
  </a>
  &nbsp;
  <a href="https://github.com/JaywardhanYadav">
    <img src="https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
  </a>
</div>

<br/>

<div align="center">
  <sub>⚡ Designed with pure SVG animations &amp; crafted for modern AI Engineering standards. Built by <a href="https://github.com/JaywardhanYadav">Jaywardhan Yadav</a>.</sub>
</div>
