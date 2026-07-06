Inflation forecasting sits at the heart of monetary policy decisions. 
This project tests whether modern machine learning can outperform the 
classical economic models that central banks have relied on for decades.

# US CPI Inflation Forecasting

Comparing classical econometric models (Phillips Curve OLS, ARIMA) 
against machine learning (XGBoost) for forecasting US CPI inflation.

Data source: FRED API (Federal Reserve Economic Data)

# US CPI Inflation Forecasting: Econometric vs. Machine Learning Models

## Overview
Comparison of classical econometric models against machine learning for 
forecasting US CPI inflation, using 20+ years of monthly macroeconomic 
data from the FRED API (Federal Reserve Economic Data).

## What I Found
Phillips Curve OLS outperformed XGBoost (RMSE 0.12 vs 0.43), demonstrating 
that economic theory outperforms purely data-driven approaches on 
macroeconomic forecasting tasks.

## Models Compared
| Model | RMSE | MAE |
| Naive Baseline | 0.3659 | 0.2563 |
| Phillips Curve OLS | 0.1192 | 0.0934 |
| ARIMA | 3.9506 | 3.8480 |
| XGBoost | 0.4275 | 0.3071 |

## Features Used
- CPI Inflation (target)
- Unemployment Rate (Phillips Curve)
- Federal Funds Rate (Taylor Rule)
- 10yr-2yr Yield Spread (recession signal)
- M2 Money Supply Growth (quantity theory)
- Oil Prices / WTI (supply shock)
- Consumer Sentiment (expectations)

## Feature Engineering
- Lag features (1, 3, 6 months) for all key variables
- Rolling averages (3m, 6m) for inflation and unemployment
- Theory-driven features: Phillips Gap, Real Interest Rate

## Results
[Model Comparison](model_comparison.png)
[Feature Importance](feature_importance.png)

## Tech Stack
Python · FRED API · XGBoost · scikit-learn · statsmodels · pandas · matplotlib

## How to Run
1. Clone the repo
2. Install dependencies: pip install -r requirements.txt
3. Add your FRED API key in the notebook
4. Run notebooks/main.ipynb top to bottom


## Where the Models Failed
The 2021–22 inflation surge broke every model. No historical pattern 
could predict a post-pandemic supply shock of that scale. This was the 
most honest finding of the project — knowing where a model fails is as 
important as knowing where it works.

## About
Built as part of my interest in applying data science to macroeconomic 
problems. I study Economics and wanted to connect my Macroeconomics coursework directly to a real ML project.