# Kartik Arora

<div align="center">

[![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=2E9EF7&center=true&vCenter=true&width=600&lines=Building+Production+AI+Systems;RAG+%7C+Multi-Agent+%7C+LLM+Integration;Turning+Ideas+into+Reliable+Software)](https://git.io/typing-svg)

</div>

---

## About

I build AI systems that go beyond demos — full pipelines with feedback loops, human oversight, and real production constraints. Currently focused on incident intelligence, AI-assisted hiring, and workflow automation.

- Working on systems that use **RAG, semantic search, and LLM reasoning** at the core
- Designing **multi-agent architectures** with proper observability and guardrails
- Interested in the gap between "AI prototype" and "production-grade AI"

---

## Featured Projects

### [AIRRA](https://github.com/kkrriders/AIRRA) — Autonomous Incident Response & Reliability Agent

AI-powered incident management platform. Detects anomalies from Prometheus metrics, retrieves semantically similar past incidents via pgvector RAG, generates root-cause hypotheses using LLM reasoning, and routes for human approval before any action executes.

```
Prometheus → Z-score anomaly → pgvector semantic search → RAG reasoning
  → hypothesis ranking → SRE notification → human approval → action → feedback loop
```

**Key design decisions:**
- Multi-signal composite similarity `(0.5 × vector + 0.3 × service_match + 0.2 × metric_overlap)` — cosine distance alone is a poor proxy across services
- LLM skipped entirely when composite ≥ 0.75 — reuses past resolution, saves cost
- Trust-weighted RAG retrieval (human-validated postmortems rank 5× higher than AI-generated scenarios) — makes knowledge poisoning impractical
- Prompt injection guard + credential redaction before embeddings reach pgvector (OWASP LLM01, LLM06)
- Incident trust score + append-only audit log for every agent decision

**Tech:** `FastAPI` `Next.js 14` `PostgreSQL + pgvector` `Celery` `Redis` `Groq (LLaMA-3.3-70b)`

---

### [MockPrep](https://github.com/kkrriders/MockPrep) — AI Mock Interview Platform

End-to-end interview preparation platform. Candidates upload a CV, select a role and interview mode, and receive AI-generated questions scored in real-time with structured feedback.

**What's built:**
- CV parsing → skill extraction → gap analysis (identifies what's missing for the target role)
- Panel interview mode with distinct AI personas (Alex / Priya / James) — single Groq call per turn
- Adaptive decision agent: chooses follow-up / probe deeper / challenge / next question based on answer quality
- BullMQ scoring queue with `concurrency=1` — respects Groq free-tier rate limits without dropping answers
- SSE broadcaster for real-time score updates; Whisper STT fallback for voice answers
- Company-specific research agent (Tavily live search) to generate role-relevant questions

**Tech:** `Node.js / Express` `Next.js 15` `MongoDB` `Redis` `Groq` `BullMQ`

---

### [ChasmX](https://github.com/kkrriders/ChasmX) — AI Workflow Automation Platform

Visual drag-and-drop workflow builder with LLM integration and Redis-backed response caching.

- Multi-model support via OpenRouter (Gemini, LLaMA, Qwen)
- Redis caching layer: 20–50× faster repeat responses
- Multi-agent coordination for complex task pipelines

**Tech:** `FastAPI` `Next.js` `MongoDB` `Redis` `OpenRouter` `React Flow`

---

## Tech Stack

**AI / ML**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-121212?style=flat&logo=chainlink&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-F55036?style=flat)
![OpenRouter](https://img.shields.io/badge/OpenRouter-7C3AED?style=flat)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat&logo=huggingface&logoColor=black)
![pgvector](https://img.shields.io/badge/pgvector-336791?style=flat&logo=postgresql&logoColor=white)

**Backend & Frontend**

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![TailwindCSS](https://img.shields.io/badge/Tailwind-38B2AC?style=flat&logo=tailwind-css&logoColor=white)

**Data & Infrastructure**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=flat)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat&logo=prometheus&logoColor=white)

---

## GitHub Stats

<div align="center">

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=kkrriders&show_icons=true&theme=dark&hide_border=true&bg_color=0d1117&title_color=2E9EF7&icon_color=2E9EF7)
&nbsp;
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=kkrriders&layout=compact&theme=dark&hide_border=true&bg_color=0d1117&title_color=2E9EF7)

</div>

---

## Connect

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kartikArora3135)
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=flat&logo=twitter&logoColor=white)](https://x.com/KartikAror23722)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=flat&logo=gmail&logoColor=white)](mailto:kartikarora3135@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/kkrriders)

</div>
