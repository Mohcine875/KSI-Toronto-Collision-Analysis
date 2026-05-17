# Data Dictionary

## Overview

This document describes the main variables and engineered features used in the KSI Toronto Collision Analysis project.

The project uses collision-related features to predict whether a collision is fatal or non-fatal.

---

## Target Variable

| Variable | Description |
|---|---|
| `TARGET` | Binary target variable used for prediction |
| `0` | Non-Fatal collision |
| `1` | Fatal collision |

---

## Main Feature Groups

The dataset includes several types of features:

| Feature Group | Examples | Purpose |
|---|---|---|
| Time-based features | `YEAR`, `MONTH`, `DAY_OF_WEEK`, `HOUR` | Capture temporal collision patterns |
| Engineered time features | `WEEKEND`, `SEASON`, `TIME_PERIOD`, `RUSH_HOUR` | Improve interpretation of collision timing |
| Geographic features | `HOOD_158`, `NEIGHBOURHOOD_158`, `HIGH_RISK_NEIGHBOURHOOD` | Capture spatial collision patterns |
| Road condition features | `ROAD_CLASS`, `RDSFCOND` | Describe road type and surface condition |
| Environmental features | `LIGHT`, `VISIBILITY` | Capture lighting and visibility conditions |
| Collision-related features | `INVTYPE`, `IMPACTYPE`, `INJURY` | Describe collision context and involved parties |

---

## Engineered Features

| Feature | Description |
|---|---|
| `WEEKEND` | Indicates whether the collision happened on a weekend |
| `SEASON` | Represents the season of the collision |
| `MONTH_PART` | Groups the month into beginning, middle, or end |
| `DAY_NIGHT` | Indicates whether the collision occurred during the day or night |
| `TIME_PERIOD` | Groups the hour into morning, afternoon, evening, or night |
| `RUSH_HOUR` | Indicates whether the collision occurred during rush hour |
| `HIGH_RISK_NEIGHBOURHOOD` | Indicates whether the collision occurred in a high-risk neighbourhood |

---

## Power BI Label Columns

Some encoded columns were transformed into readable labels for dashboard interpretation.

| Label Column | Purpose |
|---|---|
| `TARGET_LABEL` | Displays Fatal / Non-Fatal labels |
| `DAY_NIGHT_LABEL` | Displays Day / Night labels |
| `TIME_PERIOD_LABEL` | Displays readable time periods |
| `SEASON_LABEL` | Displays readable seasons |
| `LIGHT_LABEL` | Displays readable light condition labels |
| `RDSFCOND_LABEL` | Displays readable road surface condition labels |
| `VISIBILITY_LABEL` | Displays readable visibility condition labels |
| `ROAD_CLASS_LABEL` | Displays readable road class labels |

---

## Modeling Notes

For machine learning, categorical variables were encoded and numerical variables were scaled.

SMOTE was applied only on the training dataset to reduce class imbalance while keeping the test set realistic.

The final prediction target remained:

```text
0 = Non-Fatal
1 = Fatal
