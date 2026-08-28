<h1 align="center">
Hi, I'm Soumya Padhi 👋
</h1>

<p align="center">
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=17&pause=800&color=A5D6FF&center=true&vCenter=true&width=760&height=34&lines=%E2%9A%A1+B.Tech+in+Electrical+Engineering" alt="B.Tech in Electrical Engineering" />
</p>
<p align="center">
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=17&pause=800&color=A5D6FF&center=true&vCenter=true&width=760&height=34&lines=National+Institute+of+Technology+Rourkela+%C2%B7+Graduating+2028" alt="National Institute of Technology Rourkela" />
</p>
<p align="center">
<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=17&pause=800&color=7EE787&center=true&vCenter=true&width=760&height=34&lines=%F0%9F%A4%96+Machine+Learning+%7C+Data+Engineering+%7C+AI" alt="Machine Learning Data Engineering AI" />
</p>
<p align="center">
<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=17&pause=800&color=F2CC60&center=true&vCenter=true&width=760&height=34&lines=%F0%9F%9B%A0%EF%B8%8F+Building+systems+that+go+beyond+the+notebook" alt="Building systems that go beyond the notebook" />
</p>
<p align="center">
<a href="https://www.linkedin.com/in/soumya-swarup-padhi-91ab90414/" target="_blank">
<img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
</a> <a href="https://github.com/Som0111">
<img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
</a>
</p>

---

I enjoy working at the intersection of **Machine Learning**, **Data
Engineering**, and **real-world engineering problems** — with a focus
on building systems that are **measurable, deployable, and useful beyond
a notebook**.

## 🧠 <b>Flagship Projects</b>

### 🛰️ **[Contrail](https://github.com/Som0111/contrail)** · <i>Event-Time Stream Processor for Flight Telemetry</i>

> `Python` · `FastAPI` · `Kafka (Redpanda)` · `TimescaleDB` · `Redis` ·
> `Docker` · `Prometheus/Grafana`

<p align="center">
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=16&pause=1000&color=7EE787&center=true&vCenter=true&width=700&height=30&lines=What+happens+when+data+arrives+out+of+order%3F;What+happens+when+traffic+spikes+6x%3F;What+happens+when+a+worker+crashes+mid-stream%3F" alt="Contrail questions" />
</p>

Contrail ingests live and synthetic ADS-B flight telemetry through Kafka
and processes it with correct event-time semantics — the three questions
that separate a real streaming system from a Kafka-consumer tutorial:
**how do you handle data that arrives late, how do you scale under
burst load, and how do you guarantee correctness after a crash.**

| Event misattribution (naive → watermark) | Peak lag under 6x burst | Replay determinism |
| ----------------------------------------- | ------------------------ | -------------------- |
| **13.66% → 0.00%** | **4.2x lower** (adaptive + shedding vs. static) | **Byte-identical** across repeated runs and mid-stream crashes |

**Every claim benchmarked against a naive baseline**, on real ADS-B data
and controlled synthetic chaos (out-of-order, duplicate, and late
events) — full reproduce commands and exact configs in `BENCHMARKS.md`.

<p align="center">
<a href="https://github.com/Som0111/contrail"><img src="https://img.shields.io/badge/View_Repository-181717?style=for-the-badge&logo=github&logoColor=white" alt="View Contrail"/></a>
</p>

<details>
<summary><b>🔍 How Contrail works</b></summary>

```
Live OpenSky feed / synthetic generator
   ↓
Kafka (Redpanda) — partitioned, idempotent producers
   ↓
Watermark-based event-time windowing (handles out-of-order + late data)
   ↓
Lag-trend adaptive controller (scales workers, sheds load under sustained overload)
   ↓
TimescaleDB (durable) + Redis (cache/pub-sub)
   ↓
FastAPI — REST + WebSocket, JWT-authenticated
   ↓
Prometheus/Grafana observability
```

</details>

<details>
<summary><b>🧪 Engineering highlights</b></summary>

- Watermark-based windowing with a configurable allowed-lateness bound
  and a late-event side output, benchmarked against a naive
  processing-time baseline on 88,199 events.
- Lag-trend adaptive control loop that scales and sheds Kafka consumer
  workers based on the *rate of change* in lag, not a static threshold —
  cuts peak lag 4.2x and p99 latency ~6x vs. a static pool during a 6x
  burst.
- Deterministic replay harness proving byte-identical output across
  repeated runs and mid-stream consumer failures, backed by idempotent
  database writes.
- FastAPI service with JWT auth, rate limiting, REST + WebSocket APIs,
  live OpenSky ingestion, full Prometheus/Grafana observability, and a
  chaos-tested crash-recovery path — all runnable with one
  `docker compose up`.
- Documented, honest limitations (not overclaimed): live multi-partition
  watermarking, shedding-under-sustained-overload — see
  `DESIGN_DECISIONS.md`.

</details>

---

