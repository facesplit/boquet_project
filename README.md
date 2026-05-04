---

## 🤖 Enabling Real AI Generation

By default, the platform uses `AI_PROVIDER=mock`, so backend returns mock responses. To enable real generation

1. Run ComfyUI locally (see `ai/` and project instructions).
2. Start or get access to an OpenAI-compatible LLM endpoint (vLLM, LM Studio, llama.cpp server, etc.).
3. Set `AI_PROVIDER=comfyui` in `.env`, fill in `LLM_*` and `COMFYUI_*` variables.
4. Run `make down && make up`.

Pipeline parameters (sampler, dimensions, variant budgets) are editable by superadmin in **Settings -> AI Config** (`/superadmin/ai-config`).

---

## 🛠 Makefile Commands

| Command | Description |
| :--- | :--- |
| `make up` | docker compose up -d --build — build and start full stack in background |
| `make down` | stop and remove containers (volumes remain) |
| `make build` | rebuild images without starting services |
| `make logs` | stream logs of all services (`Ctrl+C` to exit) |
| `make ps` | list running services and their status |
| `make migrate` | run Alembic migrations (`alembic upgrade head`) |
| `make seed` | load seed data (`python -m app.cli.seed`) |
| `make test` | run pytest inside backend container |
| `make shell` | open bash in running backend container |

---

## 📂 Repository Structure

*   `backend/` — FastAPI: `app/`, `alembic/`, `tests/`, `pyproject.toml`, `Dockerfile`
*   `frontend/` — React + Vite: `src/`, `public/`, `vite.config.ts`, `Dockerfile`, `nginx.conf`
*   `ai/` — ComfyUI portable + workflow drivers and instructions
*   `docs/` — Specs and implementation plans (`superpowers/specs`, `superpowers/plans`)
*   `docker-compose.yml`
*   `Makefile`
*   `.env.example`

---

## 📞 Contact

*   **Developer:** Aldanaev Assylkhan
*   **Email:** [aseksuper@gmail.com](mailto:aseksuper@gmail.com)
*   **Project Demo:**# 🌸 Bouquet AI Platform

**Bouquet AI** is a professional, production-grade platform designed for AI-assisted floral ordering. It bridges the gap between customer imagination and floristry by combining a modern e-commerce flow with generative AI (Stable Diffusion via **ComfyUI**) and **LLM-powered** consultations.

[![Project Demo](https://img.shields.io/badge/Demo-YouTube-red?style=for-the-badge&logo=youtube)](https://youtu.be/GOu0d4LSTX8)

---

## ✨ Key Features
*   **AI Bouquet Generation:** Generate unique floral arrangements using Stable Diffusion via **ComfyUI**.
*   **Intelligent Assistant:** Integrated **LLM** (OpenAI-compatible) to provide personalized flower recommendations and advice.
*   **Complete Ordering Cycle:** Seamless transition from AI visualization to shopping cart and order processing.
*   **Advanced Admin Panel:** Manage orders, gallery, and fine-tune AI parameters (samplers, models, and generation budgets).
*   **Scalable Architecture:** Fully containerized setup for easy deployment and local development.

---

## 🛠 Tech Stack
*   **Backend:** FastAPI (Python 3.12), SQLAlchemy 2.0 (PostgreSQL 16), Alembic.
*   **Frontend:** React 18 / Vite.
*   **AI Pipeline:** ComfyUI + OpenAI-compatible API (vLLM, LM Studio, or OpenAI).
*   **Infrastructure:** Docker Compose, Nginx.

---

## 🚀 Quick Start (Docker)

The fastest way to get the platform running is using Docker:

1. **Clone and Setup**
   ```bash
   git clone <your-repo-url>
   cd bouquet
   cp .env.example .env
