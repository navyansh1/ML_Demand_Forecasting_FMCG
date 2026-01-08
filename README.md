# FMCG Demand Forecasting

> A practical approach to demand forecasting for Fast-Moving Consumer Goods using statistical and machine learning techniques

## Project Overview 📊
 [View Notebook (Fast Web View) 📘](https://htmtopdf.herokuapp.com/ipynbviewer/temp/b2d7ab309f22b4efa96a0d543a236337/Demand_Forecasting_FMCG.html?t=1767900450271)


This project demonstrates a structured methodology for demand forecasting in the FMCG industry. Rather than complex black-box models, the focus is on interpretable, actionable insights that drive business decisions.

Also the dataset used here is a higly messy in the date column, so we will fix that as well.


## Why Demand Forecasting Matters 🎯

In FMCG, the balance between too much and too little inventory can make or break profitability:

- **Too little stock** = Lost sales, disappointed customers, market share erosion
- **Too much stock** = Capital tied up, storage costs, wastage from expiry

Accurate forecasting enables:

- ✅ Optimized inventory levels
- ✅ Better production planning
- ✅ Reduced stockouts and overstocking
- ✅ Improved customer satisfaction
- ✅ Cost savings across the supply chain

## The Approach🔍

### 1. **Understand the Data**

Before forecasting, we need to know what we're working with:

- What's the sales pattern? Seasonal? Trending?
- Which products drive revenue?
- Where are the outliers and anomalies?

**Why**: You can't forecast what you don't understand. Data exploration reveals the story behind the numbers.

### 2. **Segment Products (ABC-XYZ Analysis)**

Not all products are created equal:

- **ABC**: Revenue impact (A = high, B = medium, C = low)
- **XYZ**: Demand variability (X = stable, Y = moderate, Z = volatile)

**Why**: Different products need different strategies. High-value stable products (AX) need consistent stock. Low-value volatile products (CZ) might need make-to-order approaches.

### 3. **Test Multiple Forecasting Methods**

We compare three approaches:

- **Moving Averages**: Simple, intuitive, good baseline
- **Exponential Smoothing**: Weighs recent data more heavily
- **ARIMA**: Captures trends and seasonality mathematically
- **Machine Learning**: Uses multiple features for complex patterns

**Why**: No single method works for all scenarios. Fashion items need responsive methods (high alpha, short windows), while staples need stable methods (low alpha, long windows).

### 4. **Feature Engineering for ML Models**

When using machine learning, we create:

- **Time features**: Month, quarter, day of week
- **Lag features**: Previous periods' demand
- **Rolling statistics**: Moving averages and standard deviations

**Why**: ML models need to understand temporal patterns. Lag features capture "if we sold X last week, we'll likely sell similar this week."

### 5. **Compare Forecast Horizons**

Weekly vs Monthly forecasting serves different purposes:

- **Weekly**: Operational decisions (inventory replenishment, staff scheduling)
- **Monthly**: Strategic decisions (production capacity, budget allocation)

**Why**: Weekly forecasts capture short-term fluctuations but are noisier. Monthly forecasts are more stable and accurate for planning.

### 6. **Measure What Matters**

We track accuracy using:

- **MAE** (Mean Absolute Error): Average prediction error in actual units
- **RMSE** (Root Mean Squared Error): Penalizes large errors more
- **MAPE** (Mean Absolute Percentage Error): Error as a percentage

**Why**: Technical metrics (MAE) need to translate to business impact (cost of error, lost revenue).

## Key Insights 📈

### 1. **Aggregation Improves Accuracy**

Category-level forecasts are often more accurate than product-level forecasts because aggregation smooths out individual product volatility.

### 2. **Lag Features are King**

In ML models, past demand (lag features) is consistently the most important predictor. This validates the time series approach.

### 3. **Simple Can Outperform Complex**

ARIMA often outperforms complex ML models for stable products. The best model isn't always the most sophisticated—it's the one that fits your data.

### 4. **Context is Critical**

A 10% forecast error might be excellent for volatile fashion items but unacceptable for staple goods. Numbers mean nothing without business context.

## Tools & Libraries 🛠️

```python
# Data manipulation
pandas, numpy

# Visualization
matplotlib

# Statistical models
statsmodels (ARIMA, Exponential Smoothing)

# Machine Learning
scikit-learn (Random Forest)
xgboost
```

## Files in This Repository 📁

- `Demand_Forecasting_FMCG.ipynb` - Main analysis notebook (streamlined and commented)
- `sample.xlsx` - Sales data (product, date, volume, location)
- `README.md` - This file

## How to Use This Code 🚀

This notebook is designed to be reusable for similar FMCG forecasting projects:

1. **Replace the data source** with your sales data
2. **Ensure columns** include: Product ID, Date, Sales Volume, Category
3. **Run sections sequentially** - each builds on the previous
4. **Adjust parameters** based on your data granularity (daily/weekly/monthly)
5. **Interpret results** in your business context

## Lessons Learned 💡

- **ABC-XYZ segmentation** provided actionable categories for inventory strategy
- **ARIMA** struck a good balance between accuracy and interpretability
- **Visualizations** made patterns immediately obvious to stakeholders

## Business Takeaways 🎓

1. **Data-driven ≠ Data-dictated**: Forecasts inform decisions, but business judgment is still essential. If a model predicts 20% growth but you know a competitor just launched, adjust accordingly.
2. **Forecast accuracy is a journey**: The first model won't be perfect. Set up feedback loops, monitor accuracy, and continuously improve.
3. **Communicate in business language**: "MAE of 2,500" means nothing to executives. "We'll prevent 15% of stockouts, saving $150K monthly" does.
4. **Different products, different strategies**: One-size-fits-all doesn't work. Segment intelligently and apply appropriate methods.
5. **Start simple, add complexity**: Begin with moving averages to set a baseline. Add complexity only if it meaningfully improves results.



