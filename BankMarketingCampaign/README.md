# Bank Marketing Classification using Machine Learning

> **Using supervised machine learning to improve the efficiency of bank
> direct marketing campaigns by reducing unnecessary customer contacts
> while maintaining successful term deposit subscriptions.**

------------------------------------------------------------------------

# Project Overview

This project explores how supervised machine learning can support **bank
direct marketing optimization**. Rather than contacting every customer,
the objective is to identify customers who are most likely to subscribe
to a term deposit so that marketing resources can be focused where they
are most effective.

This notebook follows an iterative workflow inspired by the **CRISP-DM
(Cross Industry Standard Process for Data Mining)** methodology and
evaluates multiple classification algorithms using the UCI Bank
Marketing dataset.

------------------------------------------------------------------------

# Business Objective

Banks frequently conduct direct marketing campaigns to promote financial
products such as long-term deposits. Telephone campaigns require
significant staffing, time, and operational cost.

**Business Goal**

> Reduce the number of marketing contacts (and therefore campaign cost)
> while maintaining approximately the same number of successful term
> deposit subscriptions.

Achieving this objective enables the bank to improve campaign efficiency
and maximize marketing ROI.

------------------------------------------------------------------------

# Machine Learning Objective

To support the business objective, this project investigates:

> **Can customer demographic and account information alone accurately
> distinguish likely subscribers from non-subscribers?**

If successful, the resulting model can prioritize customer contacts
before a campaign begins.

------------------------------------------------------------------------

# Technical Objective

This notebook compares four widely-used supervised classification
algorithms:

-   Logistic Regression
-   K-Nearest Neighbors (KNN)
-   Decision Tree
-   Support Vector Machine (SVM)

The models are evaluated through:

-   Baseline model comparison
-   Hyperparameter tuning
-   Class imbalance handling
-   Grid Search
-   Cross Validation

Evaluation metrics include:

-   Accuracy
-   Precision
-   Recall
-   F1-score
-   ROC-AUC
-   Training time
-   Model interpretability

------------------------------------------------------------------------

# Learning Objectives

By completing this notebook readers will learn how to:

-   Build baseline classification models
-   Prepare mixed numerical and categorical data
-   Apply One-Hot Encoding and Standardization
-   Compare multiple classification algorithms
-   Tune hyperparameters using GridSearchCV
-   Handle class imbalance using class weights
-   Evaluate models with multiple performance metrics
-   Perform Stratified Cross Validation
-   Interpret Logistic Regression coefficients and odds ratios
-   Understand the trade-offs between predictive performance,
    computational efficiency, and interpretability

------------------------------------------------------------------------

# Dataset

**Source**

UCI Machine Learning Repository

https://archive.ics.uci.edu/dataset/222/bank+marketing

Dataset:

`bank-additional-full.csv`

Target variable:

`y`

-   yes
-   no

------------------------------------------------------------------------

# Phase 1 Scope (Current Notebook)

Only **bank client information** was used:

-   age
-   job
-   marital
-   education
-   default
-   housing
-   loan

Campaign history, contact information, macroeconomic variables, and call
duration were intentionally excluded to evaluate the predictive power of
customer profile alone.

------------------------------------------------------------------------

# Workflow

1.  Data understanding
2.  Data preparation
3.  Baseline models
4.  Hyperparameter tuning
5.  Class imbalance handling
6.  Grid Search
7.  Cross Validation
8.  Logistic Regression interpretation

------------------------------------------------------------------------

# Major Experiments

## Baseline Models

Compared all four classifiers using default settings.

## Hyperparameter Tuning

Optimized each classifier using GridSearchCV.

## Class Imbalance

Applied `class_weight="balanced"` where supported.

## Cross Validation

Evaluated stability using 5-fold Stratified Cross Validation.

## Model Interpretation

Balanced Logistic Regression was selected for interpretation through:

-   coefficients
-   odds ratios
-   effect strength
-   business-friendly interpretation table

------------------------------------------------------------------------

# Results Snapshot

**Best Overall Model**

Balanced Logistic Regression

**Major Findings**

-   High baseline accuracy was largely due to class imbalance.
-   Hyperparameter tuning produced only modest improvements.
-   Class imbalance handling produced the largest improvement.
-   Balanced Logistic Regression achieved the best balance between
    performance, speed, stability, and interpretability.
-   Balanced SVM achieved similar predictive performance but required
    over 2,000× longer training time.

------------------------------------------------------------------------

# Business Summary

The analysis demonstrates that meaningful predictive models can be built
using only customer demographic and account information, but this
information alone provides only moderate predictive power.

Balanced Logistic Regression emerged as the preferred model because it
combined strong recall, competitive ROC-AUC, excellent computational
efficiency, stable cross-validation performance, and straightforward
interpretability.

The study also demonstrates that:

-   Accuracy alone is misleading for imbalanced marketing datasets.
-   Handling class imbalance contributed substantially more than
    hyperparameter tuning.
-   Customer demographics alone are insufficient to fully solve the
    business problem.

These findings strongly suggest that future performance improvements
will come primarily from incorporating campaign history, contact
information, and macroeconomic indicators rather than further algorithm
tuning alone.

------------------------------------------------------------------------

# Technologies

-   Python
-   Pandas
-   NumPy
-   Matplotlib
-   Scikit-learn

------------------------------------------------------------------------

# Repository Structure

    .
    ├── data/
    ├── notebooks/
    ├── README.md
    └── requirements.txt

------------------------------------------------------------------------

# Roadmap

## Phase 1 (Completed)

-   ✅ Baseline models
-   ✅ Hyperparameter tuning
-   ✅ Class imbalance handling
-   ✅ Grid Search
-   ✅ Cross Validation
-   ✅ Logistic Regression interpretation

## Phase 2 (/ TBD)

-   Campaign history features
-   Contact features
-   Economic indicators
-   Feature engineering
-   Threshold optimization
-   SHAP explanations
-   Ensemble models
-   Random Forest
-   Gradient Boosting
-   XGBoost
-   LightGBM

------------------------------------------------------------------------

# References

Moro, S., Laureano, R., & Cortez, P.

**Using Data Mining for Bank Direct Marketing: An Application of the
CRISP-DM Methodology**

UCI Machine Learning Repository

https://archive.ics.uci.edu/dataset/222/bank+marketing

------------------------------------------------------------------------

# License

This repository is intended for educational and research purposes.
