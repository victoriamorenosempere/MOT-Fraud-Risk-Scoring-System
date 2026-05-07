# 🚗 MOT Fraud Risk Scoring System

An end-to-end machine learning fraud detection architecture designed to identify suspicious MOT tests and testers using anomaly detection, supervised learning, behavioural analytics, and continuous feedback retraining.

This project simulates how a national-scale MOT fraud detection platform could operate using real-world data science, MLOps, cloud engineering, explainable AI, and operational fraud analytics principles.

---

# 📌 Project Objectives

The system was designed to:

- Detect potentially fraudulent MOT tests
- Rank suspicious testers and garages by risk
- Reduce enforcement investigation time
- Combine unsupervised + supervised machine learning
- Continuously improve as new fraud cases are confirmed
- Demonstrate real-world production-scale ML architecture thinking
- Simulate how a government fraud platform could evolve operationally over time

---

# 🏗️ End-to-End Technical Workflow

The system follows a complete fraud detection lifecycle:

1. Raw MOT data enters the platform
2. SQL + PySpark enrichment generates behavioural features
3. Isolation Forest identifies anomalous tests
4. XGBoost learns patterns from confirmed fraud
5. Composite risk scoring ranks suspicious cases
6. Enforcement outcomes return into the fraud library
7. Models retrain monthly as labelled fraud data grows

This creates a continuously improving fraud detection ecosystem.

---

# 🔄 Technical Data Flow Architecture

![Technical Workflow](tech_flow.png)

### Architecture Highlights

- AWS S3 stores raw and enriched MOT datasets
- AWS Glue + PySpark perform distributed ETL processing
- Athena queries enriched parquet tables
- SageMaker hosts Isolation Forest and XGBoost models
- Power BI provides investigator dashboards
- EventBridge schedules monthly retraining
- Lambda handles event-driven fraud feedback updates

---

# 🧠 Core Machine Learning Strategy

The project intentionally uses a two-layer fraud detection approach.

---

## Phase 1 — Early System (Small Labelled Fraud Dataset)

Initially, confirmed fraud labels are very limited.

Therefore:

- Isolation Forest acts as the PRIMARY model
- XGBoost acts as a SECONDARY enhancement layer
- The platform relies mainly on anomaly detection

This allows suspicious behavioural patterns to be identified even when little historical fraud data exists.

---

## Phase 2 — Mature System (Growing Fraud Library)

As enforcement teams confirm fraud cases monthly:

- Fraud labels continuously grow
- XGBoost retrains using richer labelled datasets
- XGBoost gradually becomes the PRIMARY model
- Isolation Forest becomes the SAFETY NET model

At maturity:

| Model | Operational Role |
|---|---|
| XGBoost | Main fraud probability engine |
| Isolation Forest | Detects novel unseen fraud patterns |

Isolation Forest remains important because it can still detect:
- new fraud behaviours
- previously unseen attack patterns
- anomalies not yet represented in labelled fraud data

This mirrors how enterprise fraud systems evolve operationally in production environments.

---

# 📊 System Presentation Slides

---

## 1️⃣ Platform Overview

![Overview](slide1-overview.png)

### Highlights
- National-scale MOT fraud context
- Risk ranking workflow
- Continuous retraining lifecycle
- Enforcement feedback loop
- Multi-model fraud detection architecture

---

## 2️⃣ Data Foundation & SQL Enrichment

![Data Foundation](slide2-data-foundation.png)

### Key Data Science Concepts

- SQL LEFT JOIN enrichment
- Window functions
- Peer-group behavioural features
- Fraud rule engineering
- Missingness as signal
- Unit-of-analysis design
- Behavioural feature generation

### Technologies

- SQL
- AWS Glue
- PySpark
- Athena
- S3

---

## 3️⃣ Isolation Forest — Unsupervised Anomaly Detection

![Isolation Forest](slide3-isolation-forest.png)

### Why Isolation Forest

- No labels required
- Scales efficiently to millions of MOT tests
- Detects unusual tester behaviour
- Effective during early fraud-library stages
- Captures previously unseen fraud behaviour

