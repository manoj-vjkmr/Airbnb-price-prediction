# Benchmarking Linear vs. Ensemble Regression Architectures: A Comparative Study

This project presents a rigorous empirical study on predicting real-estate pricing using the Chicago Airbnb dataset. By evaluating a spectrum of models ranging from classical linear regression to state-of-the-art gradient boosting ensembles, this study investigates the fundamental drivers of rental pricing and the effectiveness of different regression architectures in handling non-linear market data.

## Overview
Real-estate pricing is a high-dimensional, non-linear problem. This study compares the performance and interpretability of two distinct machine learning paradigms:
1. **Interpretable Linear Baselines:** OLS and Ridge Regression to quantify directional feature influence.
2. **High-Performance Ensemble Models:** Random Forest, XGBoost, LightGBM, and CatBoost to capture non-linear market patterns.

## Methodology

### 1. Statistical Preprocessing
To ensure data integrity for regression:
* **Normalization:** Box-Cox power transformations for skewed distributions.
* **Dimensionality:** Handling multicollinearity and dropping redundant features.
* **Inference:** ANOVA and Tukey’s HSD post-hoc tests to establish statistical significance in neighborhood and temporal price variances.

### 2. Comparative Model Benchmarking
We evaluated model performance based on Mean Squared Error (MSE), with the square root ($\sqrt{MSE}$) representing the prediction error in dollars.

| Model Category | Algorithms Implemented | Primary Goal |
| :--- | :--- | :--- |
| **Linear** | Linear Regression, Ridge | Coefficient interpretability & directional influence |
| **Ensemble** | Random Forest, XGBoost, CatBoost, LightGBM | Capturing non-linear relationships |
| **Meta** | Stacking | Minimizing residual error via model averaging |

## Findings & Key Insights

### Interpretability vs. Predictive Accuracy
* **Linear Analysis:** Ridge regression successfully penalized multicollinearity, allowing us to isolate the influence of specific amenities (e.g., "terrace" and "kitchenette" positively influencing price).
* **Ensemble Performance:** Random Forest consistently outperformed linear baselines, confirming that Airbnb pricing models are fundamentally non-linear. The final "Stack" of ensemble models provided the most robust predictive performance.

### Statistical Significance
Using ANOVA tests, we validated that price differences between neighborhoods and across months/weekdays are statistically significant ($p < 0.0001$), supporting the validity of our seasonality and market-segmentation analysis.

### Feature Importance
The study identified the "Number of Bathrooms," "Bedrooms," and "Cleaning Fees" as the strongest predictors of price. Interestingly, a negative correlation was observed between the "Number of Reviews" and price, suggesting that high-frequency listings represent the economy tier of the market.
