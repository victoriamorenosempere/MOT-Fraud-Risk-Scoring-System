# 🛡️ MOT Fraud Risk Scoring System

Production-style hybrid fraud detection architecture for identifying suspicious MOT testing behaviour using anomaly detection, supervised learning, risk scoring, and continuous retraining pipelines.

---

# 🎯 Project Objective

This project explores how machine learning can support operational fraud detection within MOT testing environments.

The system combines:

- behavioural anomaly detection
- supervised fraud classification
- composite risk scoring
- enforcement feedback loops
- continuous model retraining

to prioritise high-risk MOT tests and testers for investigation.

Rather than relying purely on historical fraud labels, the architecture is intentionally designed to detect:

✔ known fraud patterns  
✔ hidden fraud behaviours  
✔ previously unseen fraud techniques  

---

# 🧠 Core Detection Philosophy

The system follows a layered fraud detection strategy:

## Layer 1 — Isolation Forest

Detects statistically unusual behaviour without requiring fraud labels.

Examples:
- unusually short test durations
- abnormal pass rates
- suspicious behavioural shifts
- peer-group deviations

---

## Layer 2 — XGBoost Supervised Learning

Learns patterns from confirmed fraud investigations.

Uses:
- labelled fraud cases
- engineered behavioural features
- anomaly scores from Isolation Forest
- domain-rule signals

---

## Layer 3 — Composite Risk Scoring

Combines:
- anomaly score
- supervised fraud probability
- rule-based indicators

into a single operational risk score.

---

# 🔄 Operational ML Workflow & Continuous Learning

This project was designed as a production-style fraud detection system rather than a standalone notebook model.

The workflow combines:

- cloud-native data engineering
- SQL enrichment pipelines
- anomaly detection
- supervised learning
- composite risk scoring
- operational dashboards
- enforcement feedback loops
- continuous retraining

As labelled fraud data grows over time, the system evolves from primarily anomaly-based detection toward a more supervised learning architecture, while retaining Isolation Forest as a safety-net model for novel fraud patterns.

![Operational ML Workflow](images/operational_ml_workflow.png)

---

# 🖼️ System Walkthrough

## 📊 Data Foundation & Feature Engineering

The platform joins multiple MOT-related datasets into enriched behavioural records.

Includes:
- MOT test data
- vehicle information
- tester / site information
- historical testing behaviour
- domain-rule flags
- confirmed fraud labels

![Data Foundation](images/slide2_data_foundation.png)

---

## 🌲 Isolation Forest — Unsupervised Anomaly Detection

Isolation Forest acts as the primary fraud discovery mechanism during early deployment when labelled fraud data is limited.

The model identifies:
- statistical anomalies
- peer-group deviations
- suspicious behavioural outliers

without requiring known fraud examples.

![Isolation Forest](images/slide3_isolation_forest.png)

---

## ⚡ XGBoost — Supervised Fraud Layer

Confirmed fraud cases are used to train XGBoost on known fraud behaviour patterns.

The supervised layer:
- learns fraud fingerprints
- improves calibration
- reduces false positives
- strengthens operational ranking

![XGBoost Layer](images/slide4_xgboost.png)

---

## 🔁 Continuous Learning & Model Evolution

The platform continuously improves through enforcement feedback loops.

Confirmed fraud investigations become new training labels.

Over time:
- XGBoost becomes increasingly dominant
- Isolation Forest transitions into a safety-net anomaly layer
- fraud detection capability matures continuously

![Continuous Learning](images/slide5_living_system.png)

---

# 🧮 Composite Risk Scoring

Final operational risk scores combine:

```python
risk_score = (
    0.50 * isolation_forest_score +
    0.30 * xgboost_probability +
    0.20 * domain_rule_score
)
```

This produces prioritised investigation queues for enforcement teams.

Example risk bands:

| Risk Score | Classification |
|---|---|
| 0.00 – 0.39 | Low Risk |
| 0.40 – 0.69 | Medium Risk |
| 0.70 – 1.00 | High Risk |

---

# 🧠 Why Hybrid Detection Matters

Traditional supervised fraud detection struggles because:

- fraud labels are incomplete
- absence of a label does not guarantee legitimacy
- new fraud behaviours constantly emerge

This architecture solves that problem by combining:

| Capability | Model |
|---|---|
| Detect unusual behaviour | Isolation Forest |
| Learn known fraud patterns | XGBoost |
| Catch new fraud techniques | Isolation Forest |
| Improve precision over time | XGBoost |
| Operational prioritisation | Composite scoring |

---

# ☁️ Technology Stack

| Area | Tools |
|---|---|
| Data Storage | AWS S3 |
| Query Layer | AWS Athena |
| ETL Pipelines | AWS Glue |
| Distributed Processing | PySpark |
| Feature Engineering | SQL + Pandas |
| ML Models | scikit-learn + XGBoost |
| Model Hosting | AWS SageMaker |
| Scheduling | AWS EventBridge |
| Event Triggers | AWS Lambda |
| Dashboards | Power BI |
| Explainability | SHAP |
| Notebook Development | Jupyter / Colab |

---

# 📈 Feature Engineering Examples

Key behavioural features include:

- average MOT duration
- tests per hour
- pass-rate deviation vs peers
- defect-rate anomalies
- retest frequency
- odometer inconsistencies
- temporal behaviour shifts
- peer-group normalisation
- missingness indicators
- rule-based fraud flags

---

# 🧪 Validation Strategy

The system uses:

- time-based validation splits
- labelled fraud recall analysis
- Precision@K
- operational trial comparisons
- enforcement outcome feedback

This prevents:
- data leakage
- overfitting
- unrealistic offline performance

---

# ⚖️ Governance & Explainability

The platform is designed for public-sector operational use.

Key principles:

✔ GDPR-aware design  
✔ auditability  
✔ explainable risk scoring  
✔ human-in-the-loop decisions  
✔ proportional data use  
✔ transparent investigation workflows  

No automated enforcement decisions are made by the model.

The system supports investigators rather than replacing them.

---

# 🚀 Future Enhancements

Potential future extensions include:

- CCTV-based anomaly detection
- convolutional autoencoders
- graph-based fraud networks
- LLM-generated enforcement summaries
- active learning workflows
- real-time fraud scoring
- streaming anomaly detection
- multimodal fraud intelligence

---

# 📂 Repository Contents

| File | Description |
|---|---|
| `README.md` | Project overview |
| `tech_flow_v2.html` | Interactive operational ML workflow |
| `presentation.pdf` | Full presentation slides |
| `notebooks/` | Experimental notebooks |
| `images/` | README visual assets |

---

# 👩‍💻 Author

Victoria Moreno Sempere

Data Scientist focused on:
- machine learning systems
- operational AI
- fraud detection
- health & public-sector analytics
- explainable AI
- scalable ML workflows

LinkedIn:
https://www.linkedin.com/in/victoria-moreno-sempere-01a438153/

---
