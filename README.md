# 📊 Revenue Forecasting with Regression Models

This repository contains a structured data science project focused on **forecasting corporate financial statements** using econometric and machine learning techniques.  
The work is based on a panel of U.S. companies and applies a progressive modeling pipeline, from simple baselines to robust regularized regressions.

---

## 🎯 Objectives

The project aims to:
- Build and compare models to **predict future revenues** from historical financial data.  
- Evaluate the effectiveness of linear regression, regularization techniques (Ridge), and robust methods.  
- Apply rigorous validation (rolling cross-validation) to assess predictive performance.  
- Provide interpretable insights into model selection and the trade-offs between bias, variance, and robustness.

---

## 🗂 Repository Structure

── 01_baseline_OLS.ipynb # Baseline model using Ordinary Least Squares
── 02_ridge_tuning.ipynb # Ridge regression with grid search for alpha tuning
── 03_robust_regression.ipynb # Robust approaches (Ridge + Huber) and diagnostic checks
── 04_final_model_USA.ipynb # Final model with rolling cross-validation and metrics

- **Data**: Proprietary financial statement data (not included in this repository for confidentiality).  
- **Code**: Python notebooks with clear, reproducible steps.  
- **Pipeline**: From exploratory analysis and feature engineering (lags, log-transformations) to final validation.  

---

## ⚙️ Methodology

1. **Data Preparation**  
   - Cleaning and normalization of financial statement data.  
   - Feature engineering with lags of revenues, EBITDA, and net income.  
   - Log-transformations to stabilize variance and improve model fit.  

2. **Model Development**  
   - **Baseline OLS**: Simple benchmark to test linear predictability.  
   - **Ridge Regression**: Introduction of L2 regularization to mitigate multicollinearity.  
   - **Hyperparameter Tuning**: Grid search for the optimal alpha parameter.  
   - **Robust Regression**: Use of Huber loss to handle potential outliers.  

3. **Validation**  
   - Rolling cross-validation across years.  
   - Performance metrics: **MAE** (Mean Absolute Error) and **MAPE** (Mean Absolute Percentage Error).  
   - Benchmark against a **naïve model** (last year’s revenue as forecast).  

---

## 📈 Results

- The **baseline OLS** provided a first benchmark, highlighting issues of overfitting and collinearity.  
- **Ridge regression** significantly improved predictive stability, with lower variance and improved generalization.  
- **Huber regression** confirmed robustness against outliers (e.g., firms with anomalous revenue growth).  
- The **final model**, validated with rolling CV, achieved:  
  - **MAE < 600** (average across firms)  
  - **MAPE < 1%**, far outperforming the naïve benchmark (~3.3%).  

These results demonstrate that even relatively simple regularized models can effectively forecast firm-level revenues over short horizons, provided that features are engineered carefully and validation is rigorous.

---

## 📌 Key Takeaways

- **Iterative modeling** is crucial: the path from OLS to Ridge/Huber shows the importance of testing alternatives.  
- **Regularization** effectively addresses multicollinearity, which is typical in financial statement data.  
- **Robustness checks** (Huber loss, VIF analysis) enhance credibility of results.  
- **Validation design** matters as much as the model: rolling CV mimics real forecasting more realistically than random splits.  

