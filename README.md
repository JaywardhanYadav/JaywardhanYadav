<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="./light.svg">
    <img alt="Jaywardhan Yadav - AI Engineer Hero Banner" src="./dark.svg" width="100%" />
  </picture>
</div>

---

## ⚡ About Me

I am an **AI & Machine Learning Engineer** passionate about building robust, scalable, and intelligent production systems. My work centers on architecting autonomous **Multi-Agent workflows (LangGraph & CrewAI)**, developing high-precision **Retrieval-Augmented Generation (RAG)** systems, and training deep learning models with PyTorch. Backed by solid foundations in backend engineering and MLOps, I specialize in translating experimental AI research into high-throughput, containerized microservices deployed with FastAPI, Docker, and MLflow. I am dedicated to bridging the gap between cutting-edge LLMs and reliable, sub-second latency production applications.

---

## 🚀 Flagship AI Engineering Projects

### ⚖️ 1. [LegalDrishti AI](https://github.com/JaywardhanYadav/LegalDrishti-AI) — Two-Stage RAG Legal Intelligence & Document Research Platform
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

### 🗺️ 2. [PlanMyTrip AI](https://github.com/JaywardhanYadav/PlanMyTrip-AI) — Autonomous Multi-Agent Travel Planner & Budget Engine
> *A collaborative, state-machine driven multi-agent travel architecture leveraging **Model Context Protocol (MCP)** to orchestrate real-time modular APIs, strict budget constraints, and hallucination-free itinerary drafts.*

```
                     ┌─────────────────────────────┐
                     │   Orchestrator Supervisor   │
                     │  (LangGraph State Machine)  │
                     └──────────────┬──────────────┘
                                    │
         ┌──────────────────────────┼──────────────────────────┐
         ▼                          ▼                          ▼
┌──────────────────┐      ┌──────────────────┐      ┌──────────────────┐
│ Itinerary & Cult │      │ Budget & Expense │      │  Logistics & Geo │
│ Specialist Agent │      │ Calculator Agent │      │ Specialist Agent │
└────────┬─────────┘      └────────┬─────────┘      └────────┬─────────┘
         │                         │                         │
         └─────────────────────────┼─────────────────────────┘
                                   ▼
              ┌──────────────────────────────────────────┐
              │     Model Context Protocol (MCP) Hub     │
              │  (Tavily • OpenWeather • Flights/Hotels) │
              └──────────────────────────────────────────┘
```

- **Hierarchical LangGraph Orchestration:** Coordinates multi-turn state transitions between specialized worker agents with conditional dispatch, loop validation, and persistent thread memory.
- **Model Context Protocol (MCP) Server Hub:** Interfaces worker agents with modular, standardized MCP tool servers to query live flight, accommodation, geocoding, and local weather APIs without context clutter.
- **Deterministic Budget & Cost Optimization:** Calculates exact total travel expenses across accommodation, transit, and daily allowances, enforcing hard mathematical ceiling constraints to eliminate financial hallucinations.
- **End-to-End Itinerary Synthesis:** Produces a comprehensive, actionable travel dossier complete with hour-by-hour schedules, verified transit times, and localized recommendations.
- **Tech Stack:** `Python 3.12` • `LangGraph` • `Model Context Protocol (MCP)` • `FastAPI` • `Pydantic v2` • `LangChain` • `Tavily API` • `Docker`

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
| **Agentic & Generative AI** | `Agentic AI` • `LangGraph` • `LangChain` • `CrewAI` • `RAG (Dense/Sparse)` • `Function Calling` • `Prompt Engineering` |
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
