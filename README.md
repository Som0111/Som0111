<h1 align="center">Hi, I'm Soumya Padhi 👋</h1>

<p align="center">
  <b>B.Tech Electrical Engineering · NIT Rourkela · Graduating 2027</b><br/>
  Building ML systems, data pipelines, and AI-powered engineering tools
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/soumya-swarup-padhi-91ab90414/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="https://github.com/Som0111">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" />
  </a>
</p>

---

I enjoy working at the intersection of **Machine Learning, Data Engineering, and real-world engineering problems** — with a focus on building systems that are measurable, deployable, and useful beyond a notebook.

---

## 🚀 Featured Projects

### 🧠 [CI-Brain](https://github.com/Som0111/ci-brain) · *AI-Powered CI Intelligence Platform*

> FastAPI · PostgreSQL · SQLAlchemy · Alembic · React + TypeScript · Docker · GitHub Actions · Google Gemini · Render

Analyzes CI pipelines to make software testing faster and more intelligent — covering the three core problems large engineering orgs actually solve: which tests to run, which tests are flaky, and what caused a wall of failures.

- **Test Impact Analysis** — builds a real file-to-test dependency graph from coverage data; falls back to full suite when it can't answer confidently rather than guessing
- **Statistical flaky-test detection** — flags tests that produce both pass and fail on identical code, not just when fail rate crosses a threshold; gives a confidence level and quarantine recommendation
- **LLM failure clustering** — groups failures by likely root cause and returns a plain-English hypothesis per cluster, grounded in actual evidence

**Benchmarked against `toolz` (real open-source Python library):**

| Metric | Result |
|---|---|
| Tests eliminated | 57.5–98.9% fewer tests executed |
| Wall-clock time saved | 9.5–58.2% reduction |
| Flaky tests caught | 4 / 4 with **0 false positives** |

**Live API:** [ci-brain.onrender.com/health](https://ci-brain.onrender.com/health) · 98%+ branch coverage across 110 tests

---

### ⚡ [GridPulse](https://github.com/Som0111/gridpulse) · *India Electricity Demand Analytics*

> Python · PostgreSQL (Neon) · SARIMAX · Power BI · GitHub Actions

End-to-end ELT pipeline analyzing India's electricity demand across **65,178+ state-level daily records (2020–2025)**.

- PostgreSQL star schema on Neon cloud
- 12 SQL analyses with CTEs and window functions covering regional patterns, seasonal trends, and anomalies
- SARIMAX forecast model — **2.49% MAPE**
- Power BI dashboard: National Pulse + State Explorer pages
- Daily automated refresh via GitHub Actions with data-quality validation

---

### 📈 [ChurnGuard](https://github.com/Som0111/churn-guard) · *Cost-Sensitive Churn Prediction*

> scikit-learn · FastAPI · Docker · GitHub Actions · Render

Instead of optimizing for accuracy, ChurnGuard optimizes the decision threshold around the **actual economics of a retention campaign**.

- Cost-sensitive threshold tuning on campaign profit, not the default 0.5 cutoff
- Model comparison, calibration, and end-to-end sklearn pipeline
- Deployed as a FastAPI microservice with Docker + CI/CD

**Held-out result:**

| Approach | Campaign Profit |
|---|---|
| Blanket campaign | −$14,350 |
| ChurnGuard-targeted | **+$16,250** |
| **Swing** | **+$30,600** |

---

### 🕵️ [FraudLens](https://github.com/Som0111/fraud-detection-research) · *Credit Card Fraud Detection*

> XGBoost · Neural Networks · Jupyter

End-to-end fraud detection with XGBoost and neural networks, including temporal drift analysis and business cost optimization — not just AUC.

---

### 🔌 [Electrical Load Fingerprinting](https://github.com/Som0111/electrical-load-fingerprinting) · *NILM*

> Signal Processing · scikit-learn · REFIT Dataset

Identifies household appliances from aggregate power consumption data — combining Electrical Engineering, signal processing, and ML.

- Event detection + electrical feature extraction + appliance classification
- Logistic Regression, Decision Tree, Random Forest comparison
- **Random Forest Macro F1: 0.56** on REFIT household electricity data

---

### 🎮 [VisionPlay AI](https://github.com/Som0111/VisionPlay-AI) · *Computer Vision Platform*

> Python · OpenCV · MediaPipe · ONNX Runtime · PySide6

Modular, plugin-based platform for gesture-controlled applications and computer vision demos. Shared camera pipeline, CPU-efficient inference, ONNX Runtime integration.

---

## 🛠️ Tech Stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-003B57?style=flat&logo=postgresql&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)

**ML / AI**

![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-189AB4?style=flat&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat&logo=onnx&logoColor=white)

**Data & Backend**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)

**Visualization**

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)

---

## 📈 GitHub Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Som0111&show_icons=true&theme=github_dark&hide_border=true&count_private=true" height="160"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Som0111&layout=compact&theme=github_dark&hide_border=true" height="160"/>
</p>

---

## 🎓 Education

**National Institute of Technology Rourkela**  
B.Tech — Electrical Engineering · Graduating 2027

---

<p align="center">
  <i>Open to SDE and ML Engineering internships · Placement 2027</i><br/>
  <a href="https://www.linkedin.com/in/soumya-swarup-padhi-91ab90414/">LinkedIn</a> · <a href="https://github.com/Som0111">GitHub</a>
</p>
