# DSA 210 Project Analysis Report

## Topic: USA Housing Prices fluctuations based on the economic agents    
## Student: Bardiya Shavandi

## Contents
1. Introduction
2. Methodology
3. Findings
4. Conclusions

## Introduction

The United States housing market is one the most significant variables in global economy which affects people including investors and policymakers. Numerous factors affect its performance, including inflation, interest rates, stock market performance, and mortgage debt.
Understanding the relationships between these economic indicators and housing prices is crucial for people in oeder to make the most efficient decision.

The primary objectives of this project are:
- To examine how inflation (CPI), interest rates (FEDFUNDS), and mortgage debt service payments influence the housing market.
- To analyze the relationship between stock market performance and housing prices.
_ To have an overview of housing price fluctuations from 2000 to 2025
  
This analysis will help in understanding whether these factors have a direct or indirect impact on housing prices, and how the U.S. housing market responds to changes in these economic variables over time, which we used the specific period for it, which is 2000 to 2025.

The datasets used in this project include:
- **Inflation Data (CPI)**: To measure inflation rates and assess its effect on housing prices.
- **Interest Rates (FEDFUNDS)**: To explore how changes in interest rates impact housing affordability and demand.
- **Stock Market Data**: To understand how stock market performance correlates with housing prices.
- **Mortgage Debt Service Payments (MDSP)**: To gauge the effect of mortgage affordability on home buying trends.
- **House Price Index (USSTHPI)**: The central measure of housing prices over time in the U.S.
  
In the following sections, we describe the methodology used to analyze the data, present the findings, and discuss the implications of our results.

## Methodology

### Data Collection

For this project, we collected publicly available datasets related to the U.S. housing market and several economic indicators. The data spans the years **2000 to 2025** and includes the following key datasets:

1. **Inflation Data (CPI)**: The **Consumer Price Index (CPI)** is used to measure inflation rates over time. This data was sourced from the **FRED** and represents the **CPI for All Urban Consumers** (CPIAUCSL).
2. **Interest Rate Data (FEDFUNDS)**: The **Federal Funds Rate** represents the interest rate at which depository institutions lend reserve balances to other depository institutions overnight. This dataset was sourced from **FRED (Federal Reserve Economic Data)**.
3. **Stock Market Data**: We used data for the **closing prices of major stock market indices** (e.g., S&P 500, Dow Jones). This data was sourced from **Kaggle** and provides insights into how market conditions affect housing prices.
4. **Mortgage Debt Service Payments (MDSP)**: This dataset includes information on the proportion of disposable income allocated to mortgage payments, sourced from **FRED**.
5. **House Price Index (USSTHPI)**: The **House Price Index** tracks the average price changes of single-family homes in the United States over time. This dataset was sourced from **FRED** and is central to this project as we aim to explore how various economic factors influence housing prices.

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
