# Instacart Market Basket Analysis & Prediction

## Project Overview

This project explores frequent pattern mining and predictive analytics using the **Instacart Market Basket Analysis dataset** from Kaggle. The dataset contains over 3 million grocery orders from more than 200,000 users. Through statistical analysis, association rule mining, and machine learning models, we uncover customer purchase behaviors, product demand trends, and predictive insights for order sizes.

## Authors

- **Jittapatana (Patrick) Prayoonpruk**
- **Nexaly Orellana**

## Objectives

- Perform exploratory data analysis to uncover trends and distributions.
- Use frequent pattern mining (Apriori algorithm) to discover strong associations between products and departments.
- Predict order size using regression models.
- Forecast product demand using ARIMA time series models.

---

## Dataset

**Source:** [Instacart Market Basket Analysis on Kaggle](https://www.kaggle.com/c/instacart-market-basket-analysis)

Key files used:
- `orders.csv`
- `products.csv`
- `order_products__prior.csv`
- `departments.csv`
- `aisles.csv`

---

## Key Analyses

### 📊 Statistical Insights

- **Reorder Rate by Department:** High in `dairy eggs` (~70%), low in `personal care`.
- **Items Sold by Department:** `Produce` leads, while `bulk` has the lowest sales.
- **Order Volume by Hour:** Peaks from 10AM–4PM; insights useful for staffing and incentives.
- **Popular Products:** Top 10 items were all consumables, led by bananas.
- **Order Size Distribution:** Most orders contain 5 or fewer items.

### 🔍 Frequent Pattern Mining

- **Algorithms:** Apriori with thresholds:
  - Min Support: 0.005
  - Confidence: >0.3
  - Lift: >1.5
- **Insights:**
  - Strong intra-departmental associations (e.g., produce ↔ produce, frozen).
  - Aisle-level patterns show fresh fruits frequently paired with packaged and frozen items.

---

## 🧠 Predictive Modeling

### 1. **Order Size Prediction** (Linear Regression)
- **Features:** Order number, time since last order, user order average, order day/hour.
- **Tools:** `statsmodels`, `scikit-learn`
- **Challenges:** Overfitting observed (R² = 1), residuals not normally distributed.

### 2. **Product Demand Forecasting** (ARIMA)
- **Model:** ARIMA (2,1,1) for time series demand
- **Metric:** MAPE = 3.6%
- **Recommendation:** Incorporate exogenous variables and explore non-linear models (e.g., Random Forest, Gradient Boosting).

---

## Technologies Used

- **Python**: pandas, numpy, matplotlib, seaborn, scikit-learn, statsmodels
- **Jupyter Notebook**: For exploratory analysis and modeling
- **ARIMA Modeling**: `statsmodels.tsa.arima`
