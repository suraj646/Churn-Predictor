📊 Customer Churn Prediction

Metric-Driven ML Analysis with Business Insights

<p align="center"> <img src="https://img.shields.io/badge/Machine%20Learning-CatBoost-blue" /> <img src="https://img.shields.io/badge/Metric-PR--AUC-orange" /> <img src="https://img.shields.io/badge/Problem-Churn%20Prediction-red" /> <img src="https://img.shields.io/badge/Status-Completed-success" /> </p>
🧠 Problem Statement

Customer churn directly impacts revenue.
This project aims to identify customers likely to churn and support business decision-making using a metric-driven machine learning approach.

🎯 Project Goals

✔ Handle imbalanced churn data
✔ Optimize for business-relevant metrics
✔ Compare baseline vs advanced models
✔ Translate ML outputs into actionable insights

🗂 Dataset Overview

Dataset: Telco Customer Churn

Target: Churn (Yes / No)

Churn Rate: ~23%

Challenge: Class imbalance

📐 Why PR-AUC (Not Accuracy?)

Accuracy can be misleading when churners are a minority.

✔ PR-AUC focuses on churners (minority class)
✔ Captures precision–recall trade-off
✔ Aligns with cost of false negatives

🧪 Modeling Pipeline
Data Cleaning
     ↓
EDA & Feature Understanding
     ↓
Baseline Model (Logistic Regression)
     ↓
CatBoost (Final Model)
     ↓
PR-AUC Evaluation
     ↓
Threshold Optimization
     ↓
Feature Importance → Business Actions

🤖 Models Used
Model	Purpose
Logistic Regression	Baseline comparison
CatBoost	Final model (handles categorical features)

Techniques Applied

Stratified K-Fold Cross Validation

Class Weights

Early Stopping

Threshold tuning

📈 Model Evaluation
🔹 Precision–Recall Curve Comparison

CatBoost maintains higher precision at high recall

Outperforms Logistic Regression consistently

🔹 Threshold Selection

Selected threshold = 0.4

Achieved ~90% recall for churners

Threshold selection treated as a business decision, not a mathematical one.

🔍 Feature Importance → Business Actions
Feature	Insight	Action
📄 Contract	Month-to-month churn more	Promote long-term plans
⏳ Tenure	Early churn risk	Strong onboarding
💰 MonthlyCharges	Price sensitivity	Discounts
📺 StreamingTV	Service stickiness	Bundled offers
🔐 OnlineSecurity	Value addition	Free trials
🧠 Business Decision Logic
IF churn_probability > 0.4:
    → High Risk Customer
    → Apply targeted retention strategy
ELSE:
    → Low Risk Customer

📌 Key Takeaways

✔ Metric choice > model complexity
✔ Threshold tuning is crucial
✔ ML should drive actions, not just predictions

🚀 Future Improvements

SHAP explainability

Cost-based optimization

Model monitoring
