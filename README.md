# retail-demand-inventory-planner
Retail sales forecasting and inventory planning project
# Retail Demand Forecasting

A time-series forecasting project that predicts daily sales for different items across 10 stores.

## Project goal

Use historical sales data to forecast future demand for 50 items across 10 stores.

## Dataset

This project uses the [Kaggle Store Item Demand Forecasting dataset](https://www.kaggle.com/competitions/demand-forecasting-kernels-only/data).

- Training data: daily sales from 2013-01-01 to 2017-12-31
- Stores: 10
- Items: 50
- Forecast period: 2018-01-01 to 2018-03-31

Download the competition files from Kaggle and place them in the `data/` folder.

## Method

1. Checked the data for missing values and duplicate rows.
2. Explored sales trends and average sales by weekday.
3. Created date features: weekday and month.
4. Created sales-history features: `lag_7` and `rolling_mean_7`.
5. Used the last 14 days of training data for time-based validation.
6. Compared an `XGBoost Regressor` with a `lag_7` baseline.
7. Generated predictions for Kaggle's 45,000 test rows.

## Validation results

| Model | MAE |
|---|---:|
| Lag-7 baseline | 7.34 |
| XGBoost | 6.02 |

XGBoost reduced validation MAE by about 18% compared with the baseline.

## Main files

- `notebook/01_exploration.ipynb` — data exploration, features, model training, and predictions
- `submission.csv` — predicted sales for the Kaggle test data

## Tools

Python, pandas, NumPy, Matplotlib, scikit-learn, and XGBoost