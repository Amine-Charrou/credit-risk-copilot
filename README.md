# Credit Risk Copilot

> An ML model scores the risk; a grounded LLM writes the analyst's report; a human decides.

![status](https://img.shields.io/badge/status-design%20stage-lightgrey) ![sprint](https://img.shields.io/badge/sprint-Weeks%205--6-blue) ![project](https://img.shields.io/badge/portfolio-03%2F08-0891b2)

| | |
|---|---|
| **Category** | ML + GenAI |
| **Domain** | Banking |
| **Stack** | Python · XGBoost · SHAP · LangGraph · RAG |
| **Status** | 🚧 Scoped — implementation not started |

## Overview

A hybrid system for loan-default risk. A calibrated ML model produces the score and its drivers; an LLM then drafts an analyst-ready report using only the model output, the applicant's data and retrieved credit policies, with citations. The final decision always stays with a human reviewer.

## Business problem

Risk analysts review large volumes of financial data across sources. The process is slow, manual and hard to scale, yet decisions must stay explainable and human-owned.

## What this project demonstrates

- Combining classical ML with LLMs in a regulated domain
- Calibrated, explainable risk scoring
- Grounded generation with citations and hallucination control
- Human-in-the-loop design for high-stakes decisions

## Key points

- Default-prediction model with calibration (a 30% score should mean ~30% defaults)
- SHAP drivers passed to the LLM as structured facts, not free text
- Policy retrieval (RAG) so every claim in the report cites a rule or data point
- Report sections: risk summary, key drivers, evidence, recommended checks
- Evaluation set measuring groundedness, citation accuracy and hallucination rate
- Human-in-the-loop review screen: approve, reject or send back

## Planned architecture

```text
Applicant & loan data
   ↓
Feature engineering
   ↓
Calibrated ML risk model + SHAP drivers
   ↓
Policy retrieval (RAG)
   ↓
LLM drafts grounded, cited report
   ↓
Human review: approve / reject / send back
```

## Planned deliverables

- [ ] Default-prediction model with calibration
- [ ] Explainability layer
- [ ] Prompt & retrieval design
- [ ] Analyst review interface
- [ ] Sample reports
- [ ] Groundedness evaluation framework
- [ ] Business case and architecture diagram

## Success metrics

- ROC-AUC, precision, recall, calibration curve
- Report groundedness, citation accuracy, hallucination rate
- Analyst time saved per file

## Planned structure

```text
data/  notebooks/  src/{models,rag,agent}  app/  eval/  docs/
```

## Roadmap

- [x] Scope and README
- [ ] Data collection / generation
- [ ] Core implementation
- [ ] Evaluation and business-impact estimate
- [ ] Demo, write-up and interview notes

---

Part of my **Data & AI × Business Consulting** portfolio, a 16-week sprint of 8 projects going from data and BI to ML, GenAI, agents, automation and AI strategy. See all projects on my [GitHub profile](https://github.com/Amine-Charrou).

*Amine Charrou · Final-year Data Science & AI engineering student, ENSA Agadir · [LinkedIn](https://www.linkedin.com/in/amine-charrou/)*
