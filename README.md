<div align="center">

# Abrar Mahmud Hasan
### Computer Science Undergraduate • Software Engineer • AI Systems Builder

Currently focused on Multi-Agent Systems, AI Infrastructure and Production ML

[![Resume](https://img.shields.io/badge/View-Resume-0A66C2?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)](https://drive.google.com/file/d/1Wvb6U7F29JNNOmgnnMHMfaOYNuVp3lYQ/view?usp=drive_link)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/abrar-mahmud-hasan-75a630222/)
[![GitHub Followers](https://img.shields.io/github/followers/AlchemistReturns?style=for-the-badge&color=0A66C2&labelColor=black)](https://github.com/AlchemistReturns)

</div>

---

<div align="center">

<img src="https://streak-stats.demolab.com/?user=AlchemistReturns&theme=github-dark-blue&hide_border=true&background=0d1117&ring=0A66C2&fire=0A66C2&currStreakLabel=0A66C2" />

</div>

---

# Featured Projects



<details>
<summary><strong>HealthX</strong> — AI-powered telehealth platform</summary>

> AI-powered telehealth platform built for underserved rural communities with unreliable connectivity.

**Repository:** https://github.com/AlchemistReturns/HealthX

### Highlights

- Built HealthX, a full-stack telehealth platform (React/Vite, Node.js/Express, Firebase Auth) for underserved rural regions with unreliable connectivity, integrating Google Gemini for context-aware symptom analysis using patient history.
- Designed a hybrid online/offline architecture with client-side image compression and a hardcoded fallback dataset, ensuring core diagnosis and hospital-lookup features remain functional on unstable 2G/3G networks.
- Implemented a GPS-based hospital finder combining live OpenStreetMap/Overpass queries with an offline emergency database, plus one-tap Google Maps/Waze navigation handoff.

### Architecture

```text
                           +----------------------+
                           |      React App       |
                           +----------+-----------+
                                      |
                +---------------------+----------------------+
                |                                            |
                | Internet Available                         | Offline
                |                                            |
        +-------v--------+                          +---------v---------+
        | Express API    |                          | Local Emergency   |
        +-------+--------+                          | Dataset           |
                |                                   +---------+---------+
        +-------+---------+                                   |
        | Firebase Auth   |                                   |
        +-----------------+                                   |
                |                                              |
        +-------v---------+                           +--------v--------+
        | Gemini API      |                           | Offline Search  |
        +-----------------+                           +-----------------+

                |
        +-------v------------------+
        | OSM / Overpass API       |
        +--------------------------+
                |
        Google Maps / Waze
```
</details>



<details>
<summary><strong>Valerix</strong> — Fault-tolerant microservices platform</summary>

> Fault-tolerant distributed e-commerce backend with graceful degradation.

**Repository:** https://github.com/rawadhossain/Valerix

### Highlights

- Designed a fault-tolerant Node.js/Express microservices architecture (Order, Inventory, API Gateway) implementing timeout-triggered fallback from synchronous HTTP calls to asynchronous RabbitMQ messaging, preventing request hangs during downstream service degradation.
- Engineered idempotent message processing via an `IdempotencyLog` table to guarantee exactly-once inventory deduction under message retries/duplication, alongside indefinite connection-retry logic for self-healing broker reconnection on startup or outage.
- Instrumented services with Prometheus (RED metrics) and Grafana dashboards, and built real-time latency-alerting in the frontend, enabling observability into distributed failure modes (simulated via a configurable latency-injection mechanism).

### Architecture

```text
                    +-------------------+
                    |     Frontend      |
                    +---------+---------+
                              |
                     API Gateway
                              |
                 +------------+------------+
                 |                         |
         HTTP Success                Timeout
                 |                         |
        +--------v--------+        +-------v--------+
        | Order Service   |------->| RabbitMQ       |
        +--------+--------+        +-------+--------+
                 |                         |
                 |                  Retry / Queue
                 |                         |
        +--------v--------+        +-------v--------+
        | Inventory       |<-------| Worker         |
        | Service         |        +-------+--------+
        +--------+--------+                |
                 |                         |
        +--------v---------+               |
        | Idempotency Log  |               |
        +------------------+               |
                                           |
                +--------------------------+
                |
      Prometheus ---> Grafana ---> Alerts
```
</details>



<details>
<summary><strong>Grit</strong> — Local-first Git intelligence CLI</summary>

> Local-first Git intelligence CLI for engineering decision tracking.

**Repository:** https://github.com/AlchemistReturns/grit

### Highlights

- Built grít, a Go CLI that hooks into git pre-commit, post-rewrite, and post-commit stages to run adaptive interviews, capturing the reasoning behind commits, dependency changes, and reverts.
- Implemented a real-time file watcher with a keyword-based complexity scorer, vague-identifier detection, and paste/AI-assist heuristics, all configurable via `.grit.yaml` thresholds.
- Designed a local-first SQLite (WAL mode) storage layer with per-repo isolation, plus `stats`, `decision` (ADR-style), and Markdown/JSON `push` export commands — no cloud dependency.

### Architecture

```text
               Developer
                    |
               Git Commit
                    |
      +-------------+--------------+
      |                            |
 pre-commit                 post-commit
      |                            |
      +-------------+--------------+
                    |
               Grit Engine
                    |
     +--------------+----------------------+
     |              |                      |
 File Watcher   Interview Engine   Complexity Analysis
     |              |                      |
     +--------------+----------------------+
                    |
             SQLite (WAL Mode)
                    |
      +-------------+-------------+
      |             |             |
    stats       decision       push
                                 |
                    Markdown / JSON Export
```
</details>



<details>
<summary><strong>CurioKids</strong> — AI-assisted educational platform</summary>

> AI-assisted educational platform for early learners.

**Repository:** https://github.com/AlchemistReturns/CurioKids

### Highlights

- Built CurioKids, a cross-platform React Native/Expo educational app with dual parent/child dashboards, an interactive lesson engine, and gamified mini-games (math, literacy, motor skills) for early learners.
- Designed a Node.js/Express backend with Firebase Authentication and Firestore, syncing progress in real time to give parents actionable analytics and drive point-based rewards and leaderboards.
- Integrated an AI chatbot via a self-hosted RAG service (FastAPI + Ollama, Dockerized), enabling local LLM-backed learning assistance without external API dependencies.

### Architecture

```text
                     React Native App
                            |
         +------------------+-------------------+
         |                                      |
   Parent Dashboard                      Child Dashboard
         |                                      |
         +------------------+-------------------+
                            |
                    Node.js / Express
                            |
          +-----------------+----------------+
          |                                  |
   Firebase Auth                     Firestore
          |                                  |
          +-----------------+----------------+
                            |
                     FastAPI RAG Service
                            |
                         Ollama LLM
```
</details>

# Technical Toolkit

![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=for-the-badge&logo=langgraph&logoColor=white)
![LangSmith](https://img.shields.io/badge/LangSmith-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![Multi--Agent](https://img.shields.io/badge/Multi--Agent%20Systems-4B5563?style=for-the-badge&logo=robotframework&logoColor=white)
![RAG](https://img.shields.io/badge/RAG-4B5563?style=for-the-badge&logo=databricks&logoColor=white)
![Fine--tuning](https://img.shields.io/badge/Model%20Fine--tuning-4B5563?style=for-the-badge&logo=pytorch&logoColor=white)

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Gin](https://img.shields.io/badge/Gin-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![NoSQL](https://img.shields.io/badge/NoSQL-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)

---

<div align="center">

*"Intelligence is the system. I build what holds it up."*

</div>
