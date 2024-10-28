# Public Transport Passenger Journey Forecasting

This project aims to analyze and predict daily public transport passenger journeys across different service types using time series forecasting techniques. The dataset includes daily records of passenger journeys categorized by various routes and services.

## Dataset Overview

The dataset contains daily records of public transport passenger journeys by service type, such as **Local Route**, **Long Distance**, etc. The key features are:
- **Date**: The date of each recorded journey.
- **Local Route**: The number of passengers on local transport routes.

### Business Insight

The goal of this analysis is to provide insights into:
1. **Historical Patterns**: Understanding fluctuations in daily passenger journeys.
2. **Seasonality**: Identifying seasonal patterns that impact the demand for public transport.
3. **Future Trends**: Predicting future passenger journeys to assist in optimizing transportation services.

## Predictive Insights

To achieve this, we used two time series forecasting models:
1. **ARIMA (AutoRegressive Integrated Moving Average)**: A statistical model suited for univariate time series data, primarily focusing on past observations to forecast future values.
2. **Prophet**: A model developed by Facebook, designed for time series with daily observations that accounts for trends and seasonality, making it robust for forecasting.

### Modeling and Forecasting Steps:
- **Preprocessing**: The dataset is cleaned, and missing values are filled using forward fill.
- **ARIMA Modeling**: ARIMA is applied to model the historical passenger data and forecast the number of passengers.
- **Prophet Modeling**: Prophet is used for both trend analysis and long-term future forecasting (e.g., 365 days).
- **Comparison**: Both ARIMA and Prophet results are compared to assess which model performs better in terms of predicting future values.

## Libraries Used

- **pandas**: For data manipulation and cleaning.
- **matplotlib**: For plotting time series and forecasting results.
- **statsmodels**: For ARIMA modeling, a traditional statistical method.
- **prophet**: For time series forecasting with a focus on capturing seasonality and trends.

## Visualizations and Plots

Several plots are used in the project for better insights:
1. **ARIMA Forecast vs Actuals**: Visual comparison between ARIMA forecasts and the actual passenger journey data.
2. **Prophet Forecast**: Visualization of the forecasted passenger journeys using Prophet, including confidence intervals.
3. **Trend and Seasonality Plots**: Prophet components, showing the underlying trend, weekly and yearly seasonality.
4. **ARIMA vs Prophet Comparison**: A plot comparing the performance of ARIMA and Prophet on the test set.

## Conclusion

This project demonstrates the application of time series forecasting for public transport data, helping stakeholders understand historical trends and predict future passenger journeys. The insights can assist in better planning of transportation services and resource allocation.

## Files Included

- `Task.ipynb`: The Jupyter notebook with the entire analysis and forecasting implementation.
- `Dataset.csv`: The CSV file containing the forecasted results.
- `Public_Transport_Passenger_Analysis.pdf`: Basic Insights and Idea from Dataset
- `requirements.txt`: Python libraries used
- `.Algorithm_Report.pdf`: Details of algorithm  used 


# Local Route Passenger Journey Forecast

This project uses Facebook's Prophet model to forecast the number of passenger journeys on a local route over the next 7 days.

## Output Explanation

After running the forecasting script, the output displays a table with forecasted values, including confidence intervals. Here’s a breakdown of each column:

| Date       | Predicted Passenger Journeys | Lower Bound | Upper Bound |
|------------|------------------------------|-------------|-------------|
| YYYY-MM-DD | Forecasted Value             | Minimum     | Maximum     |

### Column Descriptions

- **Date**: The forecasted date for passenger journeys.
  
- **Predicted Passenger Journeys**: The central forecast value (also known as `yhat` in Prophet), representing the expected number of passenger journeys for that date.

- **Lower Bound**: Known as `yhat_lower`, this value is the lower end of the forecast interval, providing a conservative estimate within the confidence interval (e.g., 80% or 95%).

- **Upper Bound**: Known as `yhat_upper`, this is the upper end of the forecast interval, offering an optimistic estimate within the same confidence interval.

### Example Output and Interpretation

| Date       | Predicted Passenger Journeys | Lower Bound | Upper Bound |
|------------|------------------------------|-------------|-------------|
| 2024-01-01 | 1500                         | 1300        | 1700        |

In this example:
- On **January 1, 2024**, the model predicts around **1500 passenger journeys**.
- The **actual number** could reasonably range between **1300** and **1700** due to data variability.

### Purpose of Lower and Upper Bounds

The lower and upper bounds provide insight into the **uncertainty** of the forecast. By accounting for potential fluctuations, this interval range helps with planning and offers a more reliable estimate of possible outcomes.
