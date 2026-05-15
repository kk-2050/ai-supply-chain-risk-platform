# AI Supply Chain Risk Intelligence Platform

> AI-assisted Enterprise Decision Platform for Supply Chain Risk Monitoring and Alerting

---

## Project Overview

This project is a portfolio demonstration of an end-to-end AI automation pipeline for supply chain risk intelligence.

The platform automatically collects supply chain news, analyzes risk using AI, scores suppliers, saves data, and sends alerts — without manual intervention.

> **Note:** All company names in this project are entirely fictional and created for portfolio demonstration purposes only. Any resemblance to real companies is purely coincidental.

---

## Live Demo

- **Dashboard:** https://kk-2050.github.io/ai-supply-chain-risk-platform/dashboard/
- **Workflow:** n8n Cloud (Published / Active)

---

## Architecture

```
[Google News RSS]
       ↓
[n8n: Scheduled Collection — every 6 hours]
       ↓
[n8n: Text Cleaning / Supplier Matching]
       ↓
[OpenAI GPT-4o-mini: Risk Extraction + Scoring]
       ↓
[n8n: Parse AI Response + Calculate Business Risk Score]
       ↓
[Google Sheets: Save Risk Events]
       ↓
[n8n: Check Risk Threshold (score >= 3.5)]
       ↓
[Gmail: Automated Alert Email]
```

---

## Business Risk Score Formula

```
Overall Risk Score =
  (Severity Score           x 0.40)
+ (Operational Impact Score x 0.35)
+ (Urgency Score            x 0.25)
```

**Design Rationale:**

- **Severity (0.40):** The magnitude of a risk event is the primary driver of business response priority.
- **Operational Impact (0.35):** In manufacturing and supply chain operations, business impact often becomes the key driver of operational decision-making. Even a single supplier issue can affect an entire production line.
- **Urgency (0.25):** Time sensitivity alone does not justify resource allocation. A high-urgency but low-severity event should not displace a critical but slower-moving risk.

**Phase 2 (planned):**

```
Overall Risk Score =
  (Severity Score           x 0.35)
+ (Operational Impact Score x 0.30)
+ (Urgency Score            x 0.20)
+ (Likelihood Score         x 0.15)
```

---

## Features

- Automated RSS news collection every 6 hours
- AI-powered risk extraction and multi-dimensional scoring
- Business Risk Score calculation (Severity / Operational Impact / Urgency)
- Automated alert email for high-risk events (score >= 3.5)
- Google Sheets data logging for historical analysis
- SQL Server database design for enterprise-grade persistence
- HTML dashboard for portfolio demonstration

---

## Dashboard

The HTML dashboard published on GitHub Pages serves as a static portfolio demo with representative sample data.

The live operational version connects directly to Google Sheets via n8n automation, displaying real-time risk events as they are detected and scored by the AI pipeline.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Automation | n8n Cloud |
| AI Analysis | OpenAI GPT-4o-mini |
| Data Storage | Google Sheets / SQL Server Express |
| Database Design | T-SQL (SQL Server Management Studio 22) |
| Dashboard | HTML / CSS / JavaScript |
| Hosting | GitHub Pages |
| Alert | Gmail (via n8n) |

---

## Database Schema

Four tables designed for enterprise-grade supply chain risk tracking:

| Table | Description |
|---|---|
| supplier_master | Supplier registry with criticality level |
| risk_events | Risk event log with source and category |
| risk_scores | AI-generated scores per event |
| alert_logs | Alert delivery history |

See sample-data/supply_chain_ddl_v2.sql for full schema.

---

## Project Structure

```
supply-chain-risk/
├── README.md
├── dashboard/
│   └── index.html
├── workflow-json/
│   └── AI Supply Chain Risk Intelligence Platform v1.json
├── sample-data/
│   └── supply_chain_ddl_v2.sql
├── screenshots/
│   ├── dashboard.png
│   ├── gmail_alert.png
│   ├── google_sheets_data.png
│   ├── screenshot n8n AI Supply Chain Risk Intelligence Platform v1.png
│   └── ssms_supplier_master.png
├── architecture/
└── docs/
```

---

## Current Version (v1)

- Single RSS source (Google News — supply chain keywords)
- One matched risk event per execution
- AI risk scoring via OpenAI GPT-4o-mini
- Google Sheets logging
- Gmail alert for high-risk events

## Planned Enhancements (v2)

- Batch processing with $input.all()
- Multiple data sources (NewsAPI, tariff feeds, ERP alerts)
- SQL Server direct integration
- Power BI live dashboard
- Webhook / event-driven architecture

---

## Background

This project was built to demonstrate practical AI automation skills applied to real-world supply chain operations.

The author brings 20+ years of experience in ERP, EDI, manufacturing operations, logistics, and electronic components manufacturing — combined with hands-on skills in n8n, OpenAI API, SQL, and automation architecture.

---

## Author

**Kaori Kashiwagi**
AI Automation Architect (Portfolio Project)
May 2026

---

DISCLAIMER: All company names, supplier names, and organizations in this project are entirely fictional and created for portfolio demonstration purposes only. Any resemblance to real companies is purely coincidental.
