# Electricity Demand Forecasting (Predictive Paradox Task)

 Overview:

The goal of this project is to predict the next hour’s electricity demand using historical demand data along with weather and economic indicators. This is important because accurate demand forecasting helps in maintaining grid stability and avoiding over/under production.

Approach:

 Data Preparation

* Cleaned the demand dataset by fixing timestamps and removing duplicate entries
* Handled missing values wherever required
* Observed some abnormal spikes in demand and treated them so that they don’t mislead the model

 Feature Engineering

* Lag features (previous hours demand) to give recent context
* Rolling averages (like 24-hour mean) to capture daily patterns
* Time-based features such as hour of day, day of week, etc.

Weather data was merged on an hourly basis.
Economic data was annual, so it was mapped to each year and merged accordingly.

 Model

I used XGBoost as the main model since it works well with tabular data and handles non-linear relationships effectively.

 Training Strategy

The data was split chronologically to avoid any leakage:

* Training set: past data
* Test set: future data

Final performance:

* **MAPE ≈ 2.47%**

Key Observations:

* Recent demand (lag features) turned out to be the most important factor
* Daily patterns were captured well using rolling features
* Weather had some influence, but not as strong as past demand

 Final Thoughts

This project helped in understanding how to handle time-series problems using non-sequential models by carefully engineering features and maintaining proper validation.
