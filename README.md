# FinalProject2023
Repository for final project - Summer 2023

# Fertility Rates and Economic Development Analysis

This project investigates the relationship between fertility rates and economic development across countries over time. We utilize regression and time series analysis to derive insights from the data.

## Data Source

Economic indicators such as GDP per capita, inflation rate, and unemployment rate by country are sourced from the [World Bank API](https://api.worldbank.org/v2/countries/all/indicators/) for the time period 1980 - 2020

## Installation and Requirements
1. Install Python version 3.11.2 (https://www.python.org/downloads/release/python-3112/)
2. Clone Repository : git clone https://github.com/pragyaIES29/FinalProject2023.git
3. Install following packages :

- requests
- warnings
- numpy
- pandas
- matplotlib
- seaborn
- statsmodels

```python
%pip install requests
%pip install warnings
%pip install numpy
%pip install pandas
%pip install matplotlib.pyplot
%pip install seaborn
%pip install statsmodels
```

## Usage

Codes have been structured and laid out in the sequence they should be run for analysis. Below is a sample of each type of visual and analysis output :

For Data Visualizations :

1. Line Charts
![9b8be710-cf3b-4460-938c-decda59f012e](https://github.com/pragyaIES29/FinalProject2023/assets/125395710/29aaec88-8f91-4d0b-b99a-59e6705b1f8f)
2. Heat Map :
   ![7687c627-c34f-4b80-8d2a-95a987f35d59](https://github.com/pragyaIES29/FinalProject2023/assets/125395710/a4a552d7-fcf6-4d99-822e-253f2d69af80)

3. scatter plot:
   ![8991cfb6-8f87-4ac9-8fb0-63d40e0331c4](https://github.com/pragyaIES29/FinalProject2023/assets/125395710/a82efeef-ee79-4cff-a02b-5fa3bf1d6f45)


5. Box Plots
![2b8a6eb6-db97-4ec9-bd2a-5c7c9a589e79](https://github.com/pragyaIES29/FinalProject2023/assets/125395710/80d6a32c-60cd-4dc1-b310-a0cbc574e71c)


For Regressions :

1. Linear Regression
![9ce8e14b-2704-416e-8e0f-44f402e89809](https://github.com/pragyaIES29/FinalProject2023/assets/125395710/03a545ca-caf7-4dad-84df-0301d7d3408e)

2. Multiple Regression
                            OLS Regression Results                            
==============================================================================
Dep. Variable:         Fertility_Rate   R-squared:                       0.324
Model:                            OLS   Adj. R-squared:                  0.321
Method:                 Least Squares   F-statistic:                     115.9
Date:                Thu, 14 Sep 2023   Prob (F-statistic):           2.56e-61
Time:                        23:22:13   Log-Likelihood:                -1205.8
No. Observations:                 729   AIC:                             2420.
Df Residuals:                     725   BIC:                             2438.
Df Model:                           3                                         
Covariance Type:            nonrobust                                         
=====================================================================================
                        coef    std err          t      P>|t|      [0.025      0.975]
-------------------------------------------------------------------------------------
const                 4.4217      0.134     32.898      0.000       4.158       4.686
GDP_per_Capita    -6.987e-05   5.08e-06    -13.744      0.000   -7.98e-05   -5.99e-05
Inflation_Rate       -0.0033      0.002     -1.547      0.122      -0.007       0.001
Unemployment_Rate    -0.1348      0.020     -6.625      0.000      -0.175      -0.095
==============================================================================
Omnibus:                      183.477   Durbin-Watson:                   0.056
Prob(Omnibus):                  0.000   Jarque-Bera (JB):               42.842
Skew:                           0.300   Prob(JB):                     4.98e-10
Kurtosis:                       1.975   Cond. No.                     3.61e+04
==============================================================================

Notes:
[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.
[2] The condition number is large, 3.61e+04. This might indicate that there are
strong multicollinearity or other numerical problems.

For Time Series Analysis :

1. Time series decomposition
   ![31137781-a4d3-4616-8301-169e7673e0a4](https://github.com/pragyaIES29/FinalProject2023/assets/125395710/53fdf824-2c6f-4a97-9c2f-be23d2e7dba2)


3. Forecasting using VaR and ARIMA

![8214347a-260e-4315-a29a-ae8dfe9961b3](https://github.com/pragyaIES29/FinalProject2023/assets/125395710/cbc61d1a-e708-4e71-8b28-be5e3c08b5fa)

## Analysis Techniques

- Regression Analysis
- Time Series Analysis

## License
[MIT](https://choosealicense.com/licenses/mit/)

[CreativeCommons](https://creativecommons.org/licenses/by/4.0/)

