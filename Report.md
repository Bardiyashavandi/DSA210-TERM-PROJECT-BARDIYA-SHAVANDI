# 🏠 DSA 210 Project: Housing Prices & Economic Indicators in the U.S. (2000–2025)

**Student:** Bardiya Shavandi  
**Course:** DSA 210   
**Topic:** The Impact of Economic Indicators on U.S. Housing Prices

### 📌 Contents

- Introduction

- Target Variable and Features

- Methodology

      - Data Collection
  
      - Preprocessing
  
      - Feature Engineering
  
- Exploratory Data Analysis

- Machine Learning

      - Supervised
      
      - Unsupervised
  
- Findings

- Conclusions

---

## 📖 Introduction

The United States housing market is one the most significant variables in global economy which affects people including investors and policymakers. Numerous factors affect its performance, including inflation, interest rates, stock market performance, mortgage debt, unemployment and GDP.
Understanding the relationships between these economic indicators and housing prices is crucial for people in order to make the most efficient decision.

### 🎯 Project Objectives
- To examine how inflation (CPI), interest rates (FEDFUNDS), and mortgage debt service payments influence the housing market.
- To analyze the relationship between stock market performance and housing prices.
_ To have an overview of housing price fluctuations from 2000 to 2025
  
This analysis will help in understanding whether these factors have a direct or indirect impact on housing prices, and how the U.S. housing market responds to changes in these economic variables over time, which we used the specific period for it, which is 2000 to 2025.

### 📂 Datasets Used
- **Inflation Data (CPI)**: To measure inflation rates and assess its effect on housing prices.
- **Interest Rates (FEDFUNDS)**: To explore how changes in interest rates impact housing affordability and demand.
- **Stock Market Data**: To understand how stock market performance correlates with housing prices.
- **Mortgage Debt Service Payments (MDSP)**: To understand the effect of mortgage affordability on home buying trends.
- **GDP** : The effect of gdp on house prices
- **Unemployment** : How would changes on unemployment rate affect it?
- **House Price Index (USSTHPI)**: The central measure of housing prices over time in the U.S.
  
In the following sections, we describe the methodology used to analyze the data, present the findings, and discuss the implications of our results.

---

## 🎯 Target Variable and Features

### 🏠 Target Variable
The target variable in this project is **USSTHPI (House Price Index)**, which represents the changes in housing prices over time.

### 📈 Features Used for Prediction
The features used to predict housing prices include:
- **Inflation (CPIAUCSL)**: The inflation rate in the U.S. over the analysis period.
- **Interest Rates (FEDFUNDS)**: The federal funds rate, representing the cost of borrowing.
- **Stock Market (Close)**: Stock market performance (closing prices of major indices).
- **Mortgage Debt Service Payments (MDSP)**: Payments made by households for mortgages.
- **Unemployment Rate**: The unemployment rate in the U.S.
- **GDP**: The U.S. Gross Domestic Product over the years.

These features are used in conjunction to predict the target variable, **USSTHPI**.

---

## 🧪 Methodology

### 📥 Data Collection

For this project, we collected publicly available datasets related to the U.S. housing market and several economic indicators. The data spans the years **2000 to 2025** and includes the following key datasets:

1. **Inflation Data (CPI)**: The **Consumer Price Index (CPI)** is used to measure inflation rates over time. This data was sourced from the **FRED** and represents the **CPI for All Urban Consumers** (CPIAUCSL).
2. **Interest Rate Data (FEDFUNDS)**: The **Federal Funds Rate** represents the interest rate at which depository institutions lend reserve balances to other depository institutions overnight. This dataset was sourced from **FRED (Federal Reserve Economic Data)**.
3. **Stock Market Data**: We used data for the **closing prices of major stock market indices** (e.g., S&P 500, Dow Jones). This data was sourced from **Kaggle** and provides insights into how market conditions affect housing prices.
4. **Mortgage Debt Service Payments (MDSP)**: This dataset includes information on the proportion of disposable income allocated to mortgage payments, sourced from **FRED**.
5. **House Price Index (USSTHPI)**: The **House Price Index** tracks the average price changes of single-family homes in the United States over time. This dataset was sourced from **FRED** and is central to this project as we aim to explore how various economic factors influence housing prices.
6. GDP : from FRED
7. Unemployment : from FRED

