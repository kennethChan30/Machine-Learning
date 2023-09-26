# Stock Prediction Model Summary

## Disclaimer
This analysis is merely reflective of my opinions, founded on data available during the time of creation. Investment ventures inherently entail risks. Prospective investors are urged to seek counsel from a qualified financial advisor prior to making any investment decisions. It is crucial to remember that past performances are not indicative of future results. Investment decisions should be made with professional advice.

## Objective
The primary goal is to construct a prediction model, leveraging LightGBM, integrated with various indicators, to forecast whether the following period closing price will be higher(Ture indicates higher closing price).

## Data
The dataset encompasses 3364 US stocks, each with a minimum trading history of three years.
- **Duration:** 2013-09-01 to 2023-08-31
- **Test Data Range:** 2023-07-01 to 2023-08-31

## Parameters
The following parameters were utilized in the analysis:
- 14-day RSI
- Change in RSI compared to the previous RSI
- Percentage of close from the 52-week high
- Percentage of close from the 52-week low
- Whether Close is higher than EMA20
- Whether EMA20 is higher than EMA50
- Whether EMA50 is higher than EMA200
- Whether Volume is higher than MA20
- % change in the previous close

## Evaluation Results
| Metric             | Validation Data | Test Data | Test data(prediciton all True)  | Test data(prediction all False)  | Randomly Distributed |
|--------------------|-----------------|-----------|----------|-----------|----------------------|
| **Accuracy**       |  53.44%               |   52.02%        |     47.94%     |    52.06%       |       50.05%               |
| **AUC Score**      |   0.5482              |   0.5271    |    0.5      |       0.5    |           0.5005           |


### Observations on Model Performance
While the model displays a lackluster ability to discriminate between classes, it appears to have a slightly superior predictive accuracy compared to random guessing. However, when contrasted against scenarios where all predictions are false, the model's performance doesn't hold up well, indicating significant room for improvement.
