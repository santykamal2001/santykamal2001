<!-- HERO -->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f0c29,50:302b63,100:24243e&height=220&section=header&text=Santhos%20Kamal%20A%20B&fontSize=48&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Building%20AI%20systems%20that%20think%20in%20graphs%2C%20scale%20to%20millions%2C%20and%20cost%20less%20to%20run&descAlignY=60&descSize=15&descColor=a8b2d8" width="100%" />
</div>

<br/>

<!-- ONE-LINE IDENTITY STATEMENT -->
<div align="center">
  <h3>I ship <strong>production-grade LLM systems</strong> — GraphRAG pipelines, multi-agent architectures, and inference infrastructure that runs at 1,200 req/sec with 99.95% uptime.</h3>
</div>

<br/>

<!-- KEY METRICS — THE HOOK -->
<div align="center">

| ⚡ 1,200 req/sec | 🧠 40% fewer hallucinations | 💰 $50K/mo saved | 📊 NDCG@10: 0.87 | 👥 50K+ MAU |
|:---:|:---:|:---:|:---:|:---:|
| LLM serving at sub-100ms | Multi-agent graph pipelines | AWS GPU & S3 optimisation | Cross-encoder reranking | 99.95% availability |

</div>

<br/>

<!-- BADGES -->
<div align="center">
  <img src="https://komarev.com/ghpvc/?username=santykamal2001&style=flat-square&color=302b63&label=Profile+Views" />
  &nbsp;
  <a href="mailto:santykamal2001@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white"/></a>
  &nbsp;
  <a href="https://linkedin.com/in/santhos-kamal"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white"/></a>
  &nbsp;
  <a href="https://santhos-portfolio.vercel.app"><img src="https://img.shields.io/badge/Portfolio-000000?style=flat-square&logo=vercel&logoColor=white"/></a>
  &nbsp;
  <a href="https://github.com/santykamal2001"><img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white"/></a>
</div>

---

<!-- WHO THIS IS FOR — INDUSTRY FRAMING -->
## 🎯 What I Actually Build

> *If you're in **Tech, Startups, or BFSI** — here's what matters to you, not a generic skills dump.*

<details>
<summary>🏦 &nbsp;<strong>BFSI / Enterprise</strong> — Compliance-aware RAG, fraud signal extraction, KG-powered decision systems</summary>

<br/>

I've built LLM pipelines designed around **reliability and explainability** — two things that matter when a wrong answer costs money or triggers a regulator.

- **Hybrid GraphRAG** over 50K+ entity knowledge graphs with structured output validation — reduces hallucination by 40%, answer is traceable to a source node
- **Distributed ranking pipelines** (BM25 + dense hybrid + cross-encoder reranking) running at 1,200 req/sec — production-hardened, not proof-of-concept
- **Cypher-native NL-to-graph query generation** — natural language queries resolved to structured Neo4j traversals with citation grounding
- Built observability into everything: CloudWatch dashboards, A/B experiment tracking across 200+ runs, pytest coverage gates on every PR

*At Oncorre, I maintained 99.95% uptime for 50K+ MAU. That's not luck — it's architecture.*

</details>

<details>
<summary>🚀 &nbsp;<strong>Startups</strong> — Move fast without breaking prod. Lean infra, high throughput, low cloud bill.</summary>

<br/>

I know what it feels like to own a system end-to-end — from prompt design to SageMaker deployment to the CloudWatch alarm at 2am.

- Saved **$50K/month** by redesigning LLM inference on AWS: S3 tiering, GPU sharing, autoscaling on ECS — without touching latency targets
- Went from 54 features to 12 via automated reduction — **4.2× faster training, 73% less memory** — on a 581K-observation ML pipeline
- Built CI/CD pipelines, merged 200+ PRs with coverage gates, shipped 40% faster after adding proper experiment tracking
- Full-stack AI: Python backend (FastAPI, gRPC) → LangGraph orchestration → vector/graph retrieval → AWS serving → monitoring

*Startups hire me when they want a prototype that doesn't need to be rewritten in 6 months.*

</details>

<details>
<summary>🔬 &nbsp;<strong>Deep Tech / Research-adjacent</strong> — Graph ML, biological networks, novel retrieval architectures</summary>

<br/>

I'm comfortable in the zone between research papers and production systems.

- Modeled **protein-protein interaction networks** as property graphs using MCL/MCODE clustering and centrality analysis — 99.9% efficiency improvement over baseline matrix methods (p < 0.001)
- Designed a **query classifier** that dynamically routes between Neo4j Cypher traversal and Qdrant hybrid vector retrieval — different retrieval paths for structural vs. semantic queries
- Targeting **48% → 85%+ retrieval accuracy** on 8TB+ enterprise data using phased GraphRAG redesign with RRF fusion
- Cross-encoder reranking achieving NDCG@10 of **0.87** — among the best scores for production hybrid retrieval systems