### Alternative Models Evaluated

- LOF (Local Outlier Factor)
- One-Class SVM
- Fast MCD
- PCA inverse reconstruction

### Key Features Engineered

- Test duration
- Tester pass-rate deviation
- Missing odometer behaviour
- Retest frequency
- Peer-group comparisons
- Behavioural consistency metrics

---

## 4️⃣ XGBoost — Supervised Fraud Probability Layer

![XGBoost](slide4-xgboost-risk-scoring.png)

### Why XGBoost

- Learns confirmed fraud patterns
- Handles non-linear feature interactions
- Produces explainable feature importance
- Strong performance on tabular data
- Handles mixed feature types effectively

### Composite Risk Score

The final risk score combines:

- Isolation Forest anomaly score
- XGBoost fraud probability
- Domain-rule activation

This produces:
- HIGH risk cases
- MEDIUM risk cases
- LOW risk cases

allowing enforcement teams to prioritise investigations efficiently.

---

### Explainability & Governance

The system is intentionally designed to remain:

- Explainable to investigators
- Auditable
- Court-defensible
- Operationally interpretable
- GDPR-aware

The architecture avoids black-box decision making.

---

## 5️⃣ Continuous Learning & Feedback Loop

![Feedback Loop](slide5-feedback-loop.png)

### Continuous Improvement Architecture

As enforcement confirms fraud:

1. Verdict returns into fraud library
2. SQL enriched datasets update
3. XGBoost retrains monthly
4. Fraud detection accuracy improves
5. Isolation Forest continues detecting unseen fraud types

This creates a living fraud detection ecosystem rather than a static machine learning model.

---

# ☁️ Cloud & Engineering Stack

| Area | Technology |
|---|---|
| Storage | AWS S3 |
| ETL | AWS Glue |
| Distributed Processing | PySpark |
| Query Engine | Athena |
| ML Platform | SageMaker |
| Unsupervised ML | Isolation Forest |
| Supervised ML | XGBoost |
| Scheduling | AWS EventBridge |
| Event Processing | AWS Lambda |
| Dashboarding | Power BI |
| Analysis | Python + Pandas |
| Feature Engineering | SQL |

---

# 🧪 Data Science Techniques Demonstrated

## Feature Engineering

- Rolling averages
- Peer-group comparisons
- Behavioural aggregation
- Fraud-rule features
- Window functions
- Missingness indicators
- Temporal behavioural features

---

## Machine Learning

- Unsupervised anomaly detection
- Supervised classification
- Ensemble scoring
- Composite risk modelling
- Threshold optimisation
- Explainable AI design

---

## Validation Strategy

- Time-aware validation
- Fraud-library growth simulation
- Controlled enforcement trial design
- Operational evaluation metrics
- Behavioural consistency testing

---

# 🔒 Governance & Responsible AI

The project incorporates:

- GDPR-aware processing
- Data minimisation principles
- Human-in-the-loop enforcement
- Explainable ML outputs
- Auditability considerations
- Operational transparency

No personal identifiers are required for model scoring.

---

# 📈 Future Enhancements

Potential future extensions include:

- ANPR roadside camera integration
- CCTV anomaly detection
- Autoencoder video analysis
- LLM-assisted enforcement reporting
- Real-time fraud streaming pipelines
- Graph-based fraud network analysis
- Reinforcement-learning prioritisation systems

---

# 🎯 What This Project Demonstrates

This project was built to demonstrate:

✅ End-to-end machine learning system design  
✅ Real-world fraud analytics thinking  
✅ Production-scale architecture awareness  
✅ Advanced feature engineering  
✅ MLOps lifecycle understanding  
✅ Cloud-native data science concepts  
✅ Explainable AI design principles  
✅ Operational deployment thinking  
✅ Fraud risk scoring methodologies  
✅ Feedback-driven model evolution  

---

# 👩‍💻 Author

Victoria Moreno Sempere

Data Science | Machine Learning | Fraud Analytics | Healthcare & Public Sector AI