### 🧠 **[CI-Brain](https://github.com/Som0111/ci-brain)** · <i>Continuous Integration Intelligence Platform</i>

> `FastAPI` · `PostgreSQL` · `SQLAlchemy` · `Alembic` ·
> `React + TypeScript` · `Docker` · `GitHub Actions` · `Google Gemini` ·
> `Render`

<p align="center">
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=16&pause=1000&color=7EE787&center=true&vCenter=true&width=700&height=30&lines=Which+tests+should+run%3F;Which+tests+are+flaky%3F;What+actually+caused+the+failure%3F" alt="CI-Brain questions" />
</p>

CI-Brain analyzes CI pipelines to make software testing faster and more
intelligent — covering the three core problems large engineering orgs
actually solve: **which tests to run, which tests are flaky, and what
caused a wall of failures.**

| Tests eliminated | Wall-clock time saved | Flaky tests caught |
| ------------------ | ----------------------- | ------------------------------- |
| **57.5–98.9%** | **9.5–58.2%** | **4 / 4 · 0 false positives** |

**Benchmarked against `toolz`**, a real open-source Python library,
across a range of simulated single-file and multi-file diffs — ranges
reflect diff size, not a single run.

<p align="center">
<a href="https://github.com/Som0111/ci-brain"><img src="https://img.shields.io/badge/View_Repository-181717?style=for-the-badge&logo=github&logoColor=white" alt="View CI-Brain"/></a>
<a href="https://ci-brain.onrender.com/health"><img src="https://img.shields.io/badge/Live_API-46E3B7?style=for-the-badge&logo=fastapi&logoColor=white" alt="Live API"/></a>
</p>

<details>
<summary><b>🔍 How CI-Brain works</b></summary>

```
CI data
   ↓
Coverage / file-to-test dependency graph
   ↓
Test Impact Analysis
   ↓
Statistical Flaky-Test Detection
   ↓
Failure Clustering
   ↓
Evidence-grounded LLM Explanation
   ↓
Developer Dashboard
```

</details>

<details>
<summary><b>🧪 Engineering highlights</b></summary>

- Test Impact Analysis falls back to the full suite when confidence is
  insufficient.
- Flaky-test detection uses behavioral evidence rather than a simple
  failure-rate threshold.
- Failure clustering groups failures by likely root cause before
  asking the LLM for a summary.
- **110 tests** with **98%+ branch coverage**.
- FastAPI backend, PostgreSQL database, React + TypeScript dashboard,
  Dockerized deployment and GitHub Actions integration.

</details>

---

## 🚀 <b>Featured Projects</b>

<p align="center">
<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=15&pause=1200&color=79C0FF&center=true&vCenter=true&width=650&height=28&lines=Build+%E2%86%92+Measure+%E2%86%92+Deploy+%E2%86%92+Improve" alt="Build Measure Deploy Improve" />
</p>

<table>
<tr>
<td width="50%" valign="top">

### ⚡ **[GridPulse](https://github.com/Som0111/gridpulse)**

**India Electricity Demand Analytics**

Python · PostgreSQL · SARIMAX · Power BI · GitHub Actions

End-to-end ELT pipeline analyzing India's electricity demand across
**65,178+ state-level daily records (2020–2025)**.

- PostgreSQL star schema on Neon
- 12 SQL analyses using CTEs and window functions
- SARIMAX forecast — **2.49% MAPE**
- Power BI dashboard
- Daily automated refresh with data-quality validation

</td>
<td width="50%" valign="top">

### 📈 **[ChurnGuard](https://github.com/Som0111/churn-guard)**

**Cost-Sensitive Churn Prediction**

scikit-learn · FastAPI · Docker · GitHub Actions · Render

Optimizes the decision threshold around the **actual economics of a
retention campaign**, rather than accuracy alone.

| Strategy | Profit |
| ------------------ | --------------- |
| Blanket campaign | −$14,350 |
| ChurnGuard | **+$16,250** |
| **Swing** | **+$30,600** |

