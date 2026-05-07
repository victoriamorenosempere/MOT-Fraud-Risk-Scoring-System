# 📊 MOT Fraud Risk Scoring Detection System

An end-to-end machine learning fraud detection framework designed to identify anomalous MOT testing behaviour using unsupervised anomaly detection, supervised learning, domain-driven risk rules, and continuous feedback retraining.

---

# 🚗 Project Objective

This project demonstrates how data science and machine learning can support enforcement prioritisation within MOT testing operations.

The system does **not automatically determine fraud**.

Instead, it:

- detects statistically unusual behaviour
- generates composite risk scores
- ranks high-risk testers and tests
- supports enforcement investigation teams
- continuously improves using confirmed fraud outcomes

---

# 🧠 Core System Architecture

The solution combines:

| Layer | Purpose |
|---|---|
| Isolation Forest | Detect previously unseen anomalous behaviour |
| XGBoost | Learn known fraud patterns from labelled cases |
| Rule Engine | Capture explicit domain knowledge |
| Composite Risk Scoring | Prioritise enforcement actions |
| Feedback Loop | Retrain and improve over time |

---

# 🖼️ System Walkthrough

## 1️⃣ System Overview

![Overview](./slide1-overview.png)

---

## 2️⃣ Data Foundation & Feature Engineering

![Data Foundation](./slide2-data-foundation.png)

---

## 3️⃣ Unsupervised Anomaly Detection — Isolation Forest

![Isolation Forest](./slide3-isolation-forest.png)

---

## 4️⃣ Supervised Learning + Composite Risk Scoring

![XGBoost](./slide4-xgboost-risk-scoring.png)

---

## 5️⃣ Continuous Learning & Feedback Loop

![Feedback Loop](./slide5-feedback-loop.png)

---

# 🔍 Key Data Sources

The modelling pipeline integrates multiple structured datasets:

- MOT test records
- Vehicle characteristics
- Tester and garage information
- Historical MOT outcomes
- Odometer readings
- Enforcement outcomes
- Rule-based fraud indicators

---

# ⚙️ Feature Engineering Examples

Examples of behavioural features engineered:

- average MOT duration
- pass-rate deviation from peer groups
- retest velocity
- defect frequency trends
- odometer inconsistencies
- sudden behavioural shifts
- tests per hour
- missingness indicators

The system models behavioural patterns rather than isolated individual events.

---

# 🤖 Machine Learning Design

## Isolation Forest

Primary anomaly detection model used to identify unusual behavioural patterns without requiring fraud labels.

Advantages:

- works with highly imbalanced fraud problems
- scales efficiently to large datasets
- detects novel fraud behaviours
- produces continuous anomaly scores

---

## XGBoost

Secondary supervised layer trained using confirmed fraud cases.

Purpose:

- learn known fraud fingerprints
- calibrate anomaly outputs
- improve ranking precision
- provide explainable feature importance

---

# 📈 Composite Risk Scoring

Final risk score combines:

- anomaly score
- supervised fraud probability
- rule-based indicators

Example:

```python
risk_score = (
    0.50 * isolation_forest +
    0.30 * xgboost_probability +
    0.20 * domain_rules
)
```

Risk levels:

| Score | Risk Level |
|---|---|
| 0.00 – 0.39 | Low |
| 0.40 – 0.69 | Medium |
| 0.70 – 1.00 | High |

---

# 🔁 Continuous Learning System

The model improves continuously through operational feedback.

Workflow:

1. model flags suspicious cases
2. enforcement investigates
3. confirmed outcomes become new labels
4. labelled fraud library grows
5. supervised layer retrains
6. detection performance improves over time

As labelled data matures:

- XGBoost becomes primary model
- Isolation Forest becomes safety-net anomaly detector

This allows the system to detect both:

- known fraud patterns
- previously unseen behaviours

---

# 🛡️ Governance & Ethics

The project incorporates public-sector AI governance principles:

- GDPR compliance
- auditability
- explainability
- proportional data use
- human-in-the-loop decision making

The model supports investigators — it does not replace them.

---

# 🧪 Validation Strategy

Evaluation combines:

## Offline Validation

- precision@k
- recall on known fraud
- stratified cross-validation
- threshold calibration

## Real-World Pilot

Controlled regional trial:

- Region A → model-guided enforcement
- Region B → traditional enforcement baseline

Primary metric:

> confirmed fraud detected per enforcement visit

---

# 🚀 Future Enhancements

Potential future developments include:

- computer vision integration using CCTV
- LLM-assisted enforcement summarisation
- graph/network fraud analysis
- real-time streaming anomaly detection
- autoencoder-based deep anomaly detection

---

# 🛠️ Technology Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- SQL
- Matplotlib
- Jupyter Notebook

---

# 📚 Key Concepts Demonstrated

- anomaly detection
- supervised learning
- ensemble systems
- feature engineering
- fraud analytics
- explainable AI
- risk scoring
- feedback retraining
- public-sector AI governance

---

# 👩‍💻 Author

Victoria Moreno Sempere

Machine Learning • Data Science • Healthcare AI • Fraud Detection • Public Sector Analytics