*I read papers on Friday and ship implementations on Monday.*

</details>

---

<!-- THE SYSTEM DIAGRAM — THE BIG DIFFERENTIATOR -->
## 🧠 Flagship System: Hybrid GraphRAG Intelligence Platform

> *The most interesting thing I'm building right now. Here's the architecture — not a slide, the actual system.*

```
                        USER QUERY
                            │
              ┌─────────────▼─────────────┐
              │      QUERY CLASSIFIER      │  ← LangGraph router
              │  (structural vs semantic)  │     with retry + fallback
              └──────┬──────────┬──────────┘
                     │          │
          ┌──────────▼──┐  ┌────▼──────────┐
          │  NEO4J PATH │  │  VECTOR PATH  │
          │  NL→Cypher  │  │  BGE + BM25   │
          │  traversal  │  │  dense+sparse │
          └──────┬──────┘  └────┬──────────┘
                 │              │
          ┌──────▼──────────────▼──────────┐
          │       RRF FUSION LAYER         │  ← Reciprocal Rank Fusion
          │   (structural + semantic)      │
          └──────────────┬─────────────────┘
                         │
          ┌──────────────▼─────────────────┐
          │    CROSS-ENCODER RERANKING     │  ← NDCG@10: 0.87
          │     (BGE-reranker-large)       │
          └──────────────┬─────────────────┘
                         │
          ┌──────────────▼─────────────────┐
          │     GROUNDED LLM RESPONSE      │  ← Citations tied to KG nodes
          │     (Structured + Validated)   │     Hallucination −40%
          └────────────────────────────────┘
```

**Status:** Phase 2 of retrieval redesign in progress — targeting 85%+ accuracy on 8TB+ enterprise data.

---

<!-- PROJECTS — STORY-FIRST FORMAT -->
## 🚀 Projects (the story behind the numbers)

<br/>

### 🔮 Hybrid GraphRAG Enterprise Intelligence System
> *"What if you could search a knowledge graph the way you'd ask a colleague?"*

The problem: enterprise data lives in silos — structured graphs and unstructured documents — and existing RAG systems choose one or the other. This system doesn't.

A query classifier decides at runtime whether a question needs **graph traversal** (relationships, paths, entity lookups) or **vector retrieval** (semantic similarity, document chunks). Then fuses both via Reciprocal Rank Fusion before a cross-encoder reranks the top candidates. Every answer is grounded in a graph node — traceable, not hallucinated.

**Stack:** Python · Neo4j · Qdrant · LangChain · Claude API · LangGraph

```
Target: 48% → 85%+ retrieval accuracy | Scale: 8TB+ enterprise data
```

<br/>

### 🧬 Biological Network Analysis via Graph Algorithms
> *"Can graph theory tell us which proteins are the 'power players' in a disease network?"*

Protein-protein interaction data is messy — thousands of nodes, millions of edges, no obvious structure. I modeled it as a property graph and applied MCL/MCODE clustering to find biologically meaningful communities, then used centrality analysis to surface regulatory hubs that standard tools miss.

**The result:** 99.9% efficiency improvement over naive matrix operations, statistically significant hub identification (p < 0.001). This is the kind of graph thinking I now apply to enterprise knowledge graphs.

**Stack:** Python · NetworkX · Graph Algorithms · Statistical Analysis

<br/>

### 🌲 Forest Fire Prediction System — End-to-End ML Pipeline
> *"Can we predict fire risk before a fire happens, at production scale?"*

Not a notebook experiment. A full ML pipeline: 581K observations, automated feature selection that cut 54 features to 12 (4.2× faster training, 73% less memory), and a deployed model hitting 94.87% accuracy. Every decision was made with production constraints in mind — inference latency, memory footprint, retrain cadence.

**Stack:** Python · Scikit-learn · AWS · Automated Feature Engineering

---

<!-- TECH STACK — GROUPED BY WHAT YOU ACTUALLY USE IT FOR -->
## 🛠️ The Stack

**Core AI/LLM Layer**

