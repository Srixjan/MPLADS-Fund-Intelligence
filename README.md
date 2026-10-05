# MPLADS Fund Intelligence & Completion Risk Platform

[![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=flat&logo=fastapi)](https://fastapi.tiangolo.com/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)](https://vercel.com/)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)

An end-to-end data analytics and machine learning platform that analyzes the conversion of sanctioned government development funds into completed works under the **Member of Parliament Local Area Development Scheme (MPLADS)** across 543 parliamentary constituencies in India.

---

## 📌 Executive Summary

* **National Fund Pool**: Tracked across ₹8,315+ Crore in allocations.
* **National Utilization**: Average fund conversion rate sits at **~9.0%** (Median: **~4.5%**).
* **Completion Risk Model**: A Supervised ML Classifier (`scikit-learn`) engineered to identify at-risk constituencies based on relative state benchmarks, prioritizing **Recall (~81%)** for public fund accountability.

---

## 🚀 Key Features

1. **Executive KPI Dashboard**: Macro-level visibility over national allocations, released disbursements, unreleased backlogs, and state distributions.
2. **State-Level Benchmarks**: Comparative leaderboard ranking all 36 Indian States and Union Territories with state-median benchmarking.
3. **Interactive MP Directory**: Search, filter, and sort 543 Members of Parliament by utilization rate, constituency, backlog, and continuous risk probability.
4. **Category Gap Analysis**: Deep-dive into fund allocation dynamics across *Normal/Others*, *Repair & Renovation*, and *Trust & Society*.
5. **AI Risk Simulator**: Real-time constituency risk inference tool for policymakers with automatic diagnostic factor generation.

---

## 🛠 Tech Stack

* **Backend & API**: Python, FastAPI, Uvicorn, Pydantic
* **Machine Learning & Pipeline**: Scikit-Learn (`LogisticRegression`, `ColumnTransformer`, `SimpleImputer`, `OneHotEncoder`), Joblib, Pandas, NumPy
* **Frontend**: HTML5, Vanilla JavaScript (Zero-framework, high-performance), Chart.js
* **Styling**: Minimalist Zinc Dark Design System (Linear / Vercel style)
* **Deployment**: Vercel Serverless (`@vercel/python`)

---

## 📊 Project Structure

```
├── data/
│   ├── raw/                  # Raw government data CSVs
│   └── processed/            # Pre-computed cached datasets (<10ms cold boot)
├── models/
│   └── completion_risk_v1.pkl # Serialized ML pipeline + trained model artifact
├── src/
│   ├── analysis.py           # State and category aggregation functions
│   ├── data_pipeline.py      # Regex sanitization, numeric coercion, deduplication
│   ├── feature_pipeline.py   # Scikit-learn ColumnTransformer with robust imputers
│   ├── model.py              # CompletionRiskModel wrapper class
│   ├── risk_target.py        # State-relative median target formulation
│   └── evaluation.py         # Binary classification metrics & ROC-AUC analysis
├── static/
│   ├── index.html            # Minimalist Single-Page Application
│   ├── style.css             # High-performance CSS design tokens
│   └── app.js                # Asynchronous chart rendering & simulator logic
├── app.py                    # FastAPI server & REST endpoints
├── main.py                   # Model training and EDA execution script
├── requirements.txt          # Production dependencies
└── vercel.json               # Vercel deployment configuration
```

---

## ⚙️ Local Development

### 1. Clone & Setup
```bash
git clone https://github.com/Srixjan/MPLADS-Fund-Intelligence.git
cd MPLADS-Fund-Intelligence
```

### 2. Create Virtual Environment
```bash
python -m venv venv
# On Windows:
.\venv\Scripts\activate
# On Linux/macOS:
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run Application
```bash
uvicorn app:app --host 127.0.0.1 --port 8000
```
Open [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser.

---

## 🌐 Deploy to Vercel

https://mplads-fund-intelligence.vercel.app/

---

## 📄 License
This project is open-source under the MIT License.
