# Weather Data Analysis and Forecasting

## Overview

This project provides tools for analyzing weather data and forecasting temperature by country. It includes functionalities for:
- **Data Cleaning:** Cleaning the data based on the numeric and categorical data.
- **Handling Ouliers:** This process includes handling of outliers based on the IQR detection.
- **Data Normalization:** Standardizing numeric weather measurements to ensure consistent scaling.
- **Anomaly Detection:** Identifying unusual or extreme weather events through rolling calculations and z-scores.
- **Temperature Forecasting:** Predicting daily temperature using multiple models, including SARIMA, Linear Regression, Random Forest, XGBoost, and an ensemble approach.

## Features

### Data Normalization
- Standardizes key numeric columns (e.g., temperature, wind speed, and air quality indices) so that each has a mean of 0 and a standard deviation of 1.
- Enhances the performance of forecasting models by ensuring that all input features are on a comparable scale.

### Anomaly Detection
- Detects anomalies for each country across multiple numeric features.
- Uses a 7-day centered rolling window to calculate a rolling mean and standard deviation.
- Computes z-scores to flag days where the absolute deviation exceeds a predetermined threshold (typically, a z-score greater than 3).
- Helps identify extreme weather events or potential data quality issues.

### Temperature Forecasting
- Forecasts daily temperature for a specific country.
- Implements multiple forecasting models:
  - **SARIMA:** Captures time-series trends using seasonal autoregressive integrated moving average with exogenous variables.
  - **Linear Regression:** Provides a straightforward regression-based forecast.
  - **Random Forest:** Uses an ensemble of decision trees to improve prediction robustness.
  - **XGBoost:** Leverages gradient boosting techniques optimized for regression.
  - **Ensemble Method:** Averages predictions from Linear Regression, Random Forest, and XGBoost to yield more robust forecasts.
- Evaluates model performance using metrics such as Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), Mean Absolute Percentage Error (MAPE), and the coefficient of determination (\(R^2\)).

## Rolling Calculations and Z-Score Formulas

- **Rolling Mean:** Calculated as the average of values within a 7-day window centered on each day.
- **Rolling Standard Deviation:** Measures the variability of values within the same 7-day window.
- **Z-Score:** Determines how many standard deviations a day's value deviates from the rolling mean. Values beyond an absolute z-score of 3 are flagged as anomalies.

## Installation

To set up the project:
1. Clone the repository.
2. Create and activate a virtual environment.
3. Install the required packages as specified in the project's dependency list.

## Dependencies

Key libraries and tools include:
- Python 3.7 or higher
- Pandas and NumPy for data manipulation
- Matplotlib for data visualization
- Scikit-learn for data normalization and evaluation metrics
- Statsmodels for SARIMA modeling
- XGBoost for gradient boosting

## Usage

- **Data Normalization:** Load your weather dataset and apply the normalization process to standardize numeric features.
- **Anomaly Detection:** Execute the anomaly detection process to review extreme weather events by country.
- **Temperature Forecasting:** Select a country to forecast daily temperature using the available models. Optionally, visualize the forecasted results alongside actual data to assess model performance.
