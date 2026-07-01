# WellHave — AI Wellness & Burnout Prevention

[![Python 3.10+](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-backend-009688.svg)](https://fastapi.tiangolo.com/)
[![React Native](https://img.shields.io/badge/React%20Native-mobile-61DAFB.svg)](https://reactnative.dev/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Smart wellness platform that combines **machine learning burnout risk prediction** with **LLM-powered emotional coaching**.

**Author:** [Diego Armando Salinas Lugo](https://sites.google.com/tec.mx/salinasdiegoarmando/know-me)

---

## Core features

- **Daily Pulse Check** — workload, sleep, social support, emotional energy
- **Burnout Risk Engine** — ML classifier (Low / Moderate / High)
- **AI Wellness Coach** — personalized recovery plans via GPT-4o / LangChain
- **Trends Dashboard** — stress and recovery patterns over time

## Architecture

```
Wellhave/
├── backend/          # FastAPI server + ML inference + LLM logic
├── mobile-app/       # React Native (Expo) client
├── notebooks/        # Model training & research
├── data/             # Sample datasets and schemas
└── Specs.md          # Detailed technical specification
```

## Tech stack

| Layer | Stack |
|-------|-------|
| Backend | Python, FastAPI, scikit-learn / XGBoost |
| LLM | OpenAI GPT-4o via LangChain |
| Mobile | React Native (Expo) |
| Database | Supabase (PostgreSQL + Auth) |

## API contract

`POST /predict` accepts wellness features (sleep hours, workload score, etc.), runs the ML model for `risk_level`, and returns an LLM-generated `recovery_plan`.

## Getting started

See [Specs.md](Specs.md) for full architecture. Backend setup:

```bash
cd backend
pip install -r requirements.txt
uvicorn app.main:app --reload
```

## License

MIT — see [LICENSE](LICENSE).
