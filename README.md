# **Project Name: Predicting Demand for Shared Bikes**

BoomBikes, a US-based bike-sharing provider, has experienced a significant decline in revenue due to the ongoing COVID-19 pandemic. Facing challenges to sustain in the current market, the company is seeking to develop a strategic business plan to recover and accelerate revenue growth once the lockdown ends and the economy stabilizes.

To prepare for the post-pandemic recovery, BoomBikes aims to understand the factors influencing the demand for shared bikes across the American market. This insight will help them cater effectively to customer needs, differentiate from competitors, and achieve profitability.

To achieve this, BoomBikes has contracted a consulting firm to analyze their data and address the following business objectives:
1. Identify the significant factors that influence the demand for shared bikes.
2. Assess how well these factors explain variations in bike demand.

The analysis is based on a comprehensive dataset collected daily, which incorporates various factors, including meteorological conditions and consumer behavior trends.

---

## **Table of Contents**
* [General Information](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

---

## **General Information**
### **Business Goal**
- Build a model to predict bike demand based on the available independent variables.
- Help BoomBikes understand how bike demand varies with changes in these factors.
- Provide actionable insights for the company to align its strategy with customer needs.

---

### **Dataset Overview**
The dataset contains daily bike demand data from the American market, gathered through meteorological surveys and consumer trends. 

#### **Dataset Characteristics:**
The dataset (`day.csv`) includes the following fields:

- **instant**: Record index.
- **dteday**: Date of observation.
- **season**: Season of the year (1: Spring, 2: Summer, 3: Fall, 4: Winter).
- **yr**: Year (0: 2018, 1: 2019).
- **mnth**: Month of the year (1 to 12).
- **holiday**: Indicates if the day is a holiday (1: Yes, 0: No).
- **weekday**: Day of the week.
- **workingday**: Indicates if the day is a working day (1: Yes, 0: No). A working day is defined as neither a weekend nor a holiday.
- **weathersit**: Weather conditions:
  - 1: Clear, Few clouds, Partly cloudy.
  - 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds.
  - 3: Light Snow, Light Rain + Thunderstorm, Light Rain + Scattered clouds.
  - 4: Heavy Rain, Ice Pellets, Thunderstorm, Mist, Snow + Fog.
- **temp**: Average temperature (in Celsius).
- **atemp**: Perceived or "feels-like" temperature (in Celsius).
- **hum**: Humidity level (0-1 scale).
- **windspeed**: Wind speed (0-1 scale).
- **casual**: Count of casual (non-registered) users.
- **registered**: Count of registered users.
- **cnt**: Total count of bike rentals, including both casual and registered users.


## Technologies Used

- **Python**: The primary programming language used for data analysis and model development.
- **Pandas (version 2.2.2)**: For data manipulation and preparation, including handling missing values, feature engineering, and transforming the dataset.
- **NumPy (version 1.26.4)**: For numerical computations, used primarily for array operations and statistical calculations.
- **Matplotlib (version 3.8.4)**: For data visualization, used to create plots such as histograms, boxplots, and bar charts.
- **Seaborn (version 0.13.2)**: High-level visualization library based on Matplotlib, used for statistical graphics like heatmaps and count plots.
- **VS Code**: For writing and organizing the code, visualizations, and documentation interactively.

## Conclusions
### Model Summary Overview
#### Findings

| **Variable**         | **Coefficient (β)** | **Std. Err** | **t-value** | **P value** | **95% Confidence Interval**     | **Findings**                                                                 |
|-----------------------|---------------------|--------------|-------------|--------|----------------------------------|------------------------------------------------------------------------------|
| **const**            | 2190.53            | 159.60       | 13.73       | 0.000  | [1876.96, 2504.09]              | Baseline value when all predictors are zero. Its intercept                  |
| **yr**               | 2001.24            | 74.03        | 27.03       | 0.000  | [1855.80, 2146.69]              | Significant positive trend over time.                                       |
| **temp**             | 3398.84            | 241.29       | 14.09       | 0.000  | [2924.78, 3872.90]              | Strong positive effect of temperature on the dependent variable. If climate is warm increase bike demand |
| **Spring**           | -1421.54           | 117.99       | -12.05      | 0.000  | [-1653.35, -1189.73]            | Significant reduction in the dependent variable during the spring season. Low demand for bike  |
| **Jul**              | -430.27            | 147.90       | -2.91       | 0.004  | [-720.84, -139.70]              | Moderate negative impact in July. Bike demand is reduced in July            |
| **Oct**              | 745.65             | 134.27       | 5.55        | 0.000  | [481.86, 1009.45]               | Significant positive impact in October. Bike demand increase in October     |
| **Sep**              | 592.33             | 136.34       | 4.35        | 0.000  | [324.47, 860.18]                | Significant positive impact in September. Bike demand increase in September |
| **Light Snow/Rain**  | -2341.47           | 222.47       | -10.53      | 0.000  | [-2778.56, -1904.37]            | Largest negative impact due to light snow/rain conditions. Bike demand decreases during snow and rainy conditions |
| **Mist/Cloudy**      | -679.97            | 78.65        | -8.65       | 0.000  | [-834.48, -525.45]              | Significant negative impact during misty or cloudy weather.  Reduced bike demand using cloudy or misty weather |

R-squared (0.819):  
The R-squared value indicates that approximately 81.9% of the variance in bike demand is explained by the predictors in the model. A high R-squared suggests that the model captures most of the variability in the dependent variable.

Adjusted R-squared (0.816):  
The adjusted R-squared accounts for the number of predictors in the model and is slightly lower than the R-squared. This slight reduction suggests that the predictors included in the model contribute meaningfully without overfitting. The adjusted R-squared value of 81.6% confirms a robust fit.

F-statistic (283.1, p-value: 1.31e-180):  
A very high F-statistic and an extremely small p-value indicate that the overall model is highly statistically significant. This implies that the predictors collectively explain a substantial amount of the variance in bike demand.

Durbin-Watson Statistic (2.116):  
A Durbin-Watson value close to 2 indicates that there is likely no autocorrelation in the residuals. This suggests the errors in the model are independent, meeting a key assumption of regression analysis.

Hence targe variable count
count=2190.53+(2001.24⋅yr)+(3398.84⋅temp)+(−1421.54⋅Spring)+(−430.27⋅Jul)+(745.65⋅Oct)+(592.33⋅Sep)+(−2341.47⋅Light Snow/Rain)+(−679.97⋅Mist/Cloudy)

## Acknowledgements

- This project was inspired byA **US bike-sharing provider BoomBikes** has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic.
- Special thanks to the **UpGrad Data Science Program** for providing the framework and guidance for this project.
- References: 

## Contact
Created by [@SridharGS] - feel free to contact me!
