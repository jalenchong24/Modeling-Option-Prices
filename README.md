# Modelling Option Prices Using Black-Scholes and Machine Learning

## Overview
This project explores how machine learning models compare to the traditional Black-Scholes model in predicting option prices.  
It was completed as part of **DATASCI 3ML3 (Machine Learning)** at McMaster University.

The goal was to evaluate whether modern ML techniques can replicate or improve on the Black-Scholes model using real market data,  
and to interpret the models using SHAP values to understand which features most influenced predictions.

---

## Methods
### 1. Data Collection
- Retrieved options data from the **Yahoo Finance API (`yfinance`)**.
- Engineered key financial features:
  - **Moneyness** and **log-moneyness**
  - **Time to expiry** (in years)
  - **Risk-free rate** (fixed at 2%)
  - **Mid-price** (average of bid and ask)

### 2. Models Used
- **Black-Scholes formula** (theoretical baseline)
- **Neural Network** (Keras)
- **XGBoost Regressor** (tree-based model)

Each model was evaluated using **RMSE** and **MAE** metrics to compare predictive accuracy.

### 3. Explainability
- Used **SHAP (Shapley Additive exPlanations)** to interpret feature importance.
- Created **beeswarm** and **bar plots** to visualize which features most influenced predictions.

---

## Results
| Model | RMSE | MAE | Notes |
|--------|------|------|-------|
| Black-Scholes | **0.4723** | **0.2818** | Most accurate overall |
| Neural Network | 2.7230 | 2.4001 | Captured non-linear relationships |
| XGBoost | 12.3782 | 7.8650 | Underperformed due to small dataset size |

- The **Black-Scholes model** maintained the lowest error, showing its continued strength in smaller, well-structured datasets.  
- The **Neural Network** offered stronger interpretability through SHAP, aligning with financial intuition.  
- The **XGBoost model** struggled due to limited data size, highlighting its dependence on larger training samples.

---

## Key Insights
- Machine learning can complement traditional finance models by revealing non-linear interactions and feature effects.  
- SHAP analysis showed **implied volatility** and **strike price** as key drivers of model predictions.  
- Despite its age, the **Black-Scholes formula** remains robust for small-sample financial modeling.

---

## Tools & Libraries
`Python`, `Pandas`, `Scikit-learn`, `XGBoost`, `Keras`, `yfinance`, `SHAP`, `Matplotlib`

---

## Author
**Jalen Chong**  
McMaster University — Actuarial and Financial Math  
📧 www.linkedin.com/in/jalen-chong