These datasets were retrieved in CSV format.

--- 

### 🧹 Data Preprocessing

1) Handling missing values: At the beginning, it was essential to address any missing data in the datasets. I started to check whether these missing values exist or not in datasets that will be organized further. For Stock market datasets, which include missing values, I used forward filling, which filled the null values with the last known values to ensure continuity. Furthermore, I checked all datasets to observe these missing values.
   
2) Datetime conversion & Renaming columns: For consistency, I converted the date column from each dataset to observation date to have a similar time variable. Then, I converted all datasets to the Datetime format to allow for proper filtering and combination of datasets in further steps. This conversion would ensure the analysis is consistent and complete.
   
3) Filtering: I changed all datasets' Observation date from 2000 to 2025. From this step, we can initiate our analysis because Economic agents' fluctuation should be consistent in time in order to be analysed. Moreover, this step ensures that all data sets will share the same observation data starting in 2000 and ending in 2025. Our desired time range is from 2000 to 2025, and we removed other rows including other dates which does not fall within this period.

4) Merging: In this part, I merged each economic variable with the house price index to analyze the relationship mechanism between them.

5) Checks: After these steps, I check these merged datasets by .describe.

6) Box Plot: I created a Box Plot for each variable to have an advanced overview of the datasets. Furthermore, we detected some clusters out of range, which will be analyzed further by outlier detection to ensure that if an outlier exists, it should be removed.

    ![plotshouse_price_index_boxplot](https://github.com/user-attachments/assets/77e63df4-ffda-41ce-830f-16bdac65e3f5)

7) Outlier Detection: I made the function for this purpose, and I disregard and remove these outliers. After that, I checked these datasets with a suspicious cluster, and the ones that remained are extreme values, and they are not outliers.

## 📊 Exploratory Data Analysis

To better understand the structure and relationships within the data, we created several visualizations:

### 📦 Box Plots
- Used to identify outliers in variables such as `USSTHPI`, `CPIAUCSL`, `FEDFUNDS`, and `MDSP`.
- Outliers were further analyzed and handled accordingly using Z-score and IQR methods.

### 📉 Histograms
- Plotted for each variable to inspect the distribution and skewness.
- Helped identify whether features were normally distributed or required transformation.

### 🔗 Scatter Plots
- Used to explore pairwise relationships between economic indicators and `USSTHPI`.
- Regression lines were added to visualize trends and direction of correlation.

### ⏳ Time Series Plots
- Visualized trends in housing prices and economic indicators over time.
- Clearly illustrated major events such as the 2008 financial crisis and 2020 COVID-19 recession.

### 🧮 Correlation Matrix
- A heatmap was generated using Pearson correlation coefficients.
- Revealed strong positive correlation between `CPIAUCSL` and `USSTHPI` (~0.86), as well as other moderate relationships with GDP and unemployment.
   
   ![scatterploy](https://github.com/user-attachments/assets/9bfa7cdc-7a39-4d4b-b062-eba37a26a09c)


8) I used Pearson to utilize Hypothesis testing for each dataset and the house price index.
Strong Relationships (Significant):
Inflation (CPI):
Very strong positive relationship (correlation: 0.84) — As inflation increases, housing prices tend to rise too.
GDP:
Very strong positive relationship (correlation: 0.89) — As the economy grows, housing prices also go up.
Stock Market:
Moderate positive relationship (correlation: 0.37) — When the stock market goes up, housing prices tend to increase.
Unemployment:
Moderate negative relationship (correlation: -0.29) — As unemployment rises, housing prices tend to go down.
Interest Rates:
Weak negative relationship (correlation: -0.10) — Higher interest rates slightly reduce housing prices.
No Significant Relationship:
Mortgage Debt Service Payments:
Very weak relationship (correlation: 0.0058, high p-value) — No real impact found on housing prices.

#### 📍 Linear regression

