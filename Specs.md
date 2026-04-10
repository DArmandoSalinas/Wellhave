Project Specification: WellHave
1. Project Overview
WellHave is a proactive mental health and productivity application designed to predict and prevent occupational burnout. Unlike static trackers, WellHave uses Machine Learning (ML) to quantify burnout risk and a Large Language Model (LLM) to provide personalized, empathetic coaching.

2. Core Features
Predictive Assessment: A daily "Pulse Check" (survey) that captures workload, sleep quality, social support, and emotional energy.

Burnout Risk Engine: A classification model that categorizes user risk into: Low, Moderate, or High.

AI Wellness Coach: An LLM-driven interface that interprets the ML results and provides actionable advice based on the user's specific pain points.

Trends Dashboard: Visual representation of stress and recovery patterns over time.

3. Technical Stack (The "Cursor" Context)
Backend: Python with FastAPI.

ML Core: Scikit-learn or XGBoost (Binary or Multi-class classification).

LLM Integration: OpenAI API (GPT-4o) or Anthropic API via LangChain.

Mobile Frontend: React Native (Expo) or Flutter (Targeting iOS/App Store).

Database: Supabase (PostgreSQL + Auth) for user data and history.

4. Repository Structure
Plaintext
/wellhave
├── /backend            # FastAPI server & LLM logic
│   ├── /app/main.py    # API entry point
│   ├── /app/ml_model.py# Inference logic
│   └── requirements.txt
├── /mobile-app         # React Native/Expo frontend
├── /ml-research        # Jupyter Notebooks for training
│   ├── training.ipynb
│   └── burnout_model.pkl
└── /data               # Dataset samples and schemas
5. API "Contract" (Instruction for Cursor)
The backend should expose a POST /predict endpoint that:

Receives JSON containing features (hours_slept, workload_score, etc.).

Runs the .pkl ML model to get a risk_level.

Passes the risk_level and raw data to the LLM to generate a recovery_plan.

Returns a combined JSON object to the mobile app.