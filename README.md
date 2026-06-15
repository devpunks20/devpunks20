<div align="center">

# Danil

**Fullstack / Backend Developer** · 6 years of experience

[![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=500&size=22&pause=1000&color=36BCF7&center=true&vCenter=true&width=600&lines=Go+%7C+Python+%7C+React;Microservices+%26+real-time;Telegram+%7C+Web3+%7C+AI+products)](https://git.io/typing-svg)

<br/>

[![Telegram](https://img.shields.io/badge/Telegram-@go__rshok-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/go_rshok)
[![GitHub](https://img.shields.io/badge/GitHub-devpunks20-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/devpunks20)

</div>

---

## 👋 About me

Fullstack developer with **6 years of experience**, with a backend core in **Go** and **Python**. I design and grow products end-to-end: from APIs and databases to React interfaces, fault-tolerant infrastructure, and CI/CD.

I specialize in microservices, real-time systems (WebSocket, WebRTC, gRPC), distributed fault-tolerant systems (Docker Swarm, PostgreSQL HA, multi-region), Telegram products, **DeFi on TON** (DEX aggregation, indexers), AI integrations, billing, and B2B platforms.

---

## 🛠 Skills

#### Backend
Go (Gin, Echo) · Python (Django, Django Ninja, FastAPI, aiogram) · gRPC (streaming) · REST · WebSocket · JWT · 2FA / TOTP · protobuf · Swagger · Celery · Celery Beat

#### Databases & cache
PostgreSQL · **PostgreSQL HA (Patroni + etcd + HAProxy + PgBouncer)** · replication · RO/RW split · Redis · Redis Sentinel · ClickHouse · Bun · GORM · pgx · SQL migrations (goose)

#### Real-time & streaming
WebRTC · WebSocket · NATS · HTTP/3 · QUIC · WebTransport · message brokers

#### Frontend
React · Next.js · TypeScript · Vite · Tailwind CSS · TanStack Query / Table · Telegram Mini Apps

#### AI & media generation
[OpenAI](https://openai.com/) · [ElevenLabs](https://elevenlabs.io/) (TTS/STT) · [fal.ai](https://fal.ai/) · [kie.ai](https://kie.ai/) · LLM · image / video / audio generation

#### Blockchain & DeFi
[TON](https://ton.org/) · DEX aggregators · blockchain indexer · swap routing · multi-hop paths · Jettons · TON Connect

#### Payments & Web3
Stripe · Robokassa · [Privy](https://www.privy.io/) · Plaid · Solana · webhooks

#### Messaging
Telegram Bot API · Telegram Mini Apps

#### DevOps & observability
Docker · Docker Compose · **Docker Swarm** · **Ansible** · **GlusterFS** · Nginx · nginx-proxy / acme-companion · Let's Encrypt · GitHub Actions (self-hosted runners) · private Docker registry · zero-downtime deployments · Prometheus · **VictoriaMetrics** · **VictoriaLogs** · **Vector** · **Grafana** · **Alertmanager** · node-exporter · cAdvisor · structured logging

#### Other
Git · Linux · multi-region / fault-tolerant systems · data parsing (PDF, Excel) · i18n

---

## 💼 Experience

### Fullstack Developer — [Signvano](https://sgvno.com)
`08.2025 — present`

A real-time video streaming and content generation platform (sign language, AI avatars).

**What I did:**
- Designed a distributed architecture: an **API Gateway** (Go) plus standalone **streaming servers** with gRPC service discovery and load balancing
- Built the video pipeline: WebSocket / **HTTP/3 + QUIC (WebTransport)** → WebRTC SFU → **NATS** → GPU clients over gRPC
- Created a **task queue** abstraction (PostgreSQL / Redis) for content generation without code changes
- Integrated **Stripe billing**: subscriptions, checkout, webhooks
- Built a React **admin panel**: CRUD, analytics, monitoring of streaming services
- Set up **CI/CD** (GitHub Actions): automated deployment of streaming nodes across multiple servers

**Result:** a production-ready platform with horizontal streaming scalability, monetization, and automated infrastructure deployment.

`Go` · `gRPC` · `PostgreSQL` · `Redis` · `NATS` · `WebRTC` · `HTTP/3` · `React` · `TypeScript` · `Docker` · `GitHub Actions`

---

### Backend Developer — [RPine](https://rpine.xyz/)
`2023 — present`

A startup in the **TON** ecosystem: a smart **DEX aggregator** that finds the best rates across decentralized exchanges, builds the optimal swap route, and provides transparent fees with no hidden markups ([rpine.xyz](https://rpine.xyz/)).

**What I did:**
- Developed the platform **backend**: APIs for quotes, swaps, and integration with several TON DEXs (liquidity aggregation from 4+ exchanges)
- Built a **TON blockchain indexer**: indexing of transactions, pools, and swap events for up-to-date pricing and in-product analytics
- Designed the **Pathfinder** — an engine that finds the most profitable swap route, including through intermediate tokens (multi-hop routing)
- Built the core of the **DEX aggregator**: smart rate discovery, route comparison, swap optimization accounting for fees and slippage
- Developed the **Telegram bot** (RPine App): token swaps, wallet connection, **private pools** with a price guaranteed at the moment a trade starts
- Maintained adjacent ecosystem products: NFT utilities, multisig for teams and DAOs

**Result:** a production DeFi product on TON with smart swap routing, transparent pricing, and an easy entry point via Telegram — from on-chain data indexing to trade execution in the bot.

`Go` · `Python` · `PostgreSQL` · `Redis` · `TON` · `Telegram Bot API` · `Docker`

---

### Backend / Infrastructure Developer — [VNISH Monitoring](https://vnish-monitoring.com/)
`03.2025 — present`

A multi-region monitoring platform for ASIC miners running VNISH firmware: real-time telemetry, alerts, group operations, a Telegram Mini App, and a custom fault-tolerant infrastructure.

**Backend & product:**
- Go backend: **gRPC streaming** for agents + a REST API (**Echo**) to ingest and serve telemetry; Bun / pgx, JWT, **2FA (TOTP)**, goose migrations, Swagger
- Real-time collection and aggregation of metrics (hashrate, temperature, fan, power consumption) + **micro-batching** of status writes (in-memory coalescing by MAC → bulk INSERT) so writes don't block the hot path
- An **alerting and Telegram notification** system for anomalies + email notifications via a self-hosted mail server
- A **Telegram Mini App** in React 19 / TypeScript / Vite / Tailwind / TanStack Query: dashboards, group operations over farms, i18n
- **Agentless monitoring** via VNISH firmware + a custom agent (binary built per-partner via ldflags)
- **Multi-region mesh**: cross-domain access to ASICs via Redis presence + peer gRPC federation

**Infrastructure (designed and deployed from scratch):**
- A **Docker Swarm** cluster across 7 nodes in 3 regions (COM/RU/US), per-site placement, **zero-downtime** rolling updates (start-first)
- **PostgreSQL HA**: Patroni + etcd + HAProxy + per-node PgBouncer, RO/RW split (reads from replicas), a dual **cluster ↔ single-master** mode and auto-promote on site isolation (`site-warden`)
- **GlusterFS** — shared storage (agent binaries, certificates, configs) across all nodes
- **Observability**: VictoriaMetrics + vmagent + VictoriaLogs + Vector + Grafana + vmalert + Alertmanager (per-node, gossip HA), node-exporter / cAdvisor / postgres / redis exporters
- **Edge**: nginx-proxy + acme-companion (Let's Encrypt) + an internal per-node nginx (gRPC/HTTP routing)
- **CI/CD**: GitHub Actions + self-hosted runners on the manager node, a private Docker registry, automated image builds and service rollout
- Full **cluster bootstrap via Ansible** (prereqs → Swarm → secrets → stack → edge)

**Result:** a fault-tolerant multi-region mining-farm monitoring platform with a real-time dashboard, alerts, group operations, and fully automated infrastructure deployment.

`Go` · `Echo` · `gRPC` · `WebSocket` · `Bun` · `pgx` · `PostgreSQL (Patroni/etcd/HAProxy/PgBouncer)` · `Redis` · `React` · `TypeScript` · `Docker Swarm` · `GlusterFS` · `Ansible` · `VictoriaMetrics` · `VictoriaLogs` · `Grafana` · `Alertmanager` · `Nginx` · `Let's Encrypt` · `GitHub Actions`

---

### Fullstack Developer — [SvetlanaBot](https://t.me/svetlanapsyybot)
`03.2026 — present`

An AI therapist on Telegram: chat with an LLM, a Mini App, subscriptions, content generation.

**What I did:**
- Go backend: Telegram webhook, REST API, a **WebSocket chat** with streaming LLM responses
- A **Telegram Mini App** in React: chat, onboarding, premium, files, voice messages
- Integrations: **OpenAI**, **ElevenLabs** (TTS/STT), **fal.ai** / **kie.ai** (images)
- **Robokassa billing**: subscriptions, recurring payments, a credit system, personalized payment links
- A **bulk broadcast** system with rate limiting and backoff on Telegram API limits
- **Observability**: Prometheus + Grafana (App, Postgres, Redis, Docker)

**Result:** a commercial AI product with monetization, real-time chat, and a full journey from onboarding to a premium subscription.

`Go` · `PostgreSQL` · `Redis` · `React` · `TypeScript` · `Docker` · `Prometheus` · `Grafana`

---

### Backend Developer — [PhotoPingvin Bot](https://t.me/photopingvin_bot)
`02.2025 — present`

A Telegram bot for generating photos, videos, and music.

**What I did:**
- Backend: **aiogram** + a REST API on **Django Ninja**
- An asynchronous generation pipeline: **Celery + Celery Beat**, queues on Redis
- Integration of AI providers (**fal.ai**, **kie.ai**, and others) for photo, video, and audio
- **Robokassa**: billing, user balance, paying for generations

**Result:** reliable background processing of long-running AI jobs with monetization via Telegram, without blocking the bot.

`Python` · `Django` · `Django Ninja` · `aiogram` · `Celery` · `Redis` · `PostgreSQL` · `Docker`

---

### Fullstack Developer — [Screener Exchange Spread](https://screener-spread.rpine.xyz/) · pet project · [RPine Lab](https://rpine.xyz/)
`01.2025 — present`

A spread screener and trading bot for crypto exchanges (RPine ecosystem).

**What I did:**
- Collection of quotes from multiple exchanges, computation of **spreads** and arbitrage opportunities in real time
- **Trading logic** and notifications about profitable pairs
- A React dashboard with live data
- Authentication via **Telegram**

**Result:** a tool for monitoring cross-exchange spreads and automating trading decisions in a single interface.

`Go` · `Python` · `PostgreSQL` · `Redis` · `React` · `TypeScript` · `Docker`

---

### Fullstack Developer — [Otty ASL](https://otty.go-rshok.ru)
`04.2026 — present`

An EdTech platform for learning American Sign Language (ASL).

**What I did:**
- Gamified learning: **lessons, dictionary, practice, leaderboard**
- User progress: streaks, daily tasks, a rewards system
- A **subscription** and trial monetization model
- Fullstack: backend + React frontend

**Result:** an interactive ASL learning platform with retention through gamification and a clear user journey.

`React` · `TypeScript` · `PostgreSQL` · `Docker`

---

### Fullstack Developer — [Pagga](https://github.com/devpunks20/pagga)
`11.2025 — 01.2026`

A Web3 SaaS for crypto companies: contracts, signatures, treasury, compliance.

**What I did:**
- Go backend + a **Next.js** dashboard
- **AI agents** (Hub & Spoke): generation of SAFE, NDA, and employment agreements via an LLM
- **E-signatures**: email and wallet (MetaMask, WalletConnect) via **Privy**
- Treasury: **Solana** wallets + **Plaid** for fiat accounts
- A Telegram bot for notifications and interaction

**Result:** an all-in-one platform for crypto startups — from contract generation to signing and financial analytics in a single product.

`Go` · `Gin` · `GORM` · `PostgreSQL` · `Next.js` · `TypeScript` · `Privy` · `Plaid` · `Docker`

---

### Backend Developer — [GetRealPrice](https://getrealprice.com)
`05.2022 — 05.2023`

A B2B SaaS: product matching and price monitoring for retail and FMCG ([13 countries](https://getrealprice.com/)).

**What I did:**
- Backend on **Django** and **FastAPI**: REST APIs for B2B clients
- Asynchronous **price parsing and monitoring** via Celery workers
- **Product matching** — matching the same product across marketplaces and stores
- PostgreSQL + Redis optimization: queues, caching of frequent queries

**Result:** a scalable backend for price monitoring and product matching, used by enterprise clients in multiple countries.

`Python` · `Django` · `FastAPI` · `Celery` · `Redis` · `PostgreSQL` · `Docker`

---

## 🎓 Education

**Vocational secondary education**  
Major: **Programmer**

---

<div align="center">

**Open to interesting projects and opportunities**

[![Telegram](https://img.shields.io/badge/Message_on_Telegram-@go__rshok-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/go_rshok)

<br/>

<sub>Last updated: June 2026</sub>

</div>
