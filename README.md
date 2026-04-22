# Chocolate Sales Forecasting

## Overview
This project forecasts **next month chocolate sales value** using a **pure forward forecasting** approach. The raw Excel data was transformed from a report-style format into a clean monthly modeling dataset, and machine learning models were used to predict future sales.

## Objective
The goal is to predict **next month sales (`sales_value_lakhs`)** for each segment using only historically available information, making the model realistic for business forecasting.

## Workflow
- cleaned and reshaped raw Excel data
- treated `ERR / Err / err` as missing values
- created monthly segment-level dataset
- handled outliers using IQR capping and outlier flags
- engineered lag, rolling, growth, and calendar features
- built a pure forward forecasting setup
- compared Random Forest and XGBoost models

## Models and Results

### Random Forest
- MAE: `209.15`
- RMSE: `368.28`
- R2: `0.9927`
- MAPE: `9.00%`

### XGBoost
- MAE: `167.05`
- RMSE: `288.28`
- R2: `0.9955`
- MAPE: `7.07%`

## Final Model
**XGBoost Regressor** was selected as the final model because it achieved the best forecasting performance.

## Key Predictors
The most important features were:
- `sales_lag_1`
- `sales_roll_mean_3`
- `volume_lag_1`
- `volume_roll_mean_3`

## Files
- `ALL CHOCOLATE.xlsx` : raw dataset
- `Chocolate Sales Forecasting Using Pure Forward Predictive Modeling.ipynb` : notebook
- `chocolate_cleaned_final.csv` : cleaned dataset
- `model_comparison.csv` : model comparison
- `xgboost_sales_forecast_results.csv` : final predictions

## Tools Used
- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib

## Conclusion
The project successfully built a realistic **pure forward sales forecasting model** and showed that XGBoost can predict next month chocolate sales with strong accuracy.
