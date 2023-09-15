# FinalProject2023
Repository for final project - Summer 2023

# Fertility Rates and Economic Development Analysis

This project investigates the relationship between fertility rates and economic development across countries over time. We utilize regression and time series analysis to derive insights from the data.

## Data Source

Economic indicators such as GDP per capita, inflation rate, and unemployment rate by country are sourced from the [World Bank API](https://api.worldbank.org/v2/countries/all/indicators/) for the time period 1980 - 2020

## Installation and Requirements
The Project requires Python version 3.11.2 (https://www.python.org/downloads/release/python-3112/)
to be installed along with the following packages for smooth functioning:

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

For Data Visualizations :

```python
plt.figure(figsize=(12, 8))

# Plot each country's fertility rate over Year
for country in fertility_rate_df.columns:
    plt.plot(fertility_rate_df.index, fertility_rate_df[country], label=country)

# Add labels and title
plt.xlabel("Year")
plt.ylabel("Fertility Rate")
plt.title("Fertility Rates Over Year by Country")
plt.legend()
plt.xticks(rotation=45)
plt.tight_layout()

# Show the plot
plt.show()

```
For Regressions :

```python
# Create DataFrames from the indicator data
fertility_df = pd.DataFrame(cleaned_data_by_indicator["Fertility Rate"])
gdp_per_capita_df = pd.DataFrame(cleaned_data_by_indicator["GDP per Capita"])

# Merge the DataFrames on "Country" and "Year"
merged_df = pd.merge(fertility_df, gdp_per_capita_df, on=["Country", "Year"])

# Extract variables for the linear regression
x = merged_df["Value_y"]  # GDP per Capita
y = merged_df["Value_x"]  # Fertility Rate

# Perform linear regression using scipy's linregress function
slope, intercept, r_value, p_value, std_err = stats.linregress(x, y)

# Create the regression line
regression_line = slope * x + intercept

# Print the regression results
print(f"Slope: {slope:.4f}")
print(f"Intercept: {intercept:.4f}")
print(f"R-squared: {r_value**2:.4f}")
print(f"P-value: {p_value:.4f}")

# Set up the scatter plot figure
plt.figure(figsize=(10, 8))

# Create scatter plot of the data
plt.scatter(x, y, label="Data", alpha=0.7)

# Plot the regression line
plt.plot(x, regression_line, color="red", label="Regression Line")

# Add labels and title
plt.xlabel("GDP per Capita")
plt.ylabel("Fertility Rate")
plt.title("Fertility Rates vs. GDP per Capita")

# Add legend
plt.legend()

# Show the plot
plt.tight_layout()
plt.show()
```
For time series analysis:

```python
# Load the cleaned data for Fertility Rate and GDP per Capita
fertility_data = cleaned_data_by_indicator["Fertility Rate"]
gdp_data = cleaned_data_by_indicator["GDP per Capita"]

# Create dataframes for the fertility rate and GDP per Capita
fertility_df = pd.DataFrame(fertility_data)
gdp_df = pd.DataFrame(gdp_data)

# Merge the two dataframes based on the "Country" and "Year" columns
merged_df = pd.merge(fertility_df, gdp_df, on=["Country", "Year"], how="inner")

# Define the dependent variable (y) and the independent variable (X)
y = merged_df["Value_x"]  # Fertility Rate
X = merged_df["Value_y"]  # GDP per Capita

# Add a constant to the independent variable matrix
X = sm.add_constant(X)

# Fit a linear regression model
model = sm.OLS(y, X).fit()

# Display the regression results
print(model.summary())
```


## Analysis Techniques

- Regression Analysis
- Time Series Analysis

## License
[MIT](https://choosealicense.com/licenses/mit/)

[CreativeCommons](https://creativecommons.org/licenses/by/4.0/)

