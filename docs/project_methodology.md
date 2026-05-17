# Project Methodology

## Overview

This project follows an end-to-end data science and machine learning workflow to analyze Toronto KSI collision data and predict whether a collision is fatal or non-fatal.

The methodology includes:

1. Data understanding
2. Exploratory data analysis
3. Data cleaning and preprocessing
4. Feature engineering
5. Model building and evaluation
6. Prediction workflow
7. Power BI dashboarding
8. GitHub documentation

---

## 1. Data Understanding

The project uses Toronto Killed or Seriously Injured (KSI) collision data.

The objective is to understand collision patterns and build a predictive model that classifies collisions as:

- `0` = Non-Fatal
- `1` = Fatal

---

## 2. Exploratory Data Analysis

The EDA phase focused on understanding the structure and behavior of the dataset.

Main analysis areas included:

- dataset shape and column types
- missing values
- target variable distribution
- collision trends over time
- seasonal and temporal patterns
- geographic collision patterns
- correlation analysis
- fatal vs non-fatal comparison

This step helped identify important patterns and potential modeling challenges such as class imbalance.

---

## 3. Data Cleaning and Preprocessing

The cleaning stage prepared the dataset for machine learning.

Main preprocessing steps included:

- removing irrelevant rows
- dropping weak or highly missing columns
- handling missing values
- removing unnecessary identifiers
- encoding categorical variables
- scaling numerical features
- splitting the data into training and testing sets

The data was prepared carefully to avoid leakage and maintain a clean modeling workflow.

---

## 4. Feature Engineering

Additional features were created to improve model learning and dashboard analysis.

Engineered features included:

- `WEEKEND`
- `SEASON`
- `MONTH_PART`
- `DAY_NIGHT`
- `TIME_PERIOD`
- `RUSH_HOUR`
- `HIGH_RISK_NEIGHBOURHOOD`

These features helped capture temporal and geographic collision risk patterns.

---

## 5. Class Imbalance Handling

Fatal collisions represent a minority class in the dataset.

To address this issue, SMOTE was applied to the training set only. This helped balance the training data while keeping the test set unchanged for realistic evaluation.

---

## 6. Model Building

Five supervised machine learning models were trained and evaluated:

- Logistic Regression
- Decision Tree
- Random Forest
- SVM
- Neural Network

The goal was to compare multiple algorithms and select the best-performing model.

---

## 7. Model Evaluation

The models were evaluated using multiple metrics:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- Confusion Matrix
- Classification Report

Because the dataset is imbalanced, F1-score, recall, and ROC-AUC were considered more informative than accuracy alone.

---

## 8. Best Model Selection

Random Forest was selected as the final model because it achieved the strongest overall performance across the evaluation metrics.

Although the Neural Network achieved higher recall, Random Forest provided the best overall balance between prediction quality and reliability.

---

## 9. Prediction Workflow

The final model was used to generate predictions on the test dataset.

The prediction workflow included:

- loading the final model
- loading test data
- generating predictions
- generating fatality probabilities
- comparing actual vs predicted values
- saving prediction results

---

## 10. Power BI Dashboard

A four-page Power BI dashboard was created to communicate the main findings visually.

Dashboard pages:

1. Executive Overview
2. Temporal Patterns of Collisions
3. Geographic Risk Analysis
4. Environmental and Road Conditions

The dashboard helps communicate insights clearly for both technical and non-technical audiences.

---

## 11. Reproducibility

The project is organized so that the workflow can be reproduced by running the notebooks in order:

1. `KSI_Step1_EDA.ipynb`
2. `KSI_Step2_Cleaning.ipynb`
3. `KSI_Step3_Model_Building.ipynb`
4. `KSI_Step4_Prediction.ipynb`

---

## Summary

This methodology provides a complete end-to-end workflow from raw data understanding to machine learning prediction and dashboard reporting.
