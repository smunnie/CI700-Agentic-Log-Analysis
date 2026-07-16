## Agentic AI Workflow for Cybersecurity Log Analysis

CI700 MSc Final Project (University of Brighton). A lightweight, evidence-gated
agentic AI workflow that investigates security alerts by correlating log
events, retrieving grounded cybersecurity knowledge via RAG, and producing
explainable incident reports — as an aid to human SOC analysts, not a
replacement for them.

## Repo layout

```
src/
  ingestion/    # Log parsing + normalisation for AIT-LDS (auth + Apache/Nginx)
  detection/    # Sigma rule engine + Z-score anomaly detection (hybrid engine)
  agents/       # Orchestrator, Investigation & Reporting, Threat Intelligence
  rag/          # Vector store build + retrieval (MITRE ATT&CK, Sigma docs)
  db/           # PostgreSQL models / connection / query helpers
data/
  raw/          # Untouched AIT-LDS downloads (gitignored — see below)
  processed/    # Normalised logs ready for the DB (gitignored)
docs/           # Architecture diagram, project diary, dissertation drafts
notebooks/      # Exploratory analysis, manual log inspection
tests/          # Unit tests for ingestion, detection, and agent tools
```

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env             # then fill in DB creds / API keys
```

## Dataset

This project uses the **AIT Log Data Set (AIT-LDS)** from the Austrian
Institute of Technology — synthetic multi-host enterprise logs (auth,
Apache/Nginx, DNS, VPN, etc.) with labelled attack ground truth.


