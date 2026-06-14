# 🌍 Global Commodities Ecosystem

> Plataforma de inteligência e análise para o mercado global de commodities agrícolas.

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

---

<p align="center">
  <sub>© 2026 Global Commodities Ecosystem — Valor Ag Commodities</sub>
</p>
