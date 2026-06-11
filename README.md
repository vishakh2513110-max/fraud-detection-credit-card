# Credit Card Fraud Detection using Machine Learning

## Problem Statement
The objective of this project is to detect fraudulent credit card transactions and distinguish them from legitimate transactions. Since fraud cases are extremely rare, the project focuses on handling class imbalance and minimizing missed fraud cases.

---

## Dataset
- Dataset: Kaggle Credit Card Fraud Detection Dataset
- Total Transactions: 284,807
- Fraudulent Transactions: 492 (~0.17%)
- Features: Time, Amount, V1-V28 (PCA-transformed features)
- Target Variable:
  - 0 = Legitimate Transaction
  - 1 = Fraudulent Transaction

---

## Technologies Used
- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Imbalanced-learn (SMOTE)
- Matplotlib
- Seaborn

---

## Project Workflow

1. Data Loading and Exploration
2. Data Preprocessing
3. Train-Test Split
4. Handling Class Imbalance using SMOTE
5. Model Training
   - Logistic Regression
   - Random Forest
   - XGBoost
6. Model Evaluation
7. Model Comparison
8. Selection of Best Model

---

## Model Performance

| Model | Precision | Recall | F1-Score | ROC-AUC |
|---------|---------|---------|---------|---------|
| Logistic Regression | 0.06 | 0.92 | 0.11 | 0.97 |
| Random Forest | 0.87 | 0.83 | 0.85 | 0.9737 |
| XGBoost | 0.89 | 0.92 | 0.90 | 0.98 |

---

## Why XGBoost?

XGBoost achieved the best overall performance among all models.

- Precision: 89%
- Recall: 92%
- F1-Score: 90%
- ROC-AUC: 0.98

XGBoost outperformed Random Forest because it uses boosting, where each new tree focuses on correcting the mistakes made by previous trees. This helped capture rare fraud patterns more effectively.

---

## Key Learnings

- Handling highly imbalanced datasets
- SMOTE and data leakage prevention
- Precision vs Recall trade-off
- Ensemble Learning
- Random Forest
- XGBoost
- ROC-AUC Evaluation
- Fraud Detection using Machine Learning

---

## Business Impact

The final model can automatically flag suspicious transactions for further investigation. This can help financial institutions reduce fraud-related losses and improve operational efficiency.

---

## Author

Vishakh
