# Abrar Mahmud Hasan

Computer Science undergraduate who thinks like a CTO. Software engineer building production-grade and cost-efficient AI systems. Focused on system functionality, robustness and fault-tolerance.

---

### Featured Projects

* **HealthX**
    * Built HealthX, a full-stack telehealth platform (React/Vite, Node.js/Express, Firebase Auth) for underserved rural regions with unreliable connectivity, integrating Google Gemini for context-aware symptom analysis using patient history.
    * Designed a hybrid online/offline architecture with client-side image compression and a hardcoded fallback dataset, ensuring core diagnosis and hospital-lookup features remain functional on unstable 2G/3G networks.
    * Implemented a GPS-based hospital finder combining live OpenStreetMap/Overpass queries with an offline emergency database, plus one-tap Google Maps/Waze navigation handoff.
 
* **Valerix**
    * Designed a fault-tolerant Node.js/Express microservices architecture (Order, Inventory, API Gateway) implementing timeout-triggered fallback from synchronous HTTP calls to asynchronous RabbitMQ messaging, preventing request hangs during downstream service degradation.
    * Engineered idempotent message processing via an `IdempotencyLog` table to guarantee exactly-once inventory deduction under message retries/duplication, alongside indefinite connection-retry logic for self-healing broker reconnection on startup or outage.
    * Instrumented services with Prometheus (RED metrics) and Grafana dashboards, and built real-time latency-alerting in the frontend, enabling observability into distributed failure modes (simulated via a configurable latency-injection mechanism).

* **Grit**
    * Built grít, a Go CLI that hooks into git pre-commit, post-rewrite, and post-commit stages to run adaptive interviews, capturing the reasoning behind commits, dependency changes, and reverts.
    * Implemented a real-time file watcher with a keyword-based complexity scorer, vague-identifier detection, and paste/AI-assist heuristics, all configurable via .grit.yaml thresholds.
    * Designed a local-first SQLite (WAL mode) storage layer with per-repo isolation, plus `stats`, `decision` (ADR-style), and Markdown/JSON `push` export commands — no cloud dependency.

* **CurioKids**
    * Built CurioKids, a cross-platform React Native/Expo educational app with dual parent/child dashboards, an interactive lesson engine, and gamified mini-games (math, literacy, motor skills) for early learners.
    * Designed a Node.js/Express backend with Firebase Authentication and Firestore, syncing progress in real time to give parents actionable analytics and drive point-based rewards and leaderboards.
    * Integrated an AI chatbot via a self-hosted RAG service (FastAPI + Ollama, Dockerized), enabling local LLM-backed learning assistance without external API dependencies.

---

### Technical Toolkit

| Category | Technologies |
| :--- | :--- |
| **AI & Agentic Systems** | LangGraph, Model Fine-tuning, Multi-agent Architectures, RAG |
| **Full-stack** | FastAPI, Gin, Django, Spring Boot, Next.js, SQL, NoSQL |
| **Infra & Observability** | Docker, Kubernetes, Prometheus, Grafana, LangSmith |

---

### Professional Experience

**Software Engineering Intern | Intelsense AI** *January 2026 – April 2026* 
* Designed dashboards and interfaces that turn model output into business decisions.

**Junior Software Engineer | Shahrish Engineering & Construction Limited** *December 2024 – September 2025* 
* Delivered production-grade ERP system that reduced manual data handling by 90%.

---

### Achievements & Leadership

* **Champion:** Microservice & DevOps Hackathon, BUET CSE Fest 2026
* **1st Runner-up:** Future Builders 2025 AI Driven Cognitive Innovation Hackathon
* **Finalist:**  HackCSB Hackathon, Top 7 of 116 teams 
* **Contestant:** ACM ICPC Dhaka Regionals
* **Former Joint Secretary:** IUT Computer Society
* **Former General Secretary:** Notre Dame Science Club 