*Profit figures use illustrative campaign-cost assumptions ($50 offer
cost / $500 customer LTV / 30% save rate) on the IBM Telco dataset —
the framework is the point, not these exact dollar values.*

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🕵️ **[FraudLens](https://github.com/Som0111/fraud-detection-research)**

**Credit Card Fraud Detection**

XGBoost · Neural Networks · Jupyter

End-to-end fraud detection including **temporal drift analysis**, model
robustness and business cost optimization — not just AUC.

</td>
<td width="50%" valign="top">

### 🔌 **[Electrical Load Fingerprinting](https://github.com/Som0111/electrical-load-fingerprinting)**

**NILM — Non-Intrusive Load Monitoring**

Signal Processing · scikit-learn · REFIT

Identifies household appliances from aggregate power consumption by
combining **Electrical Engineering, signal processing, and ML**.

**Random Forest Macro F1: 0.56**

</td>
</tr>
</table>

---

## ⚡ <b>Electrical Engineering Projects</b>

Core-EE work applying signal processing and circuit analysis to problems
that actually show up on a plant floor — condition monitoring and power
quality, not just simulation for its own sake.

<table>
<tr>
<td width="50%" valign="top">

### 🔧 **[Motor Condition Monitoring](https://github.com/Som0111/motor-condition-monitoring)**

**Bearing Fault Diagnosis via Envelope Spectrum Analysis**

Signal Processing · Hilbert Transform · scikit-learn · CWRU Dataset

Diagnoses rolling-element bearing faults from raw vibration by
demodulating the structural resonance — physics first, ML as a
cross-check, not the method.

- Rule-based diagnosis (bandpass → Hilbert envelope → defect-frequency
  matching): **83.2% accuracy**, zero false alarms on healthy bearings
- RandomForest cross-check: **100% test accuracy**, confirming the
  physics-derived features (envelope amplitude at BPFO/BPFI/BSF) carry
  the signal
- Kurtogram-based automatic band selection (Antoni, 2006), including an
  honest negative result: it doesn't fix the hardest fault class, and
  that failure is itself diagnostic
- Self-checked against a synthetic signal with a known answer before
  trusting it on real bearing data

</td>
<td width="50%" valign="top">

### 🔌 **[Power Quality & Reactive Compensation](https://github.com/Som0111/power-quality-reactive-compensation)**

**Plant Feeder Harmonic Filter Design (IEEE 519-referenced)**

Python · Circuit Simulation · Power Systems

Simulates a 415V industrial feeder with a VFD load to show how a naive
capacitor bank for power-factor correction can make harmonic distortion
*worse* — and why a detuned filter is the standard fix.

- Harmonic generator verified against theory before any simulation runs
- Naive capacitor bank: PF improves, but THD rises to **9.99%** (from
  8.36% baseline) due to resonance amplification, even with the
  resonant order far from the classic 5th/7th harmonic
- Detuned filter (tuned below the 5th): lower total kVA and lower
  absolute harmonic current on every line — the real fix, even though
  THD% alone doesn't show it clearly
- Pure Python simulation, no MATLAB/Simulink, referenced against IEEE
  519 limits

</td>
</tr>
</table>

---

## 🔨 <b>Currently Building</b>

### 🎮 **[VisionPlay AI](https://github.com/Som0111/VisionPlay-AI)**

<p>
<img src="https://img.shields.io/badge/STATUS-ACTIVE-2EA043?style=for-the-badge" alt="Active"/>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white" alt="OpenCV"/>
<img src="https://img.shields.io/badge/MediaPipe-00897B?style=flat&logo=google&logoColor=white" alt="MediaPipe"/>
<img src="https://img.shields.io/badge/ONNX_Runtime-005CED?style=flat&logo=onnx&logoColor=white" alt="ONNX Runtime"/>
</p>

A modular, plugin-based computer-vision platform for gesture-controlled
applications and AI demos.

Current focus:

- Plugin-based application architecture
- Shared camera pipeline
- Computer-vision inference
- CPU-efficient processing
- ONNX Runtime integration

---

## 🧩 <b>What I Work With</b>

**Core**

`Python` · `C++` · `SQL`

**Backend / Systems**

`FastAPI` · `Kafka (Redpanda)` · `PostgreSQL` · `TimescaleDB` · `Redis` ·
`Docker` · `GitHub Actions` · `Prometheus/Grafana`

**ML / AI**

`scikit-learn` · `TensorFlow` · `XGBoost` · `OpenCV` · `ONNX`

**Data / Signal Processing**

`Pandas` · `NumPy` · `SciPy` · `Hilbert Transform` · `Power BI`

**Frontend / Visualization**

`React` · `TypeScript` · `Power BI`

---

## 📊 <b>GitHub Activity</b>

<p align="center">
<img src="https://github-readme-stats.vercel.app/api?username=Som0111&show_icons=true&theme=github_dark&hide_border=true&count_private=true" height="165" alt="GitHub stats"/>
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Som0111&layout=compact&theme=github_dark&hide_border=true" height="165" alt="Top languages"/>
</p>
<p align="center">
<img src="https://github-readme-activity-graph.vercel.app/graph?username=Som0111&theme=github-compact&hide_border=true&area=true" alt="GitHub activity graph"/>
</p>

---

## 🎓 <b>Education</b>

**National Institute of Technology Rourkela**
B.Tech — Electrical Engineering · Graduating 2028

---

## 📌 <b>Current Focus</b>

- Backend & Distributed Systems Engineering
- Machine Learning Engineering
- Data Engineering
- Computer Vision
- AI-powered developer tools

---

<p align="center">
<i>Open to SDE, Machine Learning and Data Engineering
internships · Placement 2028</i><br/><br/>
<a href="https://www.linkedin.com/in/soumya-swarup-padhi-91ab90414/">LinkedIn</a>
· <a href="https://github.com/Som0111">GitHub</a>
</p>