9) In this project, I also applied Linear Regression, one of the most fundamental supervised learning algorithms. The goal was to predict housing prices (USSTHPI) using all relevant economic features such as inflation (CPI), interest rates (FEDFUNDS), GDP, mortgage debt (MDSP), unemployment rate (UNRATE), and lag/rolling features. Also, In this part, I wanted to predict the prices based on all features , so I did not remove lagged house price index because these ones enhance the efficiency but I used Linear regression without these feature as well which I explained it after this model.

We trained the model using standardized input features and evaluated its performance on a separate test set. The results were as follows:

Mean Squared Error (MSE): 0.00115
Root Mean Squared Error (RMSE): 0.03395
R² Score: 0.99928

This exceptionally high R² score indicates that the model explains 99.9% of the variance in housing prices, meaning the linear regression model fits the data very well. Additionally, the predicted vs. actual plot shows that the predictions align very closely with real housing price values, suggesting that the model generalizes well and is not overfitting. This further reinforces that linear regression can be an effective baseline model for predicting housing prices when given well-prepared and enriched economic data.

10) Linear regression without lagged columns: I utilized this model to further explore the ralationship between our main features and house price index:
    
Linear Regression Model Evaluation:
Mean Squared Error: 0.070626422216715
Root Mean Squared Error: 0.2657563211227816
R² Score: 0.955949408314608

Linear Regression Coefficients:
CPIAUCSL: -2.9049414399599436
FEDFUNDS: -0.08364351713363764
Close: -1.0532527823441694e-06
MDSP: 0.4238359272635925
GDP: 0.0010434981353119846
UNRATE: -0.011024955688318
Intercept: -16.027124231485736

The linear regression model performed strongly, achieving an R² score of 0.956, indicating that approximately 95.6% of the variance in housing prices can be explained by the selected economic indicators. The Mean Squared Error (MSE) was 0.0706, and the Root Mean Squared Error (RMSE) was 0.266, showing a relatively low prediction error.

---
    
# Machine Learning models

#### Preparation
1) I prepared and merged the datasets in order to be ready for machine learning methods. I handled any date formatting issues by ensuring all datasets had consistent datetime formats so that we could properly merge them based on the date.

2) Feature engineering: I enriched the project by addding two more data sets (GDP & UNEMPLOYMENT), also I create new columns for modelling like lagged dataset columns. Lag features show how current values compare with previous ones (e.g., yesterday’s stock market price or inflation), while rolling averages smooth out the data to highlight long-term trends.

3) To better understand the relationship between different economic factors and housing prices, we transformed some features, such as calculating the percentage change in housing prices compared to the previous period, to capture trends over time.

4) After cleaning, enriching, and transforming the data, we merged multiple datasets (e.g., inflation data with housing price index, interest rates with housing prices, etc.) using the observation_date to get a unified dataset. This allowed us to analyze the combined effects of different economic factors on housing prices.
   
    ![Unknown](https://github.com/user-attachments/assets/5a6e5319-085d-4abd-8d3c-88335060afce)

In this plot, we compare the lagged column and the default one, which represents that past housing price movements have a notable influence on future prices. This visualization can help us understand trends and cycles in housing prices and their temporal relationships with past data.

5) I handled the missing values after feature engineering by using forward and backward fill.

---

## 🤖 Machine Learning

The project applied both **supervised** and **unsupervised** machine learning methods to analyze and predict housing price behavior.

---

1) Defining the test & training data: In this phase, I standardized my datasets to be further extracted for machine learning methods. Afterwards, I defined the features and target as follows.
   
   X = All columns except for housing price index 
   Y = Housing price index (target)
   
### 🔎 Supervised Learning

