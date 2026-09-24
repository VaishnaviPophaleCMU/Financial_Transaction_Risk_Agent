# Financial Transaction Risk Agent

An agentic financial transaction analysis system designed to identify unusual transaction behavior, investigate suspicious activity, and provide interpretable risk assessments.

The system combines natural-language workflow planning, rule-based detection, machine-learning anomaly detection, transaction graph analysis, and explainable AI into a unified investigation pipeline.

---

## Overview

Financial transaction monitoring often relies on predefined rules and thresholds. While these approaches are useful for identifying known patterns, complex transaction behavior may require combining multiple analytical techniques.

This project approaches transaction monitoring as an **agentic investigation workflow**.

A natural-language investigation request is converted into a structured analysis plan. The agent then selects the relevant analytical tools, executes them, combines the resulting signals, performs risk analysis, and generates an explanation for the investigator.

### Core Capabilities

- Natural-language transaction investigations
- Dynamic workflow planning with LangGraph
- Rule-based suspicious activity detection
- Isolation Forest and Local Outlier Factor anomaly detection
- Transaction-network analysis with NetworkX
- SHAP-based feature explanations
- Risk assessment and investigation recommendations
- Interactive Streamlit dashboard
- FastAPI backend
- Automated evaluation and testing

---

## Investigation Workflow

The system follows an adaptive investigation workflow:

```text
                    Investigation Request
                            │
                            ▼
                    ┌───────────────┐
                    │ Intent Parser │
                    └───────┬───────┘
                            │
                            ▼
                    ┌───────────────┐
                    │ Workflow      │
                    │ Planner       │
                    └───────┬───────┘
                            │
                            ▼
                    ┌───────────────┐
                    │ Analysis      │
                    │ Router        │
                    └───────┬───────┘
                            │
              ┌─────────────┼──────────────┐
              ▼             ▼              ▼
        Rule Analysis   ML Anomaly     Graph Analysis
              │             │              │
              └─────────────┼──────────────┘
                            ▼
                    ┌───────────────┐
                    │ Risk Analysis │
                    └───────┬───────┘
                            │
                            ▼
                    ┌───────────────┐
                    │ Explainability│
                    │     (SHAP)    │
                    └───────┬───────┘
                            │
                            ▼
                    Investigation Result