# 🌍 Global Commodities Ecosystem

> Plataforma de inteligência e análise para o mercado global de commodities agrícolas.

---

## 🏗️ Arquitetura

O ecossistema é composto por três serviços principais que se comunicam entre si:

```
┌─────────────────────┐        ┌──────────────────────┐        ┌─────────────────────────┐
│  valor-news-client  │ ←────→ │  valor-platform-api  │ ←────→ │  valor-platform-worker  │
│   Next.js / TS      │        │   Django / Python    │        │   Celery / Python       │
│   (Frontend)        │        │   (Backend REST API) │        │   (Jobs Assíncronos)    │
└─────────────────────┘        └──────────────────────┘        └─────────────────────────┘
                                          │
                              ┌───────────┴───────────┐
                              │                       │
                         PostgreSQL               MongoDB
                         Redis                   AWS S3
```

---

## 📦 Repositórios

### Core

| Repositório | Descrição | Stack | Versão |
|---|---|---|---|
| [valor-platform-api](https://github.com/valor-consultoria/valor-platform-api) | Backend REST API principal | Python 3.11+, Django 5, DRF | `0.6.3` |
| [valor-news-client](https://github.com/valor-consultoria/valor-news-client) | Frontend da plataforma | Next.js 14, React 18, TypeScript | — |
| [valor-platform-worker](https://github.com/valor-consultoria/valor-platform-worker) | Worker de jobs assíncronos | Python, Celery | — |

### Infraestrutura & Suporte

| Repositório | Descrição |
|---|---|
| [composes](https://github.com/valor-consultoria/composes) | Docker Compose files para deploy na nuvem |
| [workflow-templates](https://github.com/valor-consultoria/workflow-templates) | Templates reutilizáveis de GitHub Actions |
| [email-templates](https://github.com/valor-consultoria/email-templates) | Templates HTML de e-mail |
| [lab-graphs](https://github.com/valor-consultoria/lab-graphs) | Laboratório de componentes de gráficos |

---

## 🛠️ Stack de Tecnologias

### Backend (`valor-platform-api`)
- **Framework:** Django 5 + Django REST Framework
- **Auth:** JWT via `djangorestframework-simplejwt`
- **Bancos:** PostgreSQL + MongoDB
- **Cache / Fila:** Redis + Celery
- **Storage:** AWS S3 (boto3)
- **Docs:** OpenAPI automático via `drf-spectacular`
- **Deploy:** Docker + Gunicorn + Whitenoise
- **Testes:** pytest-django

### Frontend (`valor-news-client`)
- **Framework:** Next.js 14 (App Router)
- **UI:** Tailwind CSS + Radix UI + Framer Motion
- **Gráficos:** Recharts
- **Data fetching:** SWR + Axios
- **Validação:** Zod
- **Arquitetura:** Feature-based (`features/auth`, `features/markets`)
- **Testes:** Jest + Testing Library

### Worker (`valor-platform-worker`)
- **Task queue:** Celery + Redis
- **Integrações:** Gmail API (envio de e-mails)
- **Package manager:** Poetry

---

## 🚀 Como começar

### Pré-requisitos

- Python 3.11+
- Node.js 18+
- Docker & Docker Compose
- PostgreSQL, MongoDB e Redis (ou via `composes`)

### Rodando com Docker

```bash
# Clone o repositório de infraestrutura
git clone https://github.com/valor-consultoria/composes
cd composes
docker compose up -d
```

### Desenvolvimento local

```bash
# Backend
git clone https://github.com/valor-consultoria/valor-platform-api
cd valor-platform-api
cp .env.example .env
make run

# Frontend
git clone https://github.com/valor-consultoria/valor-news-client
cd valor-news-client
cp .env.example .env
npm install && npm run dev
```

---

## 👥 Time

| Dev | GitHub |
|---|---|
| Victor Martins | [@vmartins929292](https://github.com/vmartins929292) |
| Gustavo Henrique | [@gustavohc](https://github.com/gustavohc) |
| Leandro de Lima | [@LeandrodeLimaC](https://github.com/LeandrodeLimaC) |

---

<p align="center">
  <sub>© 2026 Global Commodities Ecosystem — Valor Ag Commodities</sub>
</p>
