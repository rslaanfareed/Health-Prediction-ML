# Health Prediction ML

A supervised machine learning classification project for predicting a binary health-related target using multiple machine learning algorithms.

## Models Evaluated

- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- Tuned XGBoost

## Dataset

The dataset contains health-related numerical and categorical features, including Age, BMI, Blood Pressure, Cholesterol, Glucose Level, Heart Rate, Sleep Hours, Exercise Hours, Water Intake, Stress Level, Smoking, Alcohol, Diet, Mental Health, Physical Activity, Medical History, Allergies, Diet Type, and Blood Group.

The target variable is binary (`0` and `1`) and is reasonably balanced.

| Target | Count | Proportion |
|---|---:|---:|
| 0 | 4570 | 47.86% |
| 1 | 4979 | 52.14% |

## Project Workflow

```text
Data Loading → Data Exploration → Preprocessing → Feature Analysis
→ Train/Test Split → Model Training → Evaluation → Model Comparison
→ XGBoost Tuning → Feature Importance → Cross-Validation → Final Evaluation
```

## Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix

ROC-AUC measures how well the model separates the two classes across different probability thresholds. It is different from accuracy.

## Model Results

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 81.31% | 81.75% | 82.73% | 82.24% | 0.8879 |
| Decision Tree | 89.16% | 88.41% | 91.16% | 89.77% | 0.8907 |
| Random Forest | 93.66% | 92.60% | 95.48% | 94.02% | 0.9845 |
| XGBoost | 95.18% | 94.49% | 96.39% | 95.43% | 0.9888 |
| **Tuned XGBoost** | **95.65%** | **94.98%** | **96.79%** | **95.87%** | **0.9898** |

## XGBoost Hyperparameter Tuning

Best parameters:

```python
{
    "subsample": 0.9,
    "n_estimators": 300,
    "min_child_weight": 1,
    "max_depth": 8,
    "learning_rate": 0.05,
    "colsample_bytree": 1.0
}
```

Best cross-validation ROC-AUC: **0.9841**

## Final Model Performance

The tuned XGBoost model achieved:

- Accuracy: **95.65%**
- Precision: **94.98%**
- Recall: **96.79%**
- F1 Score: **95.87%**
- ROC-AUC: **0.9898**

Confusion Matrix:

```text
[[863   51]
 [ 32  964]]
```

## Feature Importance

The most important features included:

1. BMI
2. Cholesterol
3. Stress Level
4. Glucose Level
5. Sleep Hours
6. Blood Pressure
7. Water Intake
8. Heart Rate
9. Exercise Hours
10. Age

## Cross-Validation

Five-fold cross-validation was performed for XGBoost.

| Metric | Mean ± Standard Deviation |
|---|---:|
| Accuracy | 94.15% ± 0.61% |
| Precision | 94.12% ± 1.00% |
| Recall | 94.70% ± 0.28% |
| F1 | 94.41% ± 0.55% |
| ROC-AUC | 0.9818 ± 0.0025 |

## Full Features vs Numerical Features

| Metric | Full Features | Numerical Only |
|---|---:|---:|
| Accuracy | 95.02% ± 0.57% | **95.32% ± 0.61%** |
| Precision | 95.08% ± 0.69% | **95.42% ± 0.78%** |
| Recall | 95.38% ± 0.51% | **95.62% ± 0.60%** |
| F1 | 95.23% ± 0.54% | **95.52% ± 0.58%** |
| ROC-AUC | 0.9860 ± 0.0039 | **0.9869 ± 0.0040** |

## Repository Structure

```text
Health-Prediction-ML/
├── Health_Prediction.ipynb
├── dataset.csv
├── README.md
├── requirements.txt
└── .gitignore
```

## Technologies Used

Python, NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn, XGBoost, and Jupyter Notebook.

## Conclusion

Tuned XGBoost was the best-performing model, achieving **95.65% accuracy, 95.87% F1 Score, and 0.9898 ROC-AUC** on the evaluated test set.

The project demonstrates a complete supervised machine learning workflow covering data exploration, preprocessing, model comparison, hyperparameter tuning, feature analysis, and cross-validation.

> **Note:** These results represent performance on the provided dataset and should not be interpreted as clinical diagnostic performance or automatically generalized to real-world medical populations.