#### 🌳 Random Forest Regressor
2) RANDOM FOREST: I used a random forest model to observe and evaluate how well the trained Random Forest model is performing by comparing its predictions to the actual values. It uses common metrics like Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R-squared (R²).

    ![Unknown](https://github.com/user-attachments/assets/132b8033-546a-43d1-8500-56a46f491a2c)

We can clearly see that the most important feature by far was the 3-month rolling average of CPI (Consumer Price Index), which means recent inflation trends had the biggest impact on predicting price direction. This makes sense, as CPI directly reflects changes in the cost of living and purchasing power.

The next most important features were:

USSTHPI_Lag1: The housing price index from the previous month — suggesting that past housing trends help predict future price movements.
FEDFUNDS_Rolling_Mean_3months: The 3-month average of the federal funds interest rate, which affects borrowing costs and spending.
Month and FEDFUNDS (current value) also had moderate impact, possibly due to seasonal effects and policy changes.

#### 📍 K-Nearest Neighbors (KNN)
3) KNN: We applied the K-Nearest Neighbors Regressor with k = 5 to predict housing prices (USSTHPI). The model was trained on scaled training data and evaluated using standard regression metrics:

Mean Squared Error (MSE): [insert value from output]
Root Mean Squared Error (RMSE): [insert value]
R² Score: [insert value]
These values indicate how well the KNN model performs in capturing patterns in the data. A lower RMSE means predictions are close to actual values, while an R² close to 1 shows a good fit.


---

### 🧠 Unsupervised Learning

#### 📦 K-Means Clustering
4) K-MEANS CUSTERING: I utilized unsupervised learning (K-means Clustering) in order to create the model. To explore hidden patterns in the data without using labeled outputs, we applied K-Means clustering, an unsupervised learning method. Here's how the process unfolded:

Feature Selection:
We selected seven key economic indicators for clustering:
Using the Elbow Method, we plotted the inertia (sum of squared distances to cluster centers) for different values of k from 1 to 10.
The "elbow" point in the plot indicated the optimal number of clusters, which we chose as k = 3.
Clustering and Visualization:
We applied K-Means with 3 clusters and used Principal Component Analysis (PCA) to reduce the high-dimensional data into two dimensions for easier visualization. The resulting scatter plot shows how data points are grouped into three distinct clusters.
- **Interpretation**:
  - Cluster 1 contained more volatile economic conditions.
  - Clusters 0 and 2 represented more stable periods.
  - Clusters revealed hidden economic phases based on indicator behavior, without using housing prices for training.

---

