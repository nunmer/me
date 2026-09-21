# Personal Website — Content

Status: Final draft, ready for implementation.

---

## Hero

**Sanzhar Yermek**
Full-Stack Engineer & AI Systems Architect

Building sovereign AI infrastructure and production systems at scale — from on-premise LLM clusters serving an entire bank to voice pipelines that understand agents in real time.

📍 Astana, Kazakhstan · [GitHub](https://github.com/nunmer) · [LinkedIn](https://linkedin.com/in/sanzharyermek/)

---

## About

I'm a full-stack developer and AI systems architect working at the intersection of large language models, distributed infrastructure, and real-world enterprise constraints. At ForteBank's AI Department, I design and operate the systems that let one of Kazakhstan's largest banks run generative AI entirely on its own infrastructure — no data ever leaves the perimeter.

My work spans the full stack of modern AI engineering: standing up self-hosted model clusters and the gateways that govern them, building OCR and vision pipelines that read contracts a human would take minutes to parse, and architecting voice analytics systems that turn thousands of hours of call-center audio into actionable, per-agent intelligence. I care about systems that are fast in production, not just fast in a demo — sub-second latency under real load, horizontal scaling that holds up at 3am, and architecture that survives contact with actual users.

Outside of work, I prototype and ship independent projects — from civic-tech platforms to conversational banking assistants — usually going from architecture diagram to working system in days, not sprints.

---

## Experience

### ForteBank — AI Department
**Full-Stack Software Developer** · April 2025 – Present

**Sovereign AI Infrastructure**
Designed and operate a self-hosted LLM cluster (GPT-OSS-120B, Qwen family) delivering enterprise-grade generative AI with zero data egress — every token stays on-premise. Built LiteLLM into a unified governance layer that routes, logs, and audits every model call across the organization, currently powering 160 active subscriptions across 15 departments. This is the backbone that lets legal, compliance, and customer-facing teams use frontier-grade AI without ever touching a third-party API.

**Intelligent Document Intelligence Platform**
Architected a production OCR/VLM microservice fusing multiple local vision models (GLM, DeepSeek-OCR, HunyuanVision) with advanced image preprocessing to extract structured data from contracts — including handwriting, stamps, and signatures — entirely offline. Deployed on Kubernetes with autoscaling from 3 to 20 replicas under Prometheus-driven load management, holding document processing latency in the 100–500ms range even under bursty enterprise traffic.

**Contact-Center Voice Intelligence**
Built an end-to-end voice analytics pipeline that transcribes live agent calls, runs NLP-based quality scoring, and surfaces per-agent KPI dashboards in near real time — giving management a live pulse on communication quality across the entire contact center, replacing what used to be manual spot-checks with continuous, automated coverage.

**24/7 Omnichannel Virtual Assistant**
Designed and shipped a multi-channel banking chatbot spanning the mobile app, WhatsApp, and Telegram, absorbing 40–50% of contact-center call volume during peak hours — effectively adding a full shift of capacity without adding headcount.

### ForteBank — Data Department
**Full-Stack Software Developer** · Feb 2023 – April 2025

Engineered an internal data platform that eliminated $40K+/month in redundant costs, and built the GitLab CI/CD backbone enabling zero-downtime deploys across all production services. Orchestrated complex Airflow DAGs automating large-scale data processing across business units, and scaled an internal analytics portal to 9 departments and 120+ daily users — cutting time-to-insight from days to minutes.

### Snoonu
**Back-end Intern** · Qatar (Remote) · Sep – Dec 2021

Shipped backend features for a high-scale food delivery platform in .NET C#, working across distributed teams in Qatar, the US, and UAE to keep order-management APIs and delivery contracts in sync across time zones.

---

## Independent & Exploratory Projects

Beyond my day job, I design and build full systems end-to-end — usually solo, usually fast.

**Konsul.kz — Visa Application Intelligence Platform** · *In Progress*
A civic-tech platform helping Kazakhstani citizens navigate visa applications with a deterministic success-probability scoring engine and LLM-powered guidance for complex cases. Architected as a Next.js 14 / FastAPI / PostgreSQL monorepo with KZ-native payment rails (Kaspi Pay, Epay) and a cloud-native deployment target on ECS Fargate and Amplify — built to go from prototype to production-grade fintech-adjacent infrastructure without a rewrite.

**Voice Assistant Configuration Portal** · *In Progress*
A multi-tenant SaaS platform letting businesses configure and deploy their own inbound-call voice assistants without touching code — built on a Twilio telephony bridge, designed from day one for multi-organization isolation and self-service configuration.

**Conversational Banking Assistant**
A Telegram-based banking assistant combining LLM-driven intent classification with a Redis-backed confirmation gate before executing real financial actions through a core banking API — full architecture diagrams, safety rails, and documentation included, designed so a misclassified intent can never move money.

**Tanba — Privacy-First Smart Link Platform** · *Coming Soon*
A cloud-native URL shortening and QR redirection platform planned on FastAPI, PostgreSQL, and Redis, with analytics designed around privacy-first principles — insight without surveillance. Full architecture, implementation, and design specs are complete; build is next.

**Segue — Browser-Native Auto-DJ** · *Concept*
An experimental auto-mixing DJ engine designed to run entirely in-browser on the Web Audio API — automatic beatmatching and transitions with zero backend audio processing. Currently a research spike into how far client-side signal processing can go before you need a server at all, with DRM constraints under active investigation.

**Terra Claims — Symbolic Land Trading Platform** · *Concept*
A speculative platform for collectible, symbolic territorial claims over real-world latitude/longitude coordinates — part game, part digital-collectibles market. Scoped around an off-chain Postgres/PostGIS foundation as the leanest path to a working MVP.

**Speech & Language Infrastructure for Central Asia** · *In Progress*
Designing shared API patterns for STT/TTS using the sans-IO principle, so the same logic runs cleanly across sync and async contexts. Currently evaluating local ASR engines (faster-whisper, NVIDIA Canary, Vosk) with a specific focus on Kazakh-language support — aiming to make high-quality speech AI a first-class citizen for Central Asian languages, not an afterthought.

**Status key:** *In Progress* = actively being built · *Coming Soon* = spec'd/documented, build not started · *Concept* = early research/exploration.

---

## Technical Skills

**Languages:** Go · Python · SQL · Bash
**Backend & Infra:** FastAPI · Django · React · Docker · Kubernetes · GitLab CI/CD · AWS (S3, Kiro) · Nginx · Linux
**Data Engineering:** Airflow · NiFi · Greenplum · PostgreSQL · Oracle
**AI/ML Systems:** On-premise LLM deployment · LiteLLM gateway architecture · OCR/VLM pipelines · ASR/Speech analytics · Model serving at scale

---

## Education

**Astana IT University** — B.S. Computer Science, 2020–2023, Nur-Sultan, Kazakhstan

---

## Contact

- Email: sanzharyermek@gmail.com
- GitHub: github.com/nunmer
- LinkedIn: linkedin.com/in/sanzharyermek/
