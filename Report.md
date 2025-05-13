# DSA 210 Project Analysis Report

## Topic: USA Housing Prices fluctuations based on the economic agents    
## Student: Bardiya Shavandi

## Contents
1. Introduction
2. Methodology
3. Findings
4. Conclusions

## Introduction

The United States housing market is one the most significant variables in global economy which affects people including investors and policymakers. Numerous factors affect its performance, including inflation, interest rates, stock market performance, mortgage debt, unemployment and GDP.
Understanding the relationships between these economic indicators and housing prices is crucial for people in order to make the most efficient decision.

The primary objectives of this project are:
- To examine how inflation (CPI), interest rates (FEDFUNDS), and mortgage debt service payments influence the housing market.
- To analyze the relationship between stock market performance and housing prices.
_ To have an overview of housing price fluctuations from 2000 to 2025
  
This analysis will help in understanding whether these factors have a direct or indirect impact on housing prices, and how the U.S. housing market responds to changes in these economic variables over time, which we used the specific period for it, which is 2000 to 2025.

The datasets used in this project include:
- **Inflation Data (CPI)**: To measure inflation rates and assess its effect on housing prices.
- **Interest Rates (FEDFUNDS)**: To explore how changes in interest rates impact housing affordability and demand.
- **Stock Market Data**: To understand how stock market performance correlates with housing prices.
- **Mortgage Debt Service Payments (MDSP)**: To understand the effect of mortgage affordability on home buying trends.
- **GDP** : The effect of gdp on house prices
- **Unemployment** : How would changes on unemployment rate affect it?
- **House Price Index (USSTHPI)**: The central measure of housing prices over time in the U.S.
  
In the following sections, we describe the methodology used to analyze the data, present the findings, and discuss the implications of our results.

## Target Variable and Features

### Target Variable
The target variable in this project is **USSTHPI (House Price Index)**, which represents the changes in housing prices over time.

### Features
The features used to predict housing prices include:
- **Inflation (CPIAUCSL)**: The inflation rate in the U.S. over the analysis period.
- **Interest Rates (FEDFUNDS)**: The federal funds rate, representing the cost of borrowing.
- **Stock Market (Close)**: Stock market performance (closing prices of major indices).
- **Mortgage Debt Service Payments (MDSP)**: Payments made by households for mortgages.
- **Unemployment Rate**: The unemployment rate in the U.S.
- **GDP**: The U.S. Gross Domestic Product over the years.

These features are used in conjunction to predict the target variable, **USSTHPI**.

## Methodology

### Data Collection

For this project, we collected publicly available datasets related to the U.S. housing market and several economic indicators. The data spans the years **2000 to 2025** and includes the following key datasets:

1. **Inflation Data (CPI)**: The **Consumer Price Index (CPI)** is used to measure inflation rates over time. This data was sourced from the **FRED** and represents the **CPI for All Urban Consumers** (CPIAUCSL).
2. **Interest Rate Data (FEDFUNDS)**: The **Federal Funds Rate** represents the interest rate at which depository institutions lend reserve balances to other depository institutions overnight. This dataset was sourced from **FRED (Federal Reserve Economic Data)**.
3. **Stock Market Data**: We used data for the **closing prices of major stock market indices** (e.g., S&P 500, Dow Jones). This data was sourced from **Kaggle** and provides insights into how market conditions affect housing prices.
4. **Mortgage Debt Service Payments (MDSP)**: This dataset includes information on the proportion of disposable income allocated to mortgage payments, sourced from **FRED**.
5. **House Price Index (USSTHPI)**: The **House Price Index** tracks the average price changes of single-family homes in the United States over time. This dataset was sourced from **FRED** and is central to this project as we aim to explore how various economic factors influence housing prices.
6. GDP : from FRED
7. Unemployment : from FRED

These datasets were retrieved in CSV format.

#### Data Cleaning & Preprocessing

1) Handling missing values: At the beginning, it was essential to address any missing data in the datasets. I started to check whether these missing values exist or not in datasets that will be organized further. For Stock market datasets, which include missing values, I used forward filling, which filled the null values with the last known values to ensure continuity. Furthermore, I checked all datasets to observe these missing values.
   
2) Datetime conversion & Renaming columns: For consistency, I converted the date column from each dataset to observation date to have a similar time variable. Then, I converted all datasets to the Datetime format to allow for proper filtering and combination of datasets in further steps. This conversion would ensure the analysis is consistent and complete.
   
3) Filtering: I changed all datasets' Observation date from 2000 to 2025. From this step, we can initiate our analysis because Economic agents' fluctuation should be consistent in time in order to be analysed. Moreover, this step ensures that all data sets will share the same observation data starting in 2000 and ending in 2025. Our desired time range is from 2000 to 2025, and we removed other rows including other dates which does not fall within this period.

4) Merging: In this part, I merged each economic variable with the house price index to analyze the relationship mechanism between them.

5) Checks: After these steps, I check these merged datasets by .describe.

6) Box Plot: I created a Box Plot for each variable to have an advanced overview of the datasets. Furthermore, we detected some clusters out of range, which will be analyzed further by outlier detection to ensure that if an outlier exists, it should be removed.

