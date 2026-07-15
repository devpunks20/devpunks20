<div align="center">

# Danil

**Fullstack / Backend Developer** · 6 years of experience

[![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=500&size=22&pause=1000&color=36BCF7&center=true&vCenter=true&width=600&lines=Go+%7C+Python+%7C+React;Microservices+%26+real-time;Telegram+%7C+Web3+%7C+AI+products)](https://git.io/typing-svg)

<br/>

[![Telegram](https://img.shields.io/badge/Telegram-@go__rshok-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/go_rshok)
[![GitHub](https://img.shields.io/badge/GitHub-devpunks20-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/devpunks20)

<br/>

**EN** · [RU](README.ru.md)

</div>

---

## 👋 About me

Fullstack developer with **6 years of experience**, with a backend core in **Go** and **Python**. I design and grow products end-to-end: from APIs and databases to React interfaces, fault-tolerant infrastructure, and CI/CD.

I specialize in microservices, real-time systems (WebSocket, WebRTC, gRPC), distributed fault-tolerant systems (Docker Swarm, PostgreSQL HA, multi-region), cross-platform desktop apps with native Rust audio (Tauri / Electron, speech-to-speech and **sign-language** translation), Telegram products, **DeFi on TON** (DEX aggregation, indexers), AI integrations, billing, and B2B platforms.

---

## 🛠 Skills

#### Backend
Go (Gin, Echo) · Python (Django, Django Ninja, FastAPI, aiogram) · gRPC (streaming) · REST · WebSocket · JWT · 2FA / TOTP · protobuf · Swagger · Celery · Celery Beat

#### Databases & cache
PostgreSQL · **PostgreSQL HA (Patroni + etcd + HAProxy + PgBouncer)** · replication · RO/RW split · Redis · Redis Sentinel · ClickHouse · Bun · GORM · pgx · SQL migrations (goose)

#### Real-time & streaming
WebRTC · WebSocket · NATS · HTTP/3 · QUIC · WebTransport · message brokers

#### Desktop & native audio
Rust (cpal, WASAPI, tokio, serde, **Axum**, **SQLx**) · **Tauri 2** · Electron · N-API · Android · real-time audio (PCM capture, resampling, loopback / virtual audio devices, PulseAudio/pactl) · seamless video playback

#### Frontend
React · Next.js · TypeScript · Vite · Tailwind CSS · TanStack Query / Table · Telegram Mini Apps · Chrome Extensions

#### AI & media generation
[OpenAI](https://openai.com/) · [Deepgram](https://deepgram.com/) (STT/TTS) · [Google Gemini](https://ai.google.dev/) / Gemini Live (gloss, real-time STT + translation + TTS) · [ElevenLabs](https://elevenlabs.io/) (TTS/STT) · Edge TTS · [fal.ai](https://fal.ai/) · [kie.ai](https://kie.ai/) · LLM · image / video / audio generation · **RIFE** / FFmpeg video pipelines

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

### Backend / Infrastructure Developer — [VNISH Monitoring](https://vnish-monitoring.com/)
`03.2025 — present`

A multi-region monitoring platform for ASIC miners running VNISH firmware: real-time telemetry, alerts, group operations, a Telegram Mini App, and a custom fault-tolerant infrastructure.

<table>
  <tr>
    <td width="50%"><img src="assets/projects/VNISH4.jpg" alt="VNISH — analytics dashboard" width="100%"/></td>
    <td width="50%"><img src="assets/projects/VNISH3.jpg" alt="VNISH — miner dashboard with charts" width="100%"/></td>
  </tr>
  <tr>
    <td width="50%"><img src="assets/projects/VNISH2.jpg" alt="VNISH — farm device list" width="100%"/></td>
    <td width="50%"><img src="assets/projects/VNISH1.png" alt="VNISH — farms overview" width="100%"/></td>
  </tr>
</table>

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

### Fullstack Developer — [Signvano](https://sgvno.com)
`08.2025 — present`

A real-time video streaming and content generation platform (sign language, AI avatars).

<img src="assets/projects/Signvano1.png" alt="Signvano — landing page" width="100%"/>

<table>
  <tr>
    <td width="50%"><img src="assets/projects/Signvano5.png" alt="Signvano — quick actions" width="100%"/></td>
    <td width="50%"><img src="assets/projects/Signvano2.png" alt="Signvano — cinematic avatars" width="100%"/></td>
  </tr>
  <tr>
    <td width="50%"><img src="assets/projects/Signvano3.png" alt="Signvano — text to sign video chat" width="100%"/></td>
    <td width="50%"><img src="assets/projects/Signvano6.png" alt="Signvano — video translator" width="100%"/></td>
  </tr>
  <tr>
    <td width="50%"><img src="assets/projects/Signvano4.png" alt="Signvano — translate from website" width="100%"/></td>
    <td width="50%"><img src="assets/projects/Signvano7.png" alt="Signvano — avatar creating" width="100%"/></td>
  </tr>
</table>

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

### Fullstack Developer — LiveVoice · pet project
`06.2026 — present`

A cross-platform desktop app for **real-time bidirectional voice translation** in video calls (e.g. Google Meet): the interlocutor's speech is translated into your headphones, and your speech is translated into a virtual microphone — live.

<img src="assets/projects/LiveVoice.png" alt="LiveVoice — desktop app session" width="100%"/>

**What I did:**
- Built a low-latency pipeline **audio capture → STT → translation → TTS** in both directions (incoming: peer → headphones; outgoing: mic → virtual mic)
- Wrote a native **audio engine in Rust** (cpal, **WASAPI loopback** on Windows, **PulseAudio / pactl** null-sink routing on Linux, resampling via rubato), exposed to Node via **N-API**
- Integrated multiple AI providers: **Deepgram** (live STT, TTS, Agent "think" translation over WebSocket), **Google Gemini Live** (unified STT + translation + TTS in a single WebSocket), **Kie**, and **Edge TTS**
- Implemented an **echo guard** (preventing the outgoing TTS from being re-captured and re-translated), a **TTS cache**, and **virtual microphone** routing (VB-Cable / null-sink)
- Designed a **Chrome extension** and a desktop UI (dashboard) over a shared WebSocket protocol (TypeScript + Zod)
- Leading a full **migration from Electron + Node to Tauri 2** with an all-Rust backend (single process, in-process PCM, no internal network hop)

**Result:** a working real-time speech-to-speech translation tool for live calls, with a native cross-platform audio stack and a pluggable set of STT/TTS/translation providers.

`Rust` · `cpal` · `WASAPI` · `Tauri` · `Electron` · `Node.js` · `TypeScript` · `Zod` · `WebSocket` · `Deepgram` · `Google Gemini Live` · `Edge TTS` · `Chrome Extension`

---

### Fullstack Developer — [SignSync](https://signsync.go-rshok.ru/) · pet project
`06.2026 — present`

A cross-platform **Russian Sign Language (RSL)** translator: speech or text → gloss → seamless avatar video. Desktop (Windows/Linux), Android, a product landing, and a Rust backend for auth, credits, STT proxy, and protected clip delivery.

<img src="assets/projects/SignSync1.png" alt="SignSync — desktop app (dark)" width="100%"/>

<table>
  <tr>
    <td width="68%"><img src="assets/projects/SignSync2.png" alt="SignSync — desktop app (light)" width="100%"/></td>
    <td width="32%"><img src="assets/projects/SignSync3.png" alt="SignSync — narrow / mobile layout" width="100%"/></td>
  </tr>
</table>

**What I did:**
- Built an end-to-end pipeline **mic / text → STT → Gemini gloss (РЖЯ) → playlist of seamless clips** with batch and **realtime** modes
- Shipped a **Tauri 2** app (React 19 / TypeScript / Vite / Tailwind + Rust): native **cpal** audio capture, provider keys in Stronghold, dual-layer **seamless video player** (crossfade, REST morph trim, Android WebView quirks)
- Wrote a **Rust API (Axum + SQLx + PostgreSQL)**: Telegram login (deeplink + webhook), JWT, users / **credits** / **api_key**, STT proxy (**Deepgram** / **ElevenLabs**, HTTP + WebSocket), release catalog and downloads
- Built a React landing with **Telegram QR / deeplink auth**, personal cabinet (API key, credits), and multi-platform download grid (AppImage, Windows, Android)
- Designed a GPU video pipeline (**RIFE** + FFmpeg): normalize every clip so it starts/ends on the same REST pose for jump-free chaining; video-manifest + nginx **`auth_request`** gate for `/clips/`
- Infra & CI: Docker Compose (backend, landing, nginx, Postgres), edge TLS, **GitHub Actions** builds for Linux / Windows / Android

**Result:** a working RSL translation product with cross-platform clients, Telegram-based accounts, monetization hooks (credits / API key), protected media delivery, and automated desktop/mobile releases.

`Rust` · `Axum` · `SQLx` · `PostgreSQL` · `Tauri 2` · `React` · `TypeScript` · `Vite` · `Tailwind` · `cpal` · `WebSocket` · `Deepgram` · `ElevenLabs` · `Google Gemini` · `Telegram Auth` · `Nginx` · `RIFE` · `Docker` · `GitHub Actions`

---

### Fullstack Developer — [SvetlanaBot](https://t.me/svetlanapsyybot)
`03.2026 — present`

An AI therapist on Telegram: chat with an LLM, a Mini App, subscriptions, content generation.

<table>
  <tr>
    <td width="42%"><img src="assets/projects/Svetlana.png" alt="SvetlanaBot — onboarding and menu" width="100%"/></td>
    <td width="58%"><img src="assets/projects/Svetlana2.png" alt="SvetlanaBot — streaming AI chat" width="100%"/></td>
  </tr>
</table>

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

### Backend Developer — [RPine](https://rpine.xyz/)
`2023 — present`

A startup in the **TON** ecosystem: a smart **DEX aggregator** that finds the best rates across decentralized exchanges, builds the optimal swap route, and provides transparent fees with no hidden markups ([rpine.xyz](https://rpine.xyz/)).

<img src="assets/projects/RPine1.png" alt="RPine — landing page" width="100%"/>

<table>
  <tr>
    <td width="68%"><img src="assets/projects/RPine2.png" alt="RPine — app section (Pathfinder, private pools)" width="100%"/></td>
    <td width="32%"><img src="assets/projects/RPine3.png" alt="RPine — Telegram mini app" width="100%"/></td>
  </tr>
</table>

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

### Fullstack Developer — [Screener Exchange Spread](https://screener-spread.rpine.xyz/) · pet project · [RPine Lab](https://rpine.xyz/)
`01.2025 — present`

A spread screener and trading bot for crypto exchanges (RPine ecosystem).

<img src="assets/projects/Screener1.png" alt="Screener — cross-exchange price comparison" width="100%"/>

<table>
  <tr>
    <td width="50%"><img src="assets/projects/Screener2.png" alt="Screener — trading bot strategies" width="100%"/></td>
    <td width="50%"><img src="assets/projects/Screener3.png" alt="Screener — live chart and trade log" width="100%"/></td>
  </tr>
</table>

**What I did:**
- Collection of quotes from multiple exchanges, computation of **spreads** and arbitrage opportunities in real time
- **Trading logic** and notifications about profitable pairs
- A React dashboard with live data
- Authentication via **Telegram**

**Result:** a tool for monitoring cross-exchange spreads and automating trading decisions in a single interface.

`Go` · `Python` · `PostgreSQL` · `Redis` · `React` · `TypeScript` · `Docker`

---

### Backend Developer — [PhotoPingvin Bot](https://t.me/photopingvin_bot)
`02.2025 — present`

A Telegram bot for generating photos, videos, and music.

<img src="assets/projects/Pingvin3.jpg" alt="PhotoPingvin — AI-generated photo" width="100%"/>

<table>
  <tr>
    <td width="50%"><img src="assets/projects/Pingvin.png" alt="PhotoPingvin — bot intro and menu" width="100%"/></td>
    <td width="50%"><img src="assets/projects/Pingvin2.png" alt="PhotoPingvin — generation flow" width="100%"/></td>
  </tr>
</table>

**What I did:**
- Backend: **aiogram** + a REST API on **Django Ninja**
- An asynchronous generation pipeline: **Celery + Celery Beat**, queues on Redis
- Integration of AI providers (**fal.ai**, **kie.ai**, and others) for photo, video, and audio
- **Robokassa**: billing, user balance, paying for generations

**Result:** reliable background processing of long-running AI jobs with monetization via Telegram, without blocking the bot.

`Python` · `Django` · `Django Ninja` · `aiogram` · `Celery` · `Redis` · `PostgreSQL` · `Docker`

---

### Fullstack Developer — [Otty ASL](https://otty.go-rshok.ru)
`04.2026 — present`

An EdTech platform for learning American Sign Language (ASL).

<img src="assets/projects/Otty.png" alt="Otty ASL — gamified learning dashboard" width="100%"/>

**What I did:**
- Gamified learning: **lessons, dictionary, practice, leaderboard**
- User progress: streaks, daily tasks, a rewards system
- A **subscription** and trial monetization model
- Fullstack: backend + React frontend

**Result:** an interactive ASL learning platform with retention through gamification and a clear user journey.

`React` · `TypeScript` · `PostgreSQL` · `Docker`

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

## 🎓 Education

**Vocational secondary education**  
Major: **Programmer**

---

<div align="center">

**Open to interesting projects and opportunities**

[![Telegram](https://img.shields.io/badge/Message_on_Telegram-@go__rshok-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/go_rshok)

<br/>

<sub>Last updated: July 2026</sub>

</div>