![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-302b63?style=flat-square&logo=langchain&logoColor=white)
![Anthropic Claude](https://img.shields.io/badge/Claude%20API-BF91F3?style=flat-square&logo=anthropic&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)

**Graph & Vector Retrieval**

![Neo4j](https://img.shields.io/badge/Neo4j-008CC1?style=flat-square&logo=neo4j&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-BF91F3?style=flat-square&logo=qdrant&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-38BDAE?style=flat-square&logo=databricks&logoColor=white)
![NetworkX](https://img.shields.io/badge/NetworkX-70A5FD?style=flat-square&logo=python&logoColor=white)

**Infrastructure & Serving**

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![SageMaker](https://img.shields.io/badge/SageMaker-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-4285F4?style=flat-square&logo=google&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

---

<!-- WORK EXPERIENCE — OUTCOME-LED -->
## 💼 Experience

<details>
<summary><strong>AI/ML Engineer — LLM Systems & GenAI</strong> · Oncorre Inc · Jan 2025 – Present · Bridgewater, NJ</summary>

<br/>

The challenge: serve an LLM-powered product to 50K+ monthly active users, reliably, at sub-100ms latency, with a hallucination problem and a cloud bill that needed to come down.

**What I built and what changed:**

🧠 **Multi-agent knowledge graph pipeline** (LangChain + LangGraph) over 50K+ entity Neo4j graph — agent routing, retry logic, tool use, structured output validation. Hallucinations dropped 40%.

⚡ **Distributed RAG serving infrastructure** — vector embeddings, semantic search, cross-encoder reranking (NDCG@10: 0.87). Now handling 1,200+ req/sec at 99.95% availability.

💰 **AWS cost engineering** — SageMaker, ECS, Lambda, S3 tiering, GPU autoscaling. $50K/month saved. Incidents down 60%.

📊 **Experiment culture** — 200+ A/B experiments (precision, recall, F1, NDCG), CloudWatch dashboards, 200+ PRs merged. Feature delivery 40% faster.

> ![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white) ![LangGraph](https://img.shields.io/badge/LangGraph-302b63?style=flat-square&logo=langchain&logoColor=white) ![Neo4j](https://img.shields.io/badge/Neo4j-008CC1?style=flat-square&logo=neo4j&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)

</details>

<details>
<summary><strong>Software Engineer — Data & Application Engineering</strong> · Rumango Software & Consulting · Feb 2023 – Jul 2023 · Bangalore, IN</summary>

<br/>

Shipped data-driven features for an international banking platform serving the Malawi market — 1,000+ daily transactions, 10+ production modules.

- Transaction completion rate up **25%** via SQL + REST API integration improvements
- Python and TypeScript async refactors cut latency **30%**, **99.8% uptime** maintained

> ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

</details>

---

<!-- GITHUB ACTIVITY -->
## 📊 Activity

<div align="center">
  <img src="https://streak-stats.demolab.com?user=santykamal2001&theme=tokyonight-duo&hide_border=true&background=0D1117&ring=302b63&fire=BF91F3&currStreakLabel=70A5FD&sideLabels=38BDAE&dates=8B949E&currStreakNum=C9D1D9&sideNums=C9D1D9&stroke=0D1117&border_radius=10" alt="Streak"/>
</div>

<br/>

<div align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=santykamal2001&theme=tokyo-night&bg_color=0d1117&color=70a5fd&line=bf91f3&point=38bdae&area=true&hide_border=true" width="100%"/>
</div>

---

<!-- WHAT I'M BUILDING NOW -->
## 🔭 What I'm Obsessing Over Right Now

```python
current_focus = {
    "GraphRAG v2": {
        "goal": "48% → 85%+ retrieval accuracy on 8TB+ enterprise data",
        "approach": "phased retrieval redesign: NL-to-Cypher + RRF fusion + cross-encoder",
        "hard_problem": "entity disambiguation at scale without ground truth labels"
    },
    "MLOps at scale": {
        "learning": "GPU cluster scheduling, SageMaker inference endpoints, model drift",
        "question": "how do you monitor embedding drift in production without labels?"
    },
    "Distributed systems": {
        "language": "Go",
        "building": "gRPC microservice patterns for high-throughput API design",
        "why": "Python async is great until it isn't"
    }
}
```

---

<!-- EDUCATION -->
## 🎓 Education

| | Degree | Institution | Period |
|:-:|:-------|:------------|:-------|
| 🎓 | M.Eng. in Computer Science | Oregon State University | Sep 2023 – Mar 2025 |
| 🎓 | B.Eng. in Computer Science | St. Joseph's College of Engineering | Aug 2019 – May 2023 |

---

<!-- CTA — CLEAR AND DIRECT -->
## 🤝 Want to talk systems, not slides?

If you're building something ambitious in AI and need someone who can take it from prototype to production — let's talk.

<div align="center">
  <a href="mailto:santykamal2001@gmail.com">
    <img src="https://img.shields.io/badge/Send%20me%20an%20email-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>
  &nbsp;
  <a href="https://linkedin.com/in/santhos-kamal">
    <img src="https://img.shields.io/badge/Connect%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
  &nbsp;
  <a href="https://santhos-portfolio.vercel.app">
    <img src="https://img.shields.io/badge/See%20full%20portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white"/>
  </a>
</div>

<br/>

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:24243e,50:302b63,100:0f0c29&height=140&section=footer&animation=fadeIn" width="100%"/>
</div>
