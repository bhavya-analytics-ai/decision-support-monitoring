# Decision Support & Performance Monitoring System
### NYC 311 - NYPD Complaints - Operational analytics from raw data to decision governance.

![Dataset](https://img.shields.io/badge/Data-NYC%20311%20NYPD%202024-blue?style=flat)
![Status](https://img.shields.io/badge/Status-Level%206%20Complete-brightgreen?style=flat)
![Stack](https://img.shields.io/badge/Stack-Python%20%7C%20Pandas%20%7C%20Jupyter-3776AB?style=flat&logo=python&logoColor=white)

---

## What This Is

An internal-style analytics system built on real NYC 311 - NYPD complaint data showing how operational data supports decisions over time - from validation all the way through to action.

Not a dashboard. Not a report. A **decision governance pipeline**.

---

## Dataset

NYC 311 - NYPD complaints, January 2024. Real operational data, noise preserved. No cleaning beyond what the QA gate explicitly accepts.

---

## The Outcome

The system surfaced **WARN-level demand pressure** driven by specific complaint categories, while overall operational performance stayed stable - signaling continued monitoring, not escalation.

---

## System Levels

### Level 0 - Decision Framing
Framed as operational performance monitoring from the start. The goal: explain what's happening, measure it, monitor it, and decide what to do - in that order.

### Level 1 - Data Ingestion & Validation (QA Gate)
The trust layer. Nothing runs until data quality is established.

- Schema validation
- Duplicate detection
- Timestamp parsing
- Status vs closed-date reconciliation
- Anomaly flagging

**Result:** `QA = WARN` - issues documented and accepted, not silently ignored.

### Level 2 - Diagnostic Analysis
Fixed time split to isolate real change from noise:

- **Baseline:** Jan 1-15
- **Post-period:** Jan 16-31

Mid-month volume increase identified. Change shown to be **category-driven**, not system-wide. Weekday pattern, not calendar artifact.

### Level 3 - KPI Framework
Defined operational KPIs anchored to Level 2 baselines:

- Request volume
- Average resolution time
- % resolved within threshold
- Close rate

Thresholds set explicitly to define `WARN` vs `ALERT` - not chosen after the fact.

### Level 4 - Monitoring View
Decision checkpoints, not charts for the sake of charts.

- `OK / WARN / ALERT` status per KPI
- Snapshot vs baseline comparison
- Driver watchlist
- Minimal visuals designed to support a decision, not replace one

### Level 5 - Decision Guidance
Explicit rules for when to monitor and when to intervene. No reactive or ad-hoc actions - everything is defined upfront.

### Level 6 - Boundaries & Assumptions
What the system deliberately does not do:

- No re-cleaning post-QA
- No forecasting
- No modeling

Constraints are documented, not hidden.

---

## Key Takeaway

This project demonstrates **decision governance** - how to structure operational data so it reliably supports decisions over time, not just produces outputs.

---

## Repo Structure

```
decision-support-monitoring/
├── data/
│   └── raw/
│       └── 311_NYPD_2024_01_raw.csv
├── notebooks/
│   └── decision_support_monitoring.ipynb
└── validation/
```

---

**Bhavya Pandya** · [LinkedIn](https://www.linkedin.com/in/bhavya-91p/) · M.S. Data Analytics, LIU Brooklyn
