# Credit Card Fraud Detection

## Problem Statement
Built a Fraud Detection System to identify fraudulent credit card transactions using Machine Learning.

## Dataset
- Kaggle Credit Card Fraud Detection Dataset
- 284,807 transactions, 0.17% fraud cases
- Highly imbalanced dataset (492 fraud out of 284,807)

## Tech Stack
- Python, Scikit-learn, XGBoost, Imbalanced-learn
- SMOTE for class imbalance handling
- RandomizedSearchCV for hyperparameter tuning

## Preprocessing
- StandardScaler applied on Amount feature
- Time feature dropped
- 80-20 train-test split with stratification
- SMOTE applied only on training data to avoid data leakage

## Models Compared

| Model | Precision | Recall | F1-Score | ROC-AUC |
|-------|-----------|--------|----------|---------|
| Logistic Regression | 0.06 | 0.92 | 0.11 | 0.9700 |
| Random Forest | 0.87 | 0.83 | 0.85 | 0.9737 |
| XGBoost (Default) | 0.69 | 0.87 | 0.77 | 0.9753 |
| XGBoost (Tuned) | 0.78 | 0.85 | 0.81 | 0.9753 |

## Hyperparameter Tuning
Used RandomizedSearchCV with 3-fold cross-validation.

Best parameters found:
- n_estimators: 300
- max_depth: 6
- learning_rate: 0.2
- subsample: 0.7

## Threshold Tuning
Analyzed Precision-Recall tradeoff across different thresholds.

| Threshold | Precision | Recall | F1-Score |
|-----------|-----------|--------|----------|
| 0.3 | 0.70 | 0.85 | 0.76 |
| 0.4 | 0.78 | 0.85 | 0.81 |
| 0.5 | 0.78 | 0.85 | 0.81 |
| 0.6 | 0.81 | 0.85 | 0.83 |

## Final Model Results

Final Tuned XGBoost model (threshold = 0.6) achieved:
- ROC-AUC: 0.9753
- Precision: 0.81
- Recall: 0.85
- F1-Score: 0.83

## Confusion Matrix

| | Predicted: Legitimate | Predicted: Fraud |
|---|---|---|
| Actual: Legitimate | TN = 56,840 | FP = 24 |
| Actual: Fraud | FN = 15 | TP = 83 |

## Feature Importance
V14 emerged as the most important feature with approximately 62% importance, followed by V4 and V12. Features are PCA-transformed for privacy.

## Business Impact
- Correctly detected 83 out of 98 fraud transactions
- Achieved 85% fraud recall
- Threshold tuning allows organizations to balance fraud detection and false alarms based on business requirements, without retraining the model

## Future Improvements
- SHAP values for model interpretability
- Real-time deployment via FastAPI
