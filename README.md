# Overview of the Governor’s Challenge BoC BVAR Project

This project is a comprehensive forecasting and policy analysis framework designed to replicate and extend the Bank of Canada’s style of macroeconomic modeling. At its core, the model is a **Bayesian Vector Autoregression (BVAR)**, customized to capture the complex interactions between Canadian inflation, monetary policy, financial markets, and external global shocks. The goal is to simulate how the Bank of Canada might form forecasts and set policy, while also experimenting with improvements in design and presentation.

## Objectives
1. **Forecasting:** To generate reliable projections of Canadian CPI inflation, GDP growth, and policy interest rates.
2. **Policy Simulation:** To evaluate different monetary policy responses—especially interest rate changes—and their effect on inflation and the broader economy.
3. **Communication:** To create tools (charts, fan charts, scenario paths) that communicate uncertainty in a way similar to the Bank of Canada’s Monetary Policy Report (MPR).

## Data Foundation
The project integrates a **wide set of macro-financial variables** used by the Bank of Canada and in academic work:
- **Domestic variables:** CPI and CPI components, output gap, overnight rate (policy rate), 5-year Government of Canada bond yield, labour productivity, wages (AWE), unit labour costs, Business Outlook Survey indicators, commodity price indices (BCPI).
- **External variables:** U.S. Federal Funds Rate, foreign demand measures (FAM-IO index), global supply chain indices (GSCPI).
- **Structural markers:** Crisis dummies (2008 financial crisis, 2020 pandemic) and regime-shift controls to improve stability.

This mix allows the model to capture both domestic policy drivers and external shocks that matter to a small open economy like Canada.

## Model Design
1. **Bayesian VAR Framework:** VAR extended with Bayesian shrinkage priors (Minnesota and variants) to keep forecasts stable with many variables and avoid overfitting.
2. **Structural Features:**
   - Crisis dummies for regime shifts.
   - Exogenous blocks for foreign variables (treated as external drivers).
   - Priors tuned to mimic the Bank of Canada’s forecasting horizon (1–2 years for CPI/policy rate).
3. **Forecast Horizon:** 8 to 12 quarters ahead, focusing on the Bank’s 2% inflation target horizon.
4. **Stability Tools:** Unit root testing, break detection (ADF, Zivot-Andrews), and robustness checks to guard against regime changes.

## Forecasting and Scenarios
- **Baseline Forecasts:** Central paths for inflation, GDP, and interest rates, consistent with historical trends and policy assumptions.
- **Fan Charts:** Uncertainty bands around forecasts, similar to Bank of Canada publications.
- **Scenario Analysis:** Counterfactual simulations (e.g., faster rate hikes, global demand collapse) to explore risks.

## Risks and Limitations
1. **Model stability & structural breaks.**
2. **Forecast-horizon reliability.**
3. **Specification & priors.**
4. **Interpretability.**
5. **Nonlinearity.**

## Outputs and Deliverables
- Forecast tables for CPI, GDP, and interest rates.
- Fan charts for policy communication.
- Impulse-response functions (shock propagation).
- Scenario comparisons (baseline vs alternative).
- Documentation of assumptions and limitations.

## Contribution
Combines **academic econometrics, central bank practice, and practical policy simulation** to provide:
- A research tool for testing Canada’s inflation-targeting regime.
- A framework to compare policy responses to shocks.
- A pedagogical tool for central-bank style communication of uncertainty.

By integrating Canadian data, Bayesian methods, and central-bank style communication, the project serves as both a forecasting system and a policy learning tool.


