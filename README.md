# Project Overview 📊

A **Bayesian Vector Autoregression (BVAR)** model for Canadian inflation forecasting and optimal monetary policy path optimization. This project replicates Bank of Canada-style macroeconomic modeling to generate reliable CPI forecasts and recommend optimal interest rate paths that maintain the 2% inflation target.

## Objective 🎯

Develop a comprehensive forecasting framework that:
- **Forecasts** Canadian CPI inflation 8 quarters ahead with uncertainty bands
- **Simulates** policy responses to external shocks (trade wars, supply chain disruptions)
- **Optimizes** interest rate paths to maintain stable, low, and predictable inflation

## Project Steps 🔄

### 1. 📈 Data Collection
- **Statistics Canada (CANSIM)**: CPI, GDP, labour productivity, unemployment
- **Bank of Canada**: Overnight rates, Business Outlook Survey, commodity prices
- **External sources**: US Federal Funds Rate, global supply chain pressure index

### 2. 🧹 Data Cleaning (STATA)
- Quarterly aggregation and seasonal adjustment
- Crisis dummy variables (2008 financial crisis, 2020 pandemic)
- Stationarity testing and transformation (log-differences for growth rates)

### 3. 🤖 Forecasting Model (Python)
- **BVAR with Minnesota priors** for stable forecasting with many variables
- **Shock simulation** capability for external events (trade wars, supply disruptions)
- **Fan charts** showing 50% and 80% confidence intervals

### 4. ⚡ Interest Rate Optimization
- **Beam search algorithm** testing thousands of policy rate combinations
- **Multi-objective optimization**: stability, level, and predictability
- **Constraints**: ±50bp quarterly changes, 25bp increments

## Variables 📋

**Final Model Variables (9 total):**
- `Labour_Prod`: Labour productivity growth (q/q annualized)
- `CEER`: Canadian dollar exchange rate growth
- `GOC5Y`: 5-year Government of Canada bond yield growth
- `BOS`: Business Outlook Survey indicator
- `BCPI`: Bank of Canada commodity price index growth
- `CPI`: Consumer Price Index inflation (target variable)
- `Output_Gap`: Real GDP gap measure
- `GSCPI`: Global Supply Chain Pressure Index
- `Overnight_Rate`: Bank of Canada policy rate

## Model Design 🏗️

**Bayesian VAR Framework:**
- **Lags**: 4 quarters (optimal via testing)
- **Priors**: Minnesota-style shrinkage (φ=0.9, λ=0.2, θ=0.2)
- **Posterior**: Conjugate Normal-Inverse Wishart
- **Draws**: 2,000 posterior samples for uncertainty quantification

**Key Features:**
- **Stationarity**: All variables tested via Augmented Dickey-Fuller tests
- **Shock capability**: One-time additive innovations to any variable
- **Policy conditioning**: Exogenous interest rate paths for optimization
- **Robust evaluation**: Out-of-sample testing with RMSE/MAE metrics

## Results & Policy Recommendations 🎯

**Model Performance:**
- **RMSE**: 0.85-1.39 (excellent for 8-quarter forecasts)
- **Coverage**: 100% of actual CPI within 80% confidence bands
- **Shock response**: Accurately captures trade war effects (2018 tariffs)

**Optimal Policy Path (8 quarters):**
```
[3.0%, 2.5%, 2.0%, 1.5%, 1.0%, 1.5%, 2.0%, 1.5%]
```

**Key Metrics:**
- **Average CPI**: 2.02% (perfectly on target)
- **Stability**: Low volatility in forecast path
- **Predictability**: Narrow confidence intervals

## Conclusion 💡

The BVAR model successfully replicates Bank of Canada forecasting practices with:
- **High accuracy** in out-of-sample CPI predictions
- **Robust shock handling** for external economic disruptions  
- **Optimal policy guidance** maintaining the 2% inflation target

The recommended gradual easing followed by measured tightening provides the optimal balance of price stability and economic predictability for Canadian monetary policy.