![plotshouse_price_index_boxplot](https://github.com/user-attachments/assets/77e63df4-ffda-41ce-830f-16bdac65e3f5)

7) Outlier Detection: I made the function for this purpose, and I disregard and remove these outliers. After that, I checked these datasets with a suspicious cluster, and the ones that remained are extreme values, and they are not outliers.

8) Visualization: I made numerous visuals out of these datasets separately to comprehend them.
   
   Histograms: To see the distribution and frequency
   
   Scatterplots: To observe the relationship between variables and the house price index
   
   Time series: To see the fluctuation in date
   
   Matrix: Correlation between them

   
   ![scatterploy](https://github.com/user-attachments/assets/9bfa7cdc-7a39-4d4b-b062-eba37a26a09c)


10) I used Pearson to utilize Hypothesis testing for each dataset and the house price index.


#### Findings


![Inflation](https://github.com/user-attachments/assets/9ba50811-a5bc-4074-980d-4a57a7f16d0a)

The scatter plot illustrates the relationship between Housing Prices (USSTHPI) and Inflation (CPIAUCSL). It shows a clear positive correlation, where an increase in inflation appears to correspond with higher housing prices. The red dashed line represents the linear regression line, highlighting the upward trend, which suggests that as inflation rises, housing prices tend to follow suit. This visualization helps in understanding the potential influence of inflation on the housing market.

![Interest rate](https://github.com/user-attachments/assets/ae49b9a6-dffa-443f-b5db-6e6554c51812)

There is a weak correlation between these two variables, which represent meaningful outcomes.

![scatterploy](https://github.com/user-attachments/assets/9301f5ad-e365-4f72-851b-084374b6ba64)

The scatter plot depicting the relationship between Mortgage Debt (MDSP) and Housing Prices (USSTHPI) shows a weak negative correlation, as indicated by the downward sloping red regression line. 

Hypothesis Testing: The hypothesis testing was conducted to evaluate the correlation between various economic factors—namely, inflation (CPIAUCSL), interest rates (FEDFUNDS), stock market performance (Close), and mortgage debt service payments (MDSP)—and housing prices (USSTHPI). We utilized Pearson's correlation coefficient to test the strength and significance of these relationships. Each hypothesis was tested with a null hypothesis stating that there is no significant relationship between the economic factors and housing prices. The p-values for each correlation were compared to a threshold of 0.05; if the p-value was less than 0.05, the null hypothesis was rejected, indicating a statistically significant relationship. The results of the analysis revealed strong and significant correlations across all variables. For instance, the correlation between inflation (CPIAUCSL) and housing prices (USSTHPI) was found to be 0.856, with an extremely low p-value (close to zero), signaling a strong positive relationship. Similarly, significant correlations were found between housing prices and the other factors: interest rates (FEDFUNDS), stock market performance (Close), and mortgage debt service payments (MDSP). These results collectively suggest that all the examined economic factors have a meaningful impact on housing prices in the observed period.

Time-series:

![Timeseries](https://github.com/user-attachments/assets/d93b3f5e-637d-4a87-b017-484b56290da3)

This plot highlights the trends and fluctuations in housing prices during this period. The index shows a significant increase in the years around 2004 to 2008, likely driven by a housing boom. However, there is a noticeable dip after 2008, which corresponds with the global financial crisis and the subsequent housing market crash. Following this downturn, the plot shows a steady recovery in housing prices, reflecting the post-crisis rebound and ongoing recovery until the present day. This trend underscores the cyclical nature of the housing market and provides valuable insight into the economic conditions influencing housing prices over time. The visual helps to emphasize how macroeconomic factors, including inflation, interest rates, and debt service levels, may influence the housing market.

Matrix:

![Unknown](https://github.com/user-attachments/assets/10c3711e-416f-4b81-aa95-e50997ea108f)

The heatmap visually represents the strength of correlation using color coding, where values closer to 1 indicate a strong positive correlation (red) and values closer to -1 indicate a strong negative correlation (blue). From the heatmap, we can see that the House Price Index (USSTHPI) has a strong positive correlation with Inflation (CPIAUCSL), with a value of 0.86. In contrast, there is a weaker negative correlation with other variables like Federal Funds Rate (FEDFUNDS) and Mortgage Debt Service Payments (MDSP). The Stock Market (Close) exhibits a modest positive correlation with housing prices (0.36), suggesting that market trends do have some level of influence on housing prices, but it is not as strong as other factors. This heatmap provides valuable insight into how different economic indicators are interconnected and how they might influence the housing market. Furthermore, There is strong relationship between GDP vs house price index , also there is strong relationship between UNRATE vs house price index.

Time-series (complete):

![TI](https://github.com/user-attachments/assets/c3bc07d9-2aba-49e6-97a7-6b2fe9053cf4)

This chart shows how the stock market’s closing values changed from around 2002 to 2021. Overall, the market’s been climbing steadily, with some bumps along the way. There’s a big drop around 2008 — that lines up with the global financial crisis — and another dip in 2020, which was probably due to the COVID-19 pandemic. Even with those hits, the market always seems to bounce back stronger. The shaded area around the line shows how much the values vary — and you can see that this uncertainty or volatility has gotten wider in recent years, meaning things have been more unpredictable. Still, by the end of the chart, the stock market is closing at some of its highest points ever. So, despite the chaos, the long-term direction has been up.