## 📌 Findings


  ![Inflation](https://github.com/user-attachments/assets/9ba50811-a5bc-4074-980d-4a57a7f16d0a)

The scatter plot illustrates the relationship between Housing Prices (USSTHPI) and Inflation (CPIAUCSL). It shows a clear positive correlation, where an increase in inflation appears to correspond with higher housing prices. The red dashed line represents the linear regression line, highlighting the upward trend, which suggests that as inflation rises, housing prices tend to follow suit. This visualization helps in understanding the potential influence of inflation on the housing market.
### 💸 Inflation
- Strong positive correlation with housing prices (`r ≈ 0.86`).
- Higher inflation generally aligned with increasing housing prices.

  ![Interest rate](https://github.com/user-attachments/assets/ae49b9a6-dffa-443f-b5db-6e6554c51812)

### 💰 Interest Rates
- Weak negative correlation with housing prices.
- As rates increased, housing prices were affected slightly, likely due to borrowing cost.

  ![scatterploy](https://github.com/user-attachments/assets/9301f5ad-e365-4f72-851b-084374b6ba64)

### 📉 Mortgage Debt (MDSP)
- Showed weak-to-moderate negative correlation with `USSTHPI`.
- Higher debt service pressure may suppress home-buying demand.

### 📊 Stock Market
- Moderate positive correlation with housing prices.
- Reflects investor confidence and general economic momentum.

### 📈 GDP & Unemployment
- **GDP** had a strong positive correlation with `USSTHPI`.
- **Unemployment** showed a clear inverse correlation: lower unemployment aligned with higher housing prices.

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

Linear Regression:

   ![Unknown](https://github.com/user-attachments/assets/c9bcbdc4-9d51-4653-bf72-5898b7e71b63)

This scatter plot shows the performance of a Linear Regression model that predicts housing prices (USSTHPI) based only on the raw economic features—without using any lagged or shifted columns. Each blue dot represents a single prediction, where the x-axis is the actual price and the y-axis is the predicted price. The dashed diagonal line shows where perfect predictions would fall. As we can see, most of the points are closely aligned with this line, meaning the model did a fairly good job overall. While it may not be as precise as models that include time-based memory (like lagged values), this visualization confirms that even the raw economic indicators carry enough signal to make reasonable housing price predictions.

Machine Learning:

- Supervised 

(Random Forest)

- To assess the performance of the Random Forest regression model, we used three evaluation metrics:

Mean Squared Error (MSE): 0.00115
Root Mean Squared Error (RMSE): 0.03395
R² Score: 0.99928
These results indicate that the model performs exceptionally well. The very low MSE and RMSE show that the predictions are extremely close to the actual values. Additionally, an R² score of 0.99928 means that over 99.9% of the variance in the target variable is explained by the model. This suggests a highly accurate and reliable fit for the data.

  ![Unknown copy](https://github.com/user-attachments/assets/c996ae10-9dcd-43e7-8287-7b086bc7ab29)
  
Predicted vs. Actual Values Plot:
The scatter plot compares the actual housing prices (USSTHPI) with the values predicted by our Random Forest model. Each point represents a prediction for a test data point. The diagonal dashed line indicates perfect predictions (i.e., predicted = actual). The closer the points are to this line, the better the model's performance.
In our plot, most points closely align with the diagonal, showing that the model is accurately predicting housing prices with minimal error.

   ![Unknown](https://github.com/user-attachments/assets/cc3a5954-a095-4375-9a33-a8d8d69e08a6)

The scatter plot above illustrates the relationship between the actual housing prices (USSTHPI) and the values predicted by the K-Nearest Neighbors (KNN) regression model.
Each point represents a prediction for a specific data point.
The black dashed line is the reference line where predicted values would exactly match the actual values.
Most of the points are tightly clustered around the line, showing that the model generally produces accurate predictions.
However, we can observe some minor deviations at higher USSTHPI values, where the model slightly underestimates or overestimates prices.


- Unsupervised

    ![Unknown](https://github.com/user-attachments/assets/18ede4fd-6e44-4e3a-8028-f06476e1b391)

The dots are colored based on their cluster assignments:
Cluster 0 (blue)
Cluster 1 (orange)
Cluster 2 (green)
We can observe that:

The clusters are fairly well-separated, indicating that K-Means was able to find distinct patterns in the data.
Cluster 1 (orange) is more spread out along the x-axis, suggesting it contains periods with more extreme values in some economic indicators.
Clusters 0 and 2 are more compact and closer to the origin, possibly representing more stable or moderate economic phases.

---

## ✅ Conclusion

This project demonstrated how macroeconomic indicators affect U.S. housing prices between 2000 and 2025. Through data collection, transformation, visualization, and machine learning models, we found that:

- **Inflation and GDP** had the strongest impact on housing price trends.
- **Lag features** and **rolling averages** significantly improved predictive accuracy.
- **Random Forest Regressor** yielded the best performance highlighting near-perfect prediction ability.
- **K-Means Clustering** helped identify meaningful economic patterns and time periods with shared economic characteristics.

Through visualizations and models like Random Forest, Linear Regression, and KNN, we gained deeper insight into how the housing market behaves over time. Overall, this project helped connect complex economic trends to real-life outcomes like the cost of buying a home.

The results support the idea that housing prices are deeply influenced by broader economic conditions, and machine learning can effectively model these dynamics for better forecasting and insight.

I did not use any classification methods because my datasets were not categorical therefore, random forest and knn were the most compatible with the features.

## Limitations and Future Work

While the results were promising, there are still some limitations. First, the models depend heavily on the quality and availability of historical data—missing or outdated data could impact predictions. Second, we used national-level data, which may hide regional differences in housing prices. Also, although we created lag features and rolling averages to capture trends, we didn’t use more advanced time-series models like ARIMA or LSTM, which could improve forecasting. In the future, we could explore more detailed datasets (like state-level or city-level housing prices), try different model types (e.g., deep learning), or include other variables like income, population growth, or housing supply. Adding interactive dashboards or forecasting tools could also make the project more useful for real-world applications.
