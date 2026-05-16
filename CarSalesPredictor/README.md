# Used Car Price Prediction & Modeling

## Project Overview

This project applies the CRISP-DM (Cross Industry Standard Process for Data Mining) framework to analyze and model used car pricing behavior using a large marketplace dataset of approximately 426,000 vehicle listings.

The primary objective was to identify the key drivers of used car prices and build machine learning models capable of predicting vehicle prices while balancing:

- predictive performance,

- generalization,

- interpretability,

- and model complexity.

The project explores:

- exploratory data analysis (EDA),

- feature engineering,

- regression modeling,

- polynomial feature expansion,

- regularization techniques,

- feature selection,

- hyperparameter optimization,

- and model evaluation.

---

# Business Problem

Used car dealers often face challenges related to:

- pricing consistency,

- trade-in evaluation,

- inventory optimization,

- and identifying high-margin vehicle segments.

This project aims to answer:

> What factors most strongly influence used car prices, and how can machine learning help improve pricing and inventory decisions?

---

# CRISP-DM Workflow

The project follows the CRISP-DM framework:

1. Business Understanding

2. Data Understanding

3. Data Preparation

4. Modeling

5. Evaluation

6. Deployment Recommendations

---

# Dataset

Dataset contains approximately:

- 426,000 used vehicle listings

Key variables include:

- price

- year

- manufacturer

- model

- condition

- cylinders

- fuel

- odometer

- transmission

- title status

- drive

- type

- paint color

- state

---

# Data Cleaning & Preparation

## Missing Data Handling

Columns with extremely high missing percentages were removed:

- size

- VIN

Categorical missing values were filled using:

- `"Unknown"`

Rows with unrealistic values were filtered:

- price outside $500–$100,000

- odometer outside 100–300,000 miles

---

# Feature Engineering

Several engineered features were created:

| Feature | Description |

|---|---|

| `car_age` | Vehicle age derived from year |

| `odometer_per_year` | Annualized mileage usage |

| `condition_score` | Ordinal mapping of condition |

| `cylinders_numeric` | Numeric extraction from cylinder text |

| `cylinders_missing` | Missing-cylinder indicator |

| `is_luxury` | Luxury manufacturer indicator |

| `log_price` | Log-transformed target variable |

---

# Exploratory Data Analysis (EDA)

Key findings from EDA:

- Vehicle price distributions were highly skewed and benefited significantly from log transformation.

- Vehicle age strongly negatively correlated with price.

- Mileage usage intensity (`odometer_per_year`) was more informative than raw odometer readings.

- Manufacturer and title status showed strong pricing influence.

- Nonlinear pricing behavior was clearly visible in scatter plots and residual analysis.

---

# Modeling Approaches

The following modeling techniques were explored:

## 1. Linear Regression

Baseline regression model.

## 2. Polynomial Regression

Polynomial feature expansion:

- Degree 2

- Degree 4

Polynomial expansion significantly improved model performance, confirming nonlinear pricing relationships.

## 3. Ridge Regression

Used to stabilize coefficients and reduce multicollinearity effects in polynomial feature space.

## 4. Lasso Regression

Used for:

- regularization,

- sparsity,

- and implicit feature selection.

## 5. Sequential Feature Selection

Evaluated the predictive power of engineered numeric features.

## 6. Hyperparameter Optimization

GridSearchCV was used to optimize:

- Ridge alpha

- Lasso alpha

---

# Final Selected Model

## Degree-4 Polynomial Ridge Regression

### Final Performance

| Metric | Train | Test |

|---|---|---|

| RMSE | ~0.50 | ~0.50 |

| MAE | ~0.32 | ~0.32 |

| R² | ~0.69 | ~0.69 |

### Why This Model Was Selected

This model provided:

- the best predictive performance,

- strong generalization,

- minimal overfitting,

- and stable coefficient behavior.

---

# Key Business Findings

## Major Pricing Drivers

Top factors influencing used car prices included:

- manufacturer/brand,

- vehicle age,

- title status,

- fuel type,

- luxury classification,

- and mileage usage intensity.

## Nonlinear Depreciation

Vehicle depreciation patterns were strongly nonlinear, especially across:

- newer vehicles,

- luxury vehicles,

- and high-mileage segments.

## Inventory Insights

Dealers may improve profitability by:

- optimizing brand mix,

- prioritizing low-usage vehicles,

- monitoring title status carefully,

- and adapting inventory toward changing EV demand.