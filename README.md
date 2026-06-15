<div align="center">

# Данил

**Fullstack / Backend Developer** · 6 лет опыта

[![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=500&size=22&pause=1000&color=36BCF7&center=true&vCenter=true&width=600&lines=Go+%7C+Python+%7C+React;Microservices+%26+real-time;Telegram+%7C+Web3+%7C+AI+products)](https://git.io/typing-svg)

<br/>

[![Telegram](https://img.shields.io/badge/Telegram-@go__rshok-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/go_rshok)
[![GitHub](https://img.shields.io/badge/GitHub-devpunks20-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/devpunks20)

</div>

---

## 👋 О себе

Fullstack-разработчик с **6-летним опытом**, основа — backend на **Go** и **Python**. Проектирую и развиваю продукты end-to-end: от API и баз данных до React-интерфейсов, отказоустойчивой инфраструктуры и CI/CD.

Специализация — микросервисы, real-time системы (WebSocket, WebRTC, gRPC), распределённые отказоустойчивые системы (Docker Swarm, PostgreSQL HA, multi-region), Telegram-продукты, **DeFi на TON** (DEX-агрегация, индексаторы), AI-интеграции, биллинг и B2B-платформы.

---

## 🛠 Навыки

#### Backend
Go (Gin, Echo) · Python (Django, Django Ninja, FastAPI, aiogram) · gRPC (streaming) · REST · WebSocket · JWT · 2FA / TOTP · protobuf · Swagger · Celery · Celery Beat

#### Базы данных и кэш
PostgreSQL · **PostgreSQL HA (Patroni + etcd + HAProxy + PgBouncer)** · репликация · RO/RW-split · Redis · Redis Sentinel · ClickHouse · Bun · GORM · pgx · SQL-миграции (goose)

#### Real-time и стриминг
WebRTC · WebSocket · NATS · HTTP/3 · QUIC · WebTransport · message brokers

#### Frontend
React · Next.js · TypeScript · Vite · Tailwind CSS · TanStack Query / Table · Telegram Mini Apps

#### AI и генерация медиа
[OpenAI](https://openai.com/) · [ElevenLabs](https://elevenlabs.io/) (TTS/STT) · [fal.ai](https://fal.ai/) · [kie.ai](https://kie.ai/) · LLM · image / video / audio generation

#### Blockchain и DeFi
[TON](https://ton.org/) · DEX-агрегаторы · индексатор блокчейна · swap routing · multi-hop paths · Jettons · TON Connect

#### Платежи и Web3
Stripe · Robokassa · [Privy](https://www.privy.io/) · Plaid · Solana · webhooks

#### Messaging
Telegram Bot API · Telegram Mini Apps

#### DevOps и observability
Docker · Docker Compose · **Docker Swarm** · **Ansible** · **GlusterFS** · Nginx · nginx-proxy / acme-companion · Let's Encrypt · GitHub Actions (self-hosted runners) · private Docker registry · zero-downtime деплой · Prometheus · **VictoriaMetrics** · **VictoriaLogs** · **Vector** · **Grafana** · **Alertmanager** · node-exporter · cAdvisor · structured logging

#### Прочее
Git · Linux · multi-region / отказоустойчивые системы · парсинг данных (PDF, Excel) · i18n

---

## 💼 Опыт работы

### Fullstack Developer — [Signvano](https://sgvno.com)
`08.2025 — настоящее время`

Платформа real-time видеостриминга и генерации контента (жестовый язык, AI-аватары).

**Решение:**
- Спроектировал распределённую архитектуру: **API Gateway** (Go) + отдельные **streaming-сервера** с gRPC service discovery и балансировкой нагрузки
- Реализовал видеопайплайн: WebSocket / **HTTP/3 + QUIC (WebTransport)** → WebRTC SFU → **NATS** → GPU-клиенты по gRPC
- Сделал абстракцию **очереди задач** (PostgreSQL / Redis) для генерации контента без смены кода
- Внедрил **Stripe-биллинг**: подписки, checkout, webhooks
- Собрал **админ-панель** на React: CRUD, аналитика, мониторинг streaming-сервисов
- Настроил **CI/CD** (GitHub Actions): автодеплой streaming-нод на несколько серверов

**Результат:** production-ready платформа с горизонтальным масштабированием стриминга, монетизацией и автоматизированным деплоем инфраструктуры.

`Go` · `gRPC` · `PostgreSQL` · `Redis` · `NATS` · `WebRTC` · `HTTP/3` · `React` · `TypeScript` · `Docker` · `GitHub Actions`

---

### Backend Developer — [RPine](https://rpine.xyz/)
`2023 — настоящее время`

Стартап в экосистеме **TON**: smart **DEX-агрегатор** — находит лучшие курсы на децентрализованных биржах, строит оптимальный маршрут свопа и даёт прозрачные комиссии без скрытых надбавок ([rpine.xyz](https://rpine.xyz/)).

**Решение:**
- Разработал **backend** платформы: API для котировок, свопов и интеграции с несколькими TON DEX (агрегация ликвидности из 4+ бирж)
- Реализовал **индексатор блокчейна TON**: индексация транзакций, пулов и swap-событий для актуальных цен и аналитики в продукте
- Спроектировал **Pathfinder** — движок поиска наиболее выгодного маршрута обмена, в том числе через промежуточные токены (multi-hop routing)
- Собрал ядро **DEX-агрегатора**: smart rate discovery, сравнение маршрутов, оптимизация свопа с учётом комиссий и проскальзывания
- Разработал **Telegram-бот** (RPine App): обмен токенов, подключение кошелька, **private pools** с гарантированной ценой на момент начала сделки
- Поддерживал смежные продукты экосистемы: NFT-утилити, multisig для команд и DAO

**Результат:** production DeFi-продукт на TON с умным роутингом свопов, прозрачным ценообразованием и удобным входом через Telegram — от индексации on-chain данных до исполнения сделки в боте.

`Go` · `Python` · `PostgreSQL` · `Redis` · `TON` · `Telegram Bot API` · `Docker`

---

### Backend / Infrastructure Developer — [VNISH Monitoring](https://vnish-monitoring.com/)
`03.2025 — настоящее время`

Мульти-региональная платформа мониторинга ASIC-майнеров с прошивкой VNISH: real-time телеметрия, алерты, групповые операции, Telegram Mini App и собственная отказоустойчивая инфраструктура.

**Backend и продукт:**
- Backend на Go: **gRPC-стриминг** агентов + REST API (**Echo**) для приёма и отдачи телеметрии; Bun / pgx, JWT, **2FA (TOTP)**, миграции goose, Swagger
- Real-time сбор и агрегация метрик (hashrate, температура, fan, power consumption) + **микро-батчинг** записи статусов (in-memory склейка по MAC → bulk-INSERT), чтобы запись не блокировала горячий путь
- Система **алертов и Telegram-уведомлений** при отклонениях + email-уведомления через собственный mailserver
- **Telegram Mini App** на React 19 / TypeScript / Vite / Tailwind / TanStack Query: дашборды, групповые операции над фермами, i18n
- **Agentless-мониторинг** через прошивку VNISH + собственный агент (бинарник собирается per-партнёр через ldflags)
- **Multi-region mesh**: кросс-доменный доступ к ASIC через Redis presence + peer gRPC federation

**Инфраструктура (спроектировал и развернул с нуля):**
- **Docker Swarm** кластер на 7 нод в 3 регионах (COM/RU/US), per-site placement, **zero-downtime** rolling updates (start-first)
- **PostgreSQL HA**: Patroni + etcd + HAProxy + per-node PgBouncer, RO/RW-split (чтения с реплик), дуальный режим **cluster ↔ single-master** и авто-promote при изоляции площадки (`site-warden`)
- **GlusterFS** — разделяемое хранилище (бинарники агентов, сертификаты, конфиги) на всех нодах
- **Observability**: VictoriaMetrics + vmagent + VictoriaLogs + Vector + Grafana + vmalert + Alertmanager (per-node, gossip-HA), node-exporter / cAdvisor / postgres / redis exporters
- **Edge**: nginx-proxy + acme-companion (Let's Encrypt) + внутренний per-node nginx (gRPC/HTTP routing)
- **CI/CD**: GitHub Actions + self-hosted runners на manager-ноде, приватный Docker registry, автосборка образов и rollout сервисов
- Полный **bootstrap кластера через Ansible** (prereqs → Swarm → секреты → стек → edge)

**Результат:** отказоустойчивая мульти-региональная платформа мониторинга майнинг-ферм с real-time дашбордом, алертами, групповыми операциями и полностью автоматизированным деплоем инфраструктуры.

`Go` · `Echo` · `gRPC` · `WebSocket` · `Bun` · `pgx` · `PostgreSQL (Patroni/etcd/HAProxy/PgBouncer)` · `Redis` · `React` · `TypeScript` · `Docker Swarm` · `GlusterFS` · `Ansible` · `VictoriaMetrics` · `VictoriaLogs` · `Grafana` · `Alertmanager` · `Nginx` · `Let's Encrypt` · `GitHub Actions`

---

### Fullstack Developer — [SvetlanaBot](https://t.me/svetlanapsyybot)
`03.2026 — настоящее время`

AI-психолог в Telegram: чат с LLM, Mini App, подписки, генерация контента.

**Решение:**
- Backend на Go: Telegram webhook, REST API, **WebSocket-чат** с streaming LLM-ответов
- **Telegram Mini App** на React: чат, onboarding, premium, файлы, голосовые сообщения
- Интеграции: **OpenAI** / Geminab (LLM), **ElevenLabs** (TTS/STT), **fal.ai** / **kie.ai** (изображения)
- **Биллинг Robokassa**: подписки, recurring payments, кредитная система, персональные payment links
- Система **массовых рассылок** с rate limiting и backoff на лимиты Telegram API
- **Observability**: Prometheus + Grafana (App, Postgres, Redis, Docker)

**Результат:** коммерческий AI-продукт с монетизацией, real-time чатом и полным циклом от onboarding до premium-подписки.

`Go` · `PostgreSQL` · `Redis` · `React` · `TypeScript` · `Docker` · `Prometheus` · `Grafana`

---

### Backend Developer — [PhotoPingvin Bot](https://t.me/photopingvin_bot)
`02.2025 — настоящее время`

Telegram-бот для генерации фото, видео и музыки.

**Решение:**
- Backend: **aiogram** + REST API на **Django Ninja**
- Асинхронный пайплайн генерации: **Celery + Celery Beat**, очереди на Redis
- Интеграция AI-провайдеров (**fal.ai**, **kie.ai** и др.) для фото, видео и аудио
- **Robokassa**: биллинг, баланс пользователя, оплата генераций

**Результат:** стабильная обработка длительных AI-задач в фоне с монетизацией через Telegram без блокировки бота.

`Python` · `Django` · `Django Ninja` · `aiogram` · `Celery` · `Redis` · `PostgreSQL` · `Docker`

---

### Fullstack Developer — [Screener Exchange Spread](https://screener-spread.rpine.xyz/) · pet-проект · [RPine Lab](https://rpine.xyz/)
`01.2025 — настоящее время`

Скринер спредов и торговый бот для криптобирж (экосистема RPine).

**Решение:**
- Сбор котировок с нескольких бирж, расчёт **спредов** и арбитражных возможностей в real-time
- **Торговая логика** и уведомления о выгодных связках
- Frontend-дашборд на React с live-данными
- Авторизация через **Telegram**

**Результат:** инструмент для мониторинга межбиржевых спредов и автоматизации торговых решений в одном интерфейсе.

`Go` · `Python` · `PostgreSQL` · `Redis` · `React` · `TypeScript` · `Docker`

---

### Fullstack Developer — [Otty ASL](https://otty.go-rshok.ru)
`04.2026 — настоящее время`

EdTech-платформа для изучения американского жестового языка (ASL).

**Решение:**
- Gamified-обучение: **уроки, словарь, практика, рейтинг**
- Прогресс пользователя: streak, ежедневные задания, система наград
- **Подписка** и trial-модель монетизации
- Fullstack: backend + React frontend

**Результат:** интерактивная платформа обучения ASL с удержанием через геймификацию и понятным пользовательским путём.

`React` · `TypeScript` · `PostgreSQL` · `Docker`

---

### Fullstack Developer — [Pagga](https://github.com/devpunks20/pagga)
`11.2025 — 01.2026`

Web3 SaaS для crypto-компаний: контракты, подписи, treasury, compliance.

**Решение:**
- Backend на Go + dashboard на **Next.js**
- **AI-агенты** (Hub & Spoke): генерация SAFE, NDA, employment agreements через LLM
- **Электронные подписи**: email и wallet (MetaMask, WalletConnect) через **Privy**
- Treasury: **Solana**-кошельки + **Plaid** для fiat-счетов
- Telegram-бот для уведомлений и взаимодействия

**Результат:** all-in-one платформа для crypto-стартапов — от генерации контракта до подписи и финансовой аналитики в одном продукте.

`Go` · `Gin` · `GORM` · `PostgreSQL` · `Next.js` · `TypeScript` · `Privy` · `Plaid` · `Docker`

---

### Backend Developer — [GetRealPrice](https://getrealprice.com)
`05.2022 — 05.2023`

B2B SaaS: product matching и мониторинг цен для ритейла и FMCG ([13 стран](https://getrealprice.com/)).

**Решение:**
- Backend на **Django** и **FastAPI**: REST API для B2B-клиентов
- Асинхронный **парсинг и мониторинг цен** через Celery workers
- **Product matching** — сопоставление одного товара между маркетплейсами и магазинами
- Оптимизация PostgreSQL + Redis: очереди, кэширование частых запросов

**Результат:** масштабируемый backend для мониторинга цен и matching товаров, используемый enterprise-клиентами в нескольких странах.

`Python` · `Django` · `FastAPI` · `Celery` · `Redis` · `PostgreSQL` · `Docker`

---

## 🎓 Образование

**Среднее профессиональное образование**  
Специальность: **программист**

---

<div align="center">

**Открыт к интересным проектам и предложениям**

[![Telegram](https://img.shields.io/badge/Написать_в_Telegram-@go__rshok-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/go_rshok)

<br/>

<sub>Последнее обновление: июнь 2026</sub>

</div>
