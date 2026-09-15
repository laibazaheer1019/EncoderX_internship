Internship Second Week Task :
# Warehouse & Retail Sales Forecasting

End-to-end time series forecasting project on monthly warehouse and retail sales data — covering data cleaning, feature engineering, model training, evaluation, and business insights.

## 📊 Project Overview

This project builds and compares two regression models (Linear Regression and Random Forest) to forecast monthly retail sales using historical sales patterns, lag features, rolling averages, and seasonal indicators.

**Full write-up:** see [`Retail_Sales_Forecasting_Report.pdf`](./Retail_Sales_Forecasting_Report.pdf) for the complete project report.

## 🗂️ Dataset

- **Source file:** `Warehouse and Retail Sales.csv`
- **Records:** 341,037 item-level transactions
- **Columns:** `YEAR`, `MONTH`, `SUPPLIER`, `ITEM CODE`, `ITEM DESCRIPTION`, `ITEM TYPE`, `RETAIL SALES`, `RETAIL TRANSFERS`, `WAREHOUSE SALES`
- **Years covered:** 2017–2026

## ⚙️ Pipeline

1. **Data Preparation**
   - Coerce sales columns to numeric, handle invalid/missing values
   - Fill missing `SUPPLIER` / `ITEM TYPE` with `"Unknown"`, missing sales with `0`
   - Build a proper `DATE` column and sort chronologically
   - IQR-based outlier detection on sales columns
   - Aggregate to a monthly retail sales time series

2. **Feature Engineering**
   - Calendar features: `MONTH`, `QUARTER`, `YEAR`, `DAY_OF_WEEK`, `SEASON`
   - Lag features: `LAG_1`, `LAG_2`, `LAG_3`
   - Rolling averages: `ROLLING_MEAN_3`, `ROLLING_MEAN_6`
   - Chronological train/test split (80/20)

3. **Modeling**
   - Linear Regression (baseline)
   - Random Forest Regressor (100 estimators)

4. **Evaluation**
   - Metrics: MAE, RMSE, R² Score
   - Actual vs. predicted visualization

5. **Business Insights**
   - Seasonal sales patterns
   - Inventory and marketing recommendations

## 📈 Results

| Model              | MAE       | RMSE      | R² Score |
|---------------------|-----------|-----------|----------|
| Linear Regression    | 13,973.30 | 17,858.01 | -0.977   |
| **Random Forest**    | **8,681.32** | **11,575.74** | **0.169** |

Random Forest outperformed Linear Regression on all metrics, but overall model accuracy was limited by a small effective training window and missing months in the aggregated data — see [Limitations](#-known-limitations) below.

## 🔑 Key Findings

- **Seasonality:** December shows the highest average retail sales (holiday peak); January the lowest (post-holiday slowdown).
- **Predictive features:** Lagged sales and rolling averages carry the most useful signal for near-term forecasting.
- **Model choice:** Random Forest captures non-linear seasonal effects better than Linear Regression on this dataset.

## ⚠️ Known Limitations

- The modeling window was restricted to dates before `2021-01-01`, discarding available 2021–2026 data and leaving only 18 usable rows after feature engineering.
- 83 calendar months are missing from the aggregated series, which distorts lag/rolling features.
- The test set contains only 4 observations, making evaluation metrics statistically fragile.
- Outliers were flagged (IQR method) but not removed prior to aggregation.

## 🚀 Next Steps

- [ ] Remove the 2021 date filter and use the full 2017–2026 history
- [ ] Reindex the monthly series to fill calendar gaps before computing lag/rolling features
- [ ] Treat/cap outliers before aggregation
- [ ] Add a dedicated time-series model (e.g., SARIMA, Prophet) for comparison
- [ ] Set up a recurring pipeline to refresh forecasts as new data arrives

## 🛠️ Tech Stack

- Python
- pandas, numpy
- scikit-learn (`LinearRegression`, `RandomForestRegressor`)
- matplotlib

## 📁 Output Files

| File | Description |
|------|--------------|
| `cleaned_warehouse_retail_sales.csv` | Full cleaned dataset |
| `feature_engineered_sales.csv` | Dataset with engineered features |
| `train_data.csv` / `test_data.csv` | Chronological train/test split |
| `model_predictions.csv` | Actual vs. predicted sales |
| `model_comparison.csv` / `model_evaluation_results.csv` | Model performance metrics |
| `monthly_retail_sales.png` | Actual vs. predicted sales chart |

## ▶️ Usage

```bash
pip install pandas numpy scikit-learn matplotlib
python sales_forecasting.py
```

## 📄 License

Add your preferred license here (e.g., MIT).
