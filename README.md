# ⚡ AI-Based Predictive Cyber Attack & Risk Scoring System

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Backend-Flask-009688?style=flat-square&logo=flask&logoColor=white)
![React](https://img.shields.io/badge/Frontend-React-61DAFB?style=flat-square&logo=react&logoColor=black)
![ML](https://img.shields.io/badge/ML-Gradient%20Boosting%20%7C%20Random%20Forest-FF6F00?style=flat-square)
![Attack Accuracy](https://img.shields.io/badge/Attack%20Prediction%20Accuracy-87.43%25-brightgreen?style=flat-square)


> A proactive, machine learning-driven framework that **forecasts cyberattacks before they happen** — integrating multi-source threat intelligence, MITRE ATT&CK mapping, and explainable AI into a real-time security operations dashboard.

---

## 📌 Overview

Most cybersecurity systems are **reactive** — they alert you after a breach has already occurred. This system flips the model entirely.

By fusing CVE disclosures, exploit availability signals, historical attack trends, and simulated dark web indicators, the system computes a **dynamic cyber risk score (0–100)** and predicts the likelihood, type, and time window of an incoming attack — empowering security teams to act before damage is done.

Built as a full-stack application with a **Flask REST API backend** and a **React interactive dashboard**, it delivers real-time risk visualisation, MITRE ATT&CK attack chain mapping, sector-wise risk comparison, and AI-driven remediation recommendations — all made interpretable through SHAP-based feature importance analysis.

---

## 🚀 Key Features

| Feature | Description |
|---|---|
| 🎯 **Predictive Risk Scoring** | 5-component weighted formula with sector-specific multipliers, outputting a 0–100 risk score |
| 🧠 **Dual ML Models** | Gradient Boosting Machines (GBM) + Random Forest classifiers for attack likelihood and type prediction |
| 🛡️ **MITRE ATT&CK Mapping** | Predicted threats are automatically mapped to relevant ATT&CK tactics and techniques |
| 💡 **Explainable AI (XAI)** | SHAP-based feature importance analysis reveals the key drivers behind every risk score |
| 🌐 **Multi-Source Intelligence** | Integrates CVE/NVD feeds, exploit availability signals, and simulated dark web indicators |
| 📊 **React Dashboard** | Real-time visualisation, attack chain mapping, sector comparison, and AI security recommendations |
| ⏱️ **Time Window Forecasting** | Predicts the probable time window of attack, not just whether one will occur |

---

## 📈 Performance Results

| Metric | Score |
|---|---|
| Attack Likelihood Prediction Accuracy | **87.43%** |
| Attack Type Classification Accuracy | **78.12%** |
| Risk Score Range | **0 – 100** (dynamic, continuously updated) |

> Results obtained on simulated threat intelligence datasets with realistic CVE, exploit, and historical attack data.

---

## 🔢 Risk Scoring Formula

The 5-component dynamic risk score is computed as:

```
Risk Score = Σ [ w₁·P(attack) + w₂·VulnerabilityExposure + w₃·ExploitSignal
                + w₄·DarkWebIntel + w₅·HistoricalAttackDensity ]
             × SectorMultiplier
```

Each component is independently weighted and can be tuned per sector (Finance, Healthcare, Government, etc.), producing a calibrated score from 0 (no risk) to 100 (critical threat imminent).

---

## 🛡️ MITRE ATT&CK Coverage

The system maps predicted threats across the MITRE ATT&CK framework, including:

- `TA0001` — Initial Access
- `TA0002` — Execution
- `TA0003` — Persistence
- `TA0006` — Credential Access
- `TA0007` — Discovery
- `TA0010` — Exfiltration
- `TA0040` — Impact

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    React Dashboard                       │
│   Risk Score · Attack Chain · Sector Comparison · XAI   │
└───────────────────────┬─────────────────────────────────┘
                        │ REST API
┌───────────────────────▼─────────────────────────────────┐
│                   Flask Backend                          │
│   /predict  /risk-score  /mitre-map  /recommendations   │
└──────┬──────────────────┬───────────────────────────────┘
       │                  │
┌──────▼──────┐   ┌───────▼────────┐
│  ML Models  │   │ Threat Intel   │
│  GBM + RF   │   │ CVE · Exploit  │
│  SHAP (XAI) │   │ Dark Web (sim) │
└─────────────┘   └────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technologies |
|---|---|
| **Machine Learning** | scikit-learn, XGBoost, SHAP, NumPy, Pandas |
| **Backend** | Python 3.10+, Flask, Flask-CORS, REST API |
| **Frontend** | React, Recharts, Axios, Tailwind CSS |
| **Data Sources** | NVD/CVE API, simulated exploit feeds, historical attack datasets |
| **Explainability** | SHAP (SHapley Additive exPlanations) |

---

## 📦 Source Code

> **The full project is distributed as a ZIP archive.**

Download `cyber-risk-system.zip` from the [Releases](../../releases) page or the repository root, then follow the setup instructions below.

```
cyber-risk-system/
├── backend/
│   ├── app.py                  # Flask REST API
│   ├── models/
│   │   ├── gbm_model.py        # Gradient Boosting classifier
│   │   └── rf_model.py         # Random Forest classifier
│   ├── risk_scoring/
│   │   └── scorer.py           # 5-component risk formula
│   ├── threat_intel/
│   │   ├── cve_feed.py         # CVE/NVD integration
│   │   └── dark_web_sim.py     # Simulated dark web signals
│   ├── mitre/
│   │   └── attack_mapper.py    # MITRE ATT&CK mapping
│   ├── explainability/
│   │   └── shap_explainer.py   # XAI feature importance
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── components/         # Dashboard UI components
│   │   ├── pages/              # Risk dashboard, reports
│   │   └── App.jsx
│   └── package.json
├── data/
│   ├── historical_attacks.csv  # Training dataset
│   └── cve_sample.json
└── README.md
```

---

## ⚡ Quick Start

### Prerequisites

- Python 3.10+
- Node.js 18+
- pip & npm

### 1. Extract the archive

```bash
unzip cyber-risk-system.zip
cd cyber-risk-system
```

### 2. Set up the backend

```bash
cd backend
pip install -r requirements.txt
python app.py
# API running at http://localhost:5000
```

### 3. Set up the frontend

```bash
# Open a new terminal
cd frontend
npm install
npm start
# Dashboard running at http://localhost:3000
```

### 4. API Endpoints

| Endpoint | Method | Description |
|---|---|---|
| `/predict` | POST | Predict attack likelihood & type |
| `/risk-score` | POST | Compute dynamic risk score (0–100) |
| `/mitre-map` | GET | Get MITRE ATT&CK mapping for predicted threats |
| `/recommendations` | POST | AI-generated security recommendations |
| `/sector-compare` | GET | Sector-wise risk comparison |

---

## 📊 Dashboard Preview

The React dashboard provides:

- **Real-time risk gauge** — live 0–100 score with colour-coded severity
- **Attack probability timeline** — 7/14/30-day forecasting windows
- **MITRE ATT&CK chain visualisation** — predicted attack path mapping
- **Sector-wise risk heatmap** — comparative risk across industries
- **XAI insights panel** — top risk drivers with SHAP waterfall charts
- **AI recommendations** — prioritised, actionable security guidance

---

## 🔬 Methodology

1. **Data Collection** — CVE disclosures, exploit availability (EPSS scores), historical breach data, and simulated dark web indicators are aggregated into a unified threat intelligence dataset.
2. **Feature Engineering** — 25+ features including CVSS scores, patch lag, asset exposure, exploit maturity, and sector-specific risk multipliers.
3. **Model Training** — GBM and Random Forest models are trained for binary attack likelihood prediction and multi-class attack type classification.
4. **Risk Computation** — Predicted probabilities feed into the 5-component weighted scoring formula to produce the final risk score.
5. **MITRE Mapping** — Predicted attack types are mapped to corresponding MITRE ATT&CK tactics and techniques.
6. **Explainability** — SHAP values decompose each risk score into per-feature contributions for interpretable output.

---

## 🔮 Future Work

- [ ] Integration with live SIEM/SOAR platforms (Splunk, Elastic SIEM)
- [ ] Real dark web intelligence feeds via API partnerships
- [ ] Graph neural networks for attack chain prediction
- [ ] Federated learning for cross-organisation threat sharing
- [ ] Automated incident response playbook generation

---

## 📄 Keywords

`Cybersecurity` · `Predictive Analytics` · `Risk Scoring` · `Machine Learning` · `Threat Intelligence` · `MITRE ATT&CK` · `Explainable AI` · `Gradient Boosting` · `Random Forest` · `CVE Analysis` · `Dark Web Intelligence`

---

