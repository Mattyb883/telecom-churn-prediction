# Interconnect Churn Prediction Project

## Overview

This project focuses on predicting customer churn for **Interconnect**, a fictional telecom provider. The goal is to identify customers likely to leave the service, enabling proactive retention strategies such as promotions and personalized offers.

The project was completed as part of a data science sprint and includes end-to-end data processing, model training, evaluation, and interpretation.

---

## Dataset Description

The dataset consists of four CSV files:
- `contract.csv`: Customer contract information
- `personal.csv`: Demographics such as age, partner status, dependents
- `internet.csv`: Internet service subscriptions and usage
- `phone.csv`: Phone service and multiline options

Each file includes a `customerID` column used to merge them into a single dataset.

---

## Process and Workflow

1. **Data Loading and Merging**
   - Combined all four datasets on `customerID`
   - Handled missing values and cleaned data types

2. **Feature Engineering**
   - Created a `Tenure` feature based on signup date and snapshot date
   - Binary encoded service features (Yes/No → 1/0)
   - One-hot encoded categorical variables
   - Removed non-informative features like `customerID`

3. **Exploratory Data Analysis (EDA)**
   - Visualized churn distribution
   - Explored value counts and feature distributions
   - Correlation heatmap and feature importance analysis

4. **Modeling**
   - Evaluated five models:
     - Logistic Regression
     - Random Forest
     - Gradient Boosting
     - LightGBM
     - XGBoost
   - Used `AUC-ROC` as the primary performance metric

---

## Best Model Performance

The final model selected was **XGBoost**, which outperformed all others:

- **AUC-ROC:** 0.9318
- **Accuracy:** 89.43%

A feature importance plot and correlation matrix provided additional insights into which services and contract types were most predictive of churn.

---

## Key Insights

- Customers on **month-to-month** contracts or with **fiber optic** internet were more likely to churn.
- Longer tenure and **two-year contracts** correlated strongly with customer retention.
- Specific features like `PaymentMethod_Electronic check` and lack of `OnlineSecurity` also increased churn risk.

---

## Deliverables

- Jupyter Notebook: Full exploratory and modeling workflow
- Visualizations: Feature importance, churn distribution, and correlations
- Final Summary Report: Project wrap-up with model comparison and business insights

---

## Future Work

- Incorporate behavioral data (support tickets, login activity)
- Deploy the model with a real-time prediction interface
- Build a dashboard for marketing to target at-risk customers

---

## Tools & Libraries

- Python, Pandas, NumPy
- Scikit-learn, XGBoost, LightGBM
- Matplotlib, Seaborn
