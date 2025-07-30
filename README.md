# Emission Insights: Analyzing CO2 Emissions in Vehicles Using R
## Overview
This project presents a detailed analysis of a comprehensive dataset on various vehicles, exploring the relationship between car features and environmental impact, specifically focusing on CO2 emissions. The study categorizes cars by brand, model, and type, and examines specifics like engine size, transmission, and fuel consumption in urban and highway settings. Through statistical methods, patterns are discerned, revealing correlations between vehicle attributes and fuel efficiency. The findings are essential for manufacturers aiming to develop cars that align with consumer preferences and environmental standards, providing a foundation for future vehicle innovation and sustainable practices.

## Environmental Context
CO2 emissions significantly contribute to the greenhouse effect, leading to global warming and various adverse effects such as rising global temperatures, sea-level rise, changes in weather patterns, and ecosystem disruptions. Reducing CO2 emissions is crucial for mitigating climate change and minimizing its harmful effects. This project aims to quantify the environmental impact of different vehicle types, which is critical in the current context of growing environmental concerns.

## Project Goal
The primary goal of this project is to create a sophisticated predictive model that accurately forecasts CO2 emissions from vehicles. This model utilizes a rich dataset encompassing various vehicle characteristics such as make, model, engine size, number of cylinders, type of transmission, and fuel consumption metrics. By analyzing and understanding the correlations between these variables and CO2 emissions, the project provides valuable insights into how automobile design and consumer choices can be optimized for lower carbon footprints.

## Data Description
The dataset used for this analysis includes 7,385 vehicles with the following attributes:

- Make: The brand of the vehicle (e.g., ACURA)
- Model: Specific model of the vehicle (e.g., ILX)
- Vehicle.Class: The category of the vehicle (e.g., COMPACT, SUV - SMALL)
- Engine.Size.L.: The size of the engine in liters (continuous numeric)
- Cylinders: The number of cylinders in the engine (integer)
- Transmission: Type of transmission (e.g., M6, AV7)
- Fuel Type: Type of fuel used (e.g., Z)
- Fuel Consumption City (L/100 km): Fuel consumption in city (continuous numeric)
- Fuel Consumption Hwy (L/100 km): Fuel consumption on the highway (continuous numeric)
- Fuel Consumption Comb (L/100 km): Combined fuel consumption (continuous numeric)
- Fuel Consumption Comb (mpg): Combined fuel consumption in miles per gallon (integer)
- CO2 Emissions (g/km): Carbon dioxide emissions in grams per kilometer (integer)
- No missing values were found in the dataset after initial checks.

## Data Analysis and Modeling
Univariate Exploratory Data Analysis (EDA)
Univariate EDA was performed to examine the distribution of the data, using boxplots and histograms for continuous variables, and table functions and bar plots for categorical variables.

CO2 Emissions Distribution: The histogram of CO2 Emissions shows that the majority of vehicles emit CO2 within a middle range.
Fuel Consumption Distribution: The histogram for combined fuel consumption (mpg) indicates a concentration of more fuel-efficient vehicles in the lower consumption range.
Vehicle Class Frequencies: The dataset includes a variety of vehicle classes such as compact, SUVs, and pickups.
Bivariate Analysis
CO2 Emissions by Vehicle Class: Boxplot analysis reveals that larger vehicle categories such as SUVs and pickup trucks are associated with higher median CO2 emissions compared to smaller vehicles.
CO2 Emissions vs. Fuel Consumption: A scatterplot indicates a negative correlation between CO2 emissions and fuel efficiency (in mpg): as CO2 emissions increase, fuel efficiency decreases, suggesting a potential non-linear relationship.

## Regression Models
The core of the analysis involved linear regression to predict CO2 emissions.

Null Model :
A simple linear regression model was used, calculating the average CO2 emissions with just an intercept. The average emissions were about 250.5 grams per kilometer.

Raw Model :
A multiple linear regression model was developed including predictors like car make, engine size, cylinders, and fuel type. This model achieved an R-squared value of 0.9938, indicating it explained almost all the variability in CO2 emissions. The residual standard error was about 4.662.

Diagnostics: Diagnostic plots for the raw model suggested issues such as potential non-linearity, deviations from normality, heteroscedasticity, and influential outliers.

Multicollinearity Check: High Variance Inflation Factor (VIF) values were observed for Fuel Consumption City, Fuel Consumption Highway, and Combined Fuel Consumption, indicating strong interdependence among these predictors.

Raw Model 1 (After addressing multicollinearity)
To address multicollinearity, Combined Fuel Consumption was chosen as the sole fuel consumption variable. This model achieved an R-squared of 0.9928 and a residual standard error of 5.009.

Diagnostics: Observations from the diagnostic plots suggested that assumptions of linear regression may not hold, specifically problems with non-constant variance (heteroscedasticity) and non-normally distributed residuals.

Clean Model 1 (After removing outliers)
Outliers were removed to improve model performance. This model achieved an R-squared of 0.9973.

Diagnostics: Post-cleaning, diagnostic plots showed improved adherence to normality, homoscedasticity, and linearity assumptions.

Clean Model 2 (Further data cleaning)
Subsequent data cleaning further refined the model, resulting in an even higher Multiple R-squared of 0.9982 and a small residual standard error of 2.46.

Diagnostics: The model satisfied normality and homoscedasticity assumptions, and predictive accuracy improved significantly.

## Main Results
"Clean Model 2" was identified as the best model for our chosen dataset.

Predictive Accuracy: The model can very accurately predict a car's CO2 emissions, with a Multiple R-squared of 0.9982.
Key Predictors: The intercept, car make, fuel consumption, and fuel type, particularly types N and E, were the most powerful predictors.
Model Reliability: The model's F-statistic and low p-values confirm the significance of variables, and the small residual standard error indicates high predictive accuracy.
Statistical Methods Used
Descriptive Statistics and Histogram Analysis: To summarize key features of the dataset.
Scatterplot and Correlation Analysis: To explore relationships between variables.
Simple and Multiple Linear Regression Models: For prediction and analysis.
Diagnostic Plot Analysis: To assess model reliability.
Variance Inflation Factor (VIF) Analysis: To analyze multicollinearity.
Model Validation and Predictive Accuracy Assessment: Comparing actual versus predicted CO2 emissions.

## Conclusion
This project successfully utilized statistical methods to analyze a comprehensive dataset of 7,385 vehicles, providing valuable insights into the relationship between vehicle characteristics and environmental impact. The analysis revealed that fuel types N and E were the most powerful predictors of CO2 emissions, underscoring the significant role of fuel choice. The project's findings are instrumental for automotive manufacturers and policymakers in making informed decisions aimed at reducing emissions and promoting sustainable practices in the automotive sector.
