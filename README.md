# 📊 Customer Churn Prediction using Machine Learning

<p align="center">
  <img src="https://img.shields.io/badge/Model-CatBoost-blue" />
  <img src="https://img.shields.io/badge/Metric-PR--AUC-orange" />
  <img src="https://img.shields.io/badge/Problem-Customer%20Churn-red" />
  <img src="https://img.shields.io/badge/Status-Completed-success" />
</p>

---

## 🧠 Problem Statement
Customer churn directly impacts revenue and long-term growth.  
This project focuses on **identifying customers likely to churn** and **supporting business decisions** using a metric-driven machine learning approach.

---

## 🎯 Project Objectives
- Handle **imbalanced churn data**
- Prioritize **recall for churners**
- Select an **optimal decision threshold**
- Compare baseline vs advanced models
- Translate ML outputs into **actionable business insights**

---

## 🗂 Dataset Overview
- **Dataset**: Telco Customer Churn (IBM)
- **Target Variable**: `Churn` (Yes / No)
- **Churn Rate**: ~23%
- **Challenge**: Highly imbalanced classes

---

## 📐 Why PR-AUC instead of Accuracy?

Accuracy is misleading for imbalanced datasets.

**PR-AUC was chosen because:**
- Focuses on the **minority class (churners)**
- Captures the **precision–recall trade-off**
- Aligns with the **business cost of missing churners**

---

## 🧪 Modeling Pipeline

```text
Data Cleaning
     ↓
EDA & Feature Understanding
     ↓
Baseline Model (Logistic Regression)
     ↓
CatBoost Classifier
     ↓
PR-AUC Evaluation
     ↓
Threshold Optimization
     ↓
Feature Importance & SHAP Analysis
     ↓
Business Insights
```
## 🤖 Models Used

| Model | Purpose |
|------|--------|
| **Logistic Regression** | Baseline comparison |
| **CatBoost Classifier** | Final model (handles categorical features natively) |

### 🔧 Techniques Applied
- Stratified K-Fold Cross-Validation  
- Class Weights for imbalance handling  
- Early Stopping to prevent overfitting  
- Probability-based evaluation  
- Business-driven threshold tuning  

---

## 📈 Model Evaluation

### 🔹 Precision–Recall Curve Analysis
- Compared **Logistic Regression vs CatBoost**
- CatBoost consistently maintained **higher precision at high recall**
- Demonstrated superior ranking ability on imbalanced churn data

### 🔹 Threshold Selection
- Selected **threshold = 0.38**
- Achieved approximately **90% recall** for churners
- Threshold treated as a **business decision**, not a fixed statistical rule

---
```text
IF churn_probability > 0.38:
    → High-Risk Customer
    → Apply targeted retention strategy
ELSE:
    → Low-Risk Customer

```

## 🔍 Feature Importance & SHAP Explainability

SHAP was used to explain **both global feature importance** and **individual churn predictions**, ensuring transparency and trust.

### 🔑 Key Churn Drivers Identified
- 📄 **Contract** → Month-to-month contracts significantly increase churn  
- ⏳ **Tenure** → New customers are more likely to churn  
- 💰 **MonthlyCharges** → Higher charges correlate with churn  
- 🔐 **OnlineSecurity / TechSupport** → Reduce churn risk  
- 📺 **StreamingTV / OnlineBackup** → Increase customer stickiness  

SHAP analysis enabled the model to explain **why a specific customer is predicted to churn**, making the solution suitable for real-world decision support.

<img width="1187" height="774" alt="image" src="https://github.com/user-attachments/assets/8f0c5a56-02d5-42cc-8e26-d63efde64d81" />
