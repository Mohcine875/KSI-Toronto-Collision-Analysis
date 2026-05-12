# Model Card — KSI Collision Fatality Prediction

## Model Overview

This project uses a supervised machine learning model to predict whether a traffic collision is fatal or non-fatal.

The final selected model is:

**Random Forest Classifier**

The model predicts:

- `0` = Non-Fatal collision
- `1` = Fatal collision

---

## Training Data

The model was trained using prepared KSI collision data after:

- data cleaning
- missing value handling
- feature engineering
- categorical encoding
- numerical scaling
- train/test split
- SMOTE balancing on the training set

---

## Models Compared

Five classification models were trained and evaluated:

- Logistic Regression
- Decision Tree
- Random Forest
- SVM
- Neural Network

---

## Model Performance

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.6233 | 0.2061 | 0.5861 | 0.3049 | 0.6509 |
| Decision Tree | 0.8904 | 0.6049 | 0.6423 | 0.6231 | 0.7866 |
| Random Forest | 0.9314 | 0.9790 | 0.5243 | 0.6829 | 0.9339 |
| SVM | 0.8699 | 0.5375 | 0.5506 | 0.5439 | 0.8375 |
| Neural Network | 0.8976 | 0.6209 | 0.7022 | 0.6591 | 0.8906 |

---

## Selected Model

Random Forest was selected as the final model because it achieved the strongest overall performance.

It had the highest:

- Accuracy
- Precision
- F1-Score
- ROC-AUC

Although the Neural Network achieved higher recall, Random Forest provided the best overall balance between prediction quality and reliability.

---

## Classification Report — Random Forest

| Class | Precision | Recall | F1-Score | Support |
|---|---:|---:|---:|---:|
| Non-Fatal | 0.93 | 1.00 | 0.96 | 3254 |
| Fatal | 0.98 | 0.52 | 0.68 | 534 |

Overall accuracy: **0.93**

---

## Model Limitations

The model performs very well overall, but it still misses some fatal collisions.

The main limitation is:

- fatal collisions are the minority class
- the model has lower recall for fatal cases
- some fatal cases may be predicted as non-fatal

This is important because fatal collision detection is the most sensitive part of the project.

---

## Future Improvements

Possible improvements include:

- threshold tuning to improve fatal collision recall
- hyperparameter tuning
- testing additional imbalance-handling methods
- using more advanced ensemble models
- adding more contextual features
- deploying the model through a Flask or FastAPI application

---

## Reproducibility

The final trained model file is not included in the repository due to file size limitations.

To reproduce the model, run:

```text
notebooks/KSI_Step3_Model_Building.ipynb
```

This notebook trains all models, compares performance, selects Random Forest, and saves the final trained model locally.
