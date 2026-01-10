# Decision Support & Performance Monitoring System (NYC 311 — NYPD)

Internal-style analytics system showing how **operational data supports decisions over time** — from validation to monitoring to action.

---

## Dataset
NYC 311 — NYPD complaints  
January 2024 (real operational data, noise preserved)

---

## Repository Structure
```
decision-support-monitoring/
├── data/
│ └── raw/
│ └── 311_NYPD_2024_01_raw.csv
├── notebooks/
│ └── decision_support_monitoring.ipynb
└── validation/
```

---

## What This System Does
- Establishes **data trust** through a QA gate
- Diagnoses operational change using a **fixed baseline vs post-period**
- Defines **operational KPIs with thresholds**
- Monitors performance using **OK / WARN / ALERT** decision states
- Surfaces **drivers and decision guidance**, not just metrics

---

---

## Project Levels

### Level 0 — Decision Framing
- Framed as **operational performance monitoring**
- Focus: explain → measure → monitor → decide

### Level 1 — Data Ingestion & Validation (QA Gate)
- Schema checks
- Duplicate detection
- Timestamp parsing
- Status vs closed-date reconciliation
- Anomaly checks  
**Outcome:** QA = WARN (issues documented and accepted)

### Level 2 — Diagnostic Analysis
- Fixed time split:
  - **Baseline:** Jan 1–15
  - **Post:** Jan 16–31
- Identified mid-month volume increase
- Change shown to be **category-driven**, not system-wide
- Weekday-driven, not calendar noise

### Level 3 — KPI Framework
- Defined operational KPIs:
  - Request volume
  - Avg resolution time
  - % resolved within threshold
  - Close rate
- Baselines anchored to Level 2
- Thresholds define WARN vs ALERT

### Level 4 — Monitoring View
- Decision checkpoints with **OK / WARN / ALERT**
- KPI snapshot vs baseline
- Driver watchlist
- Minimal visuals to support decisions

### Level 5 — Decision Guidance
- Explicit rules for:
  - When to monitor
  - When to intervene
- No reactive or ad-hoc actions

### Level 6 — Boundaries & Assumptions
- Messy data accepted post-QA
- No re-cleaning
- No forecasting
- No modeling

---

## Outcome
The system surfaced **WARN-level demand pressure** driven by specific complaint categories, while operational performance remained stable — signaling monitoring, not escalation.

---

## Key Takeaway
This project demonstrates **decision governance**, not dashboarding.
