# Predictive Maintenance using Machine Learning

## About the Project

This project develops a machine learning solution for **Predictive Maintenance** to proactively identify devices at risk of failure. By leveraging sensor data collected from devices, we build models that estimate the probability of failure and help plan maintenance before breakdowns occur.

### Business Problem

A company operates a fleet of sensor-enabled devices. Currently, maintenance is either time-based or reactive, both of which are inefficient and costly. Predictive Maintenance aims to:

- Detect early signs of failure
- Reduce unplanned downtime
- Minimize unnecessary maintenance
- Improve device reliability and lifespan

---

## Dataset Overview

The dataset consists of daily sensor readings from multiple devices:

| Column Name | Description |
|-------------|-------------|
| `Date`      | Date of sensor reading |
| `Device`    | Device identifier |
| `Failure`   | Binary label (1 = Failure, 0 = No Failure) |
| `metric1` to `metric9` | Sensor data (numeric) |

> **Note:** The dataset is highly imbalanced with a failure rate of ~0.085%.

---

## Exploratory Data Analysis (EDA)

Key insights from the EDA:

- **Boxplots** show variation in sensor metrics across devices.
- **Failure counts** highlight the class imbalance.
- **Time series plots** help visualize failures over time.
- **Correlation matrix** checks for multicollinearity between metrics.

---

## Machine Learning Models

We trained and evaluated several classification models:

- **Naive Bayes**
- **Decision Tree**
- **Logistic Regression**

Initial results were weak due to severe class imbalance.

---

## Handling Class Imbalance

Two main techniques were applied:

### SMOTE (Synthetic Minority Over-sampling Technique)

- Balances the dataset by creating synthetic samples of the minority class.
- Helps improve recall and F1 score without sacrificing accuracy.

### Undersampling

- Reduces the size of the majority class.
- Simple and effective, but may discard valuable information.

---

## Final Results

The best performance was achieved using **SMOTE with Decision Tree**:

- **Precision:** 0.8800  
- **Recall:** 0.9167  
- **F1 Score:** 0.8980  
- **Accuracy:** 0.8837



## Future Work

- Experiment with ensemble models like Random Forest and XGBoost
- Incorporate time-series models (e.g. LSTM)
- Tune hyperparameters using GridSearchCV
- Develop a real-time prediction pipeline


