# Unified Agentic Observability & Root Cause Analysis Platform

AI-Powered Incident Intelligence for Enterprise Operations

## Overview

The Unified Agentic Observability & Root Cause Analysis (RCA) Platform is an AI-driven incident investigation system designed to reduce Mean Time To Repair (MTTR) across enterprise IT environments.

The platform automates the complete incident lifecycle, including:

* Anomaly Detection
* Severity Classification
* Root Cause Prediction
* Historical Incident Retrieval
* Knowledge-Based Remediation
* Automated RCA Report Generation

By combining Machine Learning, Agentic Workflows, Vector Search, and Observability Analytics, the platform transforms raw telemetry into actionable operational intelligence.

---

## Problem Statement

Enterprise operations teams often spend significant time manually:

* Investigating alerts
* Correlating observability signals
* Identifying probable root causes
* Searching historical incidents
* Generating RCA reports

These activities increase incident resolution time and introduce operational inefficiencies.

This platform automates the entire investigation workflow using AI-powered agents and machine learning models to accelerate diagnosis and remediation.

---

## Key Features

### Intelligent Incident Investigation

* Automated anomaly detection
* Incident severity prediction
* Root cause classification
* RCA report generation

### Agentic Workflow Orchestration

Powered by LangGraph state-machine workflows that coordinate:

* Data analysis
* Prediction services
* Knowledge retrieval
* Report generation

### Historical Incident Intelligence

* Semantic similarity search
* Historical incident retrieval
* Knowledge reuse

### Explainable AI

* Model-driven predictions
* RCA reasoning
* Recommended remediation actions

### Enterprise Scalability

* Modular architecture
* API-first design
* Extensible workflow engine

---

## Technology Stack

### Backend

* FastAPI
* Uvicorn
* Pydantic
* SQLAlchemy

### Agentic AI

* LangGraph
* LangChain

### Machine Learning

* XGBoost
* Scikit-Learn
* Joblib
* NumPy
* Pandas

### Vector Search

* Qdrant
* Sentence Transformers
* PyTorch

### Database

* SQLite
* PostgreSQL

### Frontend

* React
* Vite
* TypeScript
* Material UI
* Recharts

---

## System Architecture

### Investigation Pipeline

1. Incident Intake
2. Anomaly Detection
3. Severity Classification
4. Root Cause Prediction
5. Historical Incident Retrieval
6. Runbook Retrieval
7. RCA Report Generation

---

## Repository Structure

```text
project-root/
│
├── backend/
│   ├── app/
│   ├── models/
│   ├── services/
│   ├── workflows/
│   ├── ml/
│   ├── database/
│   └── main.py
│
├── frontend/
│   ├── src/
│   ├── components/
│   ├── pages/
│   ├── services/
│   └── vite.config.ts
│
├── data/
│
├── models/
│
├── docs/
│
├── requirements.txt
└── README.md
```

---

# Running the Application Locally

## Prerequisites

Install:

### Backend

* Python 3.11+
* pip

### Frontend

* Node.js 20+
* pnpm 10+

### Optional

* PostgreSQL
* Qdrant

---

# Backend Setup

## Step 1: Clone Repository

```bash
git clone <repository-url>
cd AMD-Hackathon
```

## Step 2: Create Virtual Environment

Windows:

```powershell
python -m venv venv
venv\Scripts\activate
```

Linux/Mac:

```bash
python -m venv venv
source venv/bin/activate
```

## Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

## Step 4: Configure Environment Variables

Create a `.env` file:

```env
DATABASE_URL=sqlite:///incidents.db

QDRANT_HOST=localhost
QDRANT_PORT=6333

MODEL_PATH=models/

EMBEDDING_MODEL=all-MiniLM-L6-v2
```

## Step 5: Start Backend

```bash
uvicorn app.main:app --reload
```

Backend should be available at:

```text
http://localhost:8000
```

API Documentation:

```text
http://localhost:8000/docs
```

---

# Frontend Setup

## Step 1: Navigate to Frontend

```bash
cd frontend
```

## Step 2: Install Dependencies

```bash
pnpm install
```

## Step 3: Configure Environment Variables

Create `.env`:

```env
PORT=3000
BASE_PATH=/
VITE_API_URL=http://localhost:8000
```

Important:

Your Vite configuration requires:

```env
PORT
```

If this variable is missing, the application will fail with:

```text
Error: PORT environment variable is required but was not provided.
```

## Step 4: Start Frontend

Windows PowerShell:

```powershell
$env:PORT=3000
$env:BASE_PATH="/"

pnpm --filter @workspace/obs-platform dev
```

Linux/Mac:

```bash
PORT=3000 BASE_PATH=/ pnpm --filter @workspace/obs-platform dev
```

Frontend should be available at:

```text
http://localhost:3000
```

---

# Troubleshooting

## Error: PORT environment variable is required but was not provided

Cause:

Environment variables are not available in the current terminal session.

Solution:

```powershell
$env:PORT=3000
$env:BASE_PATH="/"

echo $env:PORT
```

Verify output:

```text
3000
```

Then run:

```powershell
pnpm --filter @workspace/obs-platform dev
```

---

## Verify Vite Environment

```powershell
Get-ChildItem Env:PORT
```

or

```powershell
echo $env:PORT
```

---

## Clean Dependencies

If dependency issues occur:

```bash
pnpm store prune

rm -rf node_modules
rm pnpm-lock.yaml

pnpm install
```

Windows:

```powershell
Remove-Item -Recurse -Force node_modules
Remove-Item pnpm-lock.yaml

pnpm install
```

---

# API Endpoints

## Health

```http
GET /health
```

## Severity Prediction

```http
POST /predict/severity
```

## Anomaly Detection

```http
POST /predict/anomaly
```

## Root Cause Prediction

```http
POST /predict/root-cause
```

## Full Investigation

```http
POST /investigate
```

## Incident History

```http
GET /incidents
```

## Incident Details

```http
GET /incident/{id}
```

---

# Expected Outcomes

* Reduced MTTR
* Faster Incident Diagnosis
* Automated RCA Generation
* Knowledge Reuse Through Similar Incidents
* Explainable AI-Based Recommendations
* Enterprise-Ready Scalability

---

# Team

Unified Agentic Observability & RCA Platform

Built for enterprise-grade observability, incident intelligence, and automated root cause analysis.
