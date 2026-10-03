<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="./light.svg">
    <img alt="Jaywardhan Yadav - AI Engineer Hero Banner" src="./dark.svg" width="100%" />
  </picture>
</div>

<p align="center">
  <a href="https://github.com/JaywardhanYadav"><img src="https://img.shields.io/badge/GitHub-JaywardhanYadav-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
  <a href="https://www.linkedin.com/in/jaywardhanyadav/"><img src="https://img.shields.io/badge/LinkedIn-Jaywardhan_Yadav-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="https://jaywardhanportfolio.netlify.app/"><img src="https://img.shields.io/badge/Portfolio-Live_Website-06B6D4?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Portfolio" /></a>
  <a href="mailto:jaywardhan.tech@gmail.com"><img src="https://img.shields.io/badge/Email-jaywardhan.tech@gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <img src="https://img.shields.io/badge/Focus-Agentic_AI_%26_RAG-7C3AED?style=for-the-badge&logo=openai&logoColor=white" alt="Current Focus" />
</p>

---

## ⚡ About Me

I am an **AI Engineer & Multi-Agent Systems Architect** specializing in bridging the gap between cutting-edge LLM research and production-grade software. My focus lies in designing **autonomous agentic workflows (LangGraph / CrewAI)**, **enterprise-grade Retrieval-Augmented Generation (RAG)** systems, and **scalable MLOps inference pipelines**.

- 🔭 **Current Focus:** Building autonomous multi-agent swarms with stateful reasoning, dynamic tool selection, and hybrid vector search architectures.
- 💡 **Philosophy:** *"Moving AI from exploratory Jupyter notebooks into robust, observable, sub-second latency production systems."*
- 🎯 **Recent Highlights:** Designed **LegalDrishti AI** (statutory legal RAG with hybrid dense/sparse indexing) and **PlanMyTrip AI** (multi-agent hierarchical travel planning engine).
- 💬 **Ask Me About:** Agentic orchestration, RAG hallucination reduction, LangGraph state machines, vector databases, and containerized ML APIs.

---

## 🚀 Flagship AI Engineering Projects

### ⚖️ 1. [LegalDrishti AI](https://github.com/JaywardhanYadav) — Enterprise Legal RAG Intelligence System
> *An advanced Retrieval-Augmented Generation platform built for querying, summarizing, and reasoning over complex Indian statutory codes, case files, and legal documents with precise citation traceability.*

```
┌─────────────────┐     ┌──────────────────┐     ┌────────────────────────┐
│  Legal Corpus   │ ──> │ Chunking & Meta  │ ──> │ Hybrid Vector Index    │
│  (Acts / Acts)  │     │ Tagging Engine   │     │ (Dense + Sparse BM25)  │
└─────────────────┘     └──────────────────┘     └───────────┬────────────┘
                                                             │
┌─────────────────┐     ┌──────────────────┐     ┌───────────▼────────────┐
│ Verified Answer │ <── │ LLM Synthesis &  │ <── │ Cross-Encoder Reranker │
│  with Citations │     │ Guardrails Check │     │ (Top-k Relevant Chunks)│
└─────────────────┘     └──────────────────┘     └────────────────────────┘
```

- **Hybrid Dense-Sparse Search:** Combines dense neural embeddings for semantic intent with sparse BM25 indexing for exact statutory clause and section lookups.
- **Cross-Encoder Reranking:** Filters initial vector retrieval pools through a high-precision cross-encoder to elevate pinpoint relevance before context injection.
- **Hallucination Guardrails:** Implements citation enforcement so every generated legal opinion references verifiable paragraphs and case law precedent.
- **Tech Stack:** `Python` • `FastAPI` • `LangChain` • `Qdrant / Chroma` • `PostgreSQL` • `Docker` • `Streamlit`

---

### 🗺️ 2. [PlanMyTrip AI](https://github.com/JaywardhanYadav) — Autonomous Multi-Agent Travel Planner
> *A collaborative, state-machine driven multi-agent travel architecture that coordinates real-time research, budget optimization, scheduling, and logistics.*

```
                     ┌─────────────────────────────┐
                     │   Orchestrator Supervisor   │
                     │    (Stateful Coordinator)   │
                     └──────────────┬──────────────┘
                                    │
         ┌──────────────────────────┼──────────────────────────┐
         ▼                          ▼                          ▼
┌──────────────────┐      ┌──────────────────┐      ┌──────────────────┐
│  Weather & Geo   │      │ Budget & Routing │      │ Itinerary & Cult │
│   Worker Agent   │      │   Worker Agent   │      │   Worker Agent   │
└──────────────────┘      └──────────────────┘      └──────────────────┘
```

- **Hierarchical Agent Graph:** Leverages **LangGraph** to model multi-turn state transitions, loop validation, and conditional agent dispatch.
- **Autonomous Tool Execution:** Agents utilize search APIs, geocoding, and currency converters to fetch ground-truth travel parameters.
- **Dynamic Constraint Resolution:** Resolves budget-time tradeoffs by autonomously adjusting activities and transit modes.
- **Tech Stack:** `Python` • `LangGraph` • `LangChain` • `FastAPI` • `Pydantic` • `Tavily Search API` • `Next.js`

---

### 🤖 3. [Customer Support AI](https://github.com/JaywardhanYadav) — Agentic RAG with Dynamic Tool Calling
> *Context-aware autonomous agent equipped with persistent conversational memory buffers, enterprise knowledge grounding, and live external API execution.*

- **Conversational Memory:** Uses windowed buffer memory and summarized vector history for long-term customer context retention.
- **Function Dispatching:** Dynamically executes account checks, ticket status lookups, and escalations via structured JSON schema tool calling.
- **Tech Stack:** `Python` • `LangChain` • `OpenAI API` • `Vector Database` • `FastAPI` • `Docker`

---

### ⚙️ 4. [End-to-End MLOps Pipeline](https://github.com/JaywardhanYadav) — Automated Training, Tracking & Deployment
> *Production-grade continuous training and deployment pipeline with data drift detection, automated model registry, and containerized serving.*

- **Experiment Tracking:** Centralized metric, hyperparameter, and artifact versioning powered by **MLflow**.
- **Automated CI/CD:** GitHub Actions workflows for linting, unit testing, model packaging, and Docker image publishing.
- **Sub-50ms Inference Service:** Deployed with **FastAPI** + **Gunicorn** / **Uvicorn** worker pools with comprehensive health check telemetry.
- **Tech Stack:** `MLflow` • `Docker` • `FastAPI` • `GitHub Actions` • `Scikit-Learn` • `AWS EC2/S3`

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

## 📈 Engineering Activity & Metrics

<div align="center">
  <table border="0">
    <tr>
      <td>
        <img height="175em" src="https://github-readme-stats.vercel.app/api?username=JaywardhanYadav&show_icons=true&theme=tokyonight&hide_border=true&bg_color=030712&title_color=22D3EE&icon_color=7C3AED&text_color=94A3B8" alt="Jaywardhan's GitHub Stats" />
      </td>
      <td>
        <img height="175em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=JaywardhanYadav&layout=compact&theme=tokyonight&hide_border=true&bg_color=030712&title_color=22D3EE&text_color=94A3B8" alt="Top Languages" />
      </td>
    </tr>
  </table>

  <br/>

  <img src="https://github-readme-streak-stats.herokuapp.com/?user=JaywardhanYadav&theme=tokyonight&hide_border=true&background=030712&ring=22D3EE&fire=7C3AED&currStreakLabel=22D3EE" alt="GitHub Streak" width="85%" />
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
