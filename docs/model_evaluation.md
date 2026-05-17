# Model Evaluation

## Overview

This document summarizes the machine learning model evaluation process for the KSI Toronto Collision Analysis project.

The objective of the model evaluation phase was to compare several supervised classification models and select the best model for predicting whether a collision is fatal or non-fatal.

---

## Target Variable

The prediction target is binary:

- `0` = Non-Fatal collision
- `1` = Fatal collision

Because fatal collisions are less frequent than non-fatal collisions, the dataset is imbalanced. For this reason, accuracy alone is not sufficient to evaluate model performance.

---

## Models Evaluated

Five classification models were trained and compared:

- Logistic Regression
- Decision Tree
- Random Forest
- SVM
- Neural Network

---

## Evaluation Metrics

The models were evaluated using the following metrics:

| Metric | Purpose |
|---|---|
| Accuracy | Measures the overall percentage of correct predictions |
| Precision | Measures how reliable fatal predictions are |
| Recall | Measures how many actual fatal cases were detected |
| F1-Score | Balances precision and recall |
| ROC-AUC | Measures how well the model separates fatal and non-fatal cases |

Because the dataset is imbalanced, F1-Score, Recall, and ROC-AUC are especially important.

---

## Model Comparison Results

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.6233 | 0.2061 | 0.5861 | 0.3049 | 0.6509 |
| Decision Tree | 0.8904 | 0.6049 | 0.6423 | 0.6231 | 0.7866 |
| Random Forest | 0.9314 | 0.9790 | 0.5243 | 0.6829 | 0.9339 |
| SVM | 0.8699 | 0.5375 | 0.5506 | 0.5439 | 0.8375 |
| Neural Network | 0.8976 | 0.6209 | 0.7022 | 0.6591 | 0.8906 |

---

## Best Model Selection

Random Forest was selected as the best overall model.

It achieved the highest:

- Accuracy
- Precision
- F1-Score
- ROC-AUC

Although the Neural Network achieved the highest recall, Random Forest provided the strongest overall balance between prediction reliability and model performance.

---

## Random Forest Classification Report

| Class | Precision | Recall | F1-Score | Support |
|---|---:|---:|---:|---:|
| Non-Fatal | 0.93 | 1.00 | 0.96 | 3254 |
| Fatal | 0.98 | 0.52 | 0.68 | 534 |

Overall accuracy: **0.93**

---

## Interpretation

The Random Forest model performs very well overall, especially for non-fatal collision classification.

For fatal collisions, the model achieves high precision. This means that when the model predicts a fatal collision, it is usually correct.

However, the recall for fatal collisions is lower. This means that some actual fatal collisions are still predicted as non-fatal.

This limitation is important because fatal collision detection is the most sensitive part of the project.

---

## Error Analysis

The prediction analysis showed that many incorrect predictions were fatal cases predicted as non-fatal.

This suggests that future work should focus on improving fatal collision recall.

Possible improvements include:

- threshold tuning
- hyperparameter tuning
- additional imbalance-handling methods
- testing more advanced ensemble methods
- adding more contextual features

---

## Conclusion

Random Forest was selected as the final model because it provided the best overall performance across the evaluation metrics.

The model is strong enough for project-level prediction and portfolio demonstration, but future improvements should focus on improving fatal collision recall.
