# Emission Insights: Analyzing CO2 Emissions in Vehicles Using R
## Overview
This project presents a detailed analysis of a comprehensive dataset on various vehicles, exploring the relationship between car features and environmental impact, specifically focusing on CO2 emissions. The study categorizes cars by brand, model, and type, and examines specifics like engine size, transmission, and fuel consumption in urban and highway settings. Through statistical methods, patterns are discerned, revealing correlations between vehicle attributes and fuel efficiency. The findings are essential for manufacturers aiming to develop cars that align with consumer preferences and environmental standards, providing a foundation for future vehicle innovation and sustainable practices.

## Environmental Context
CO2 emissions significantly contribute to the greenhouse effect, leading to global warming and various adverse effects such as rising global temperatures, sea-level rise, changes in weather patterns, and ecosystem disruptions. Reducing CO2 emissions is crucial for mitigating climate change and minimizing its harmful effects. This project aims to quantify the environmental impact of different vehicle types, which is critical in the current context of growing environmental concerns.

## Project Goal
The primary goal of this project is to create a sophisticated predictive model that accurately forecasts CO2 emissions from vehicles. This model utilizes a rich dataset encompassing various vehicle characteristics such as make, model, engine size, number of cylinders, type of transmission, and fuel consumption metrics. By analyzing and understanding the correlations between these variables and CO2 emissions, the project endeavors to provide valuable insights into how automobile design and consumer choices can be optimized for lower carbon footprints.

## Data Description
The dataset used for this analysis includes 7,385 vehicles  with the following attributes:

- Make: The brand of the vehicle (e.g., ACURA).
- 
- Model: Specific model of the vehicle (e.g., ILX).
- 
- Vehicle.Class: The category of the vehicle (e.g., COMPACT, SUV - SMALL).
- 
- Engine.Size.L.: The size of the engine in liters (continuous numeric).
- 
- Cylinders: The number of cylinders in the engine (integer).
- 
- Transmission: Type of transmission (e.g., M6, AV7).
- 
- Fuel Type: Type of fuel used (e.g., Z).
- 
- Fuel Consumption City (L/100 km): Fuel consumption in city (continuous numeric).
- 
- Fuel Consumption Hwy (L/100 km): Fuel consumption on the highway (continuous numeric).
- 
- Fuel Consumption Comb (L/100 km): Combined fuel consumption (continuous numeric).
- 
- Fuel Consumption Comb (mpg): Combined fuel consumption in miles per gallon (integer).
- 
- CO2 Emissions(g/km): Carbon dioxide emissions in grams per kilometer (integer).

No missing values were found in the dataset after initial checks.

## Data Analysis and Modeling
Univariate Exploratory Data Analysis (EDA)
Univariate EDA was performed to examine the distribution of the data, using boxplots and histograms for continuous variables, and table functions and bar plots for categorical variables.

CO2 Emissions Distribution: The histogram of CO2 Emissions shows that the majority of vehicles emit CO2 within a middle range, with fewer vehicles having very low or very high emissions.

Fuel Consumption Distribution: The histogram for combined fuel consumption (mpg) indicates a concentration of more fuel-efficient vehicles in the lower consumption range.

Vehicle Class Frequencies: The dataset includes a variety of vehicle classes such as compact, SUVs, and pickups.

Bivariate Analysis

CO2 Emissions by Vehicle Class: Boxplot analysis revealed that larger vehicle categories such as SUVs and pickup trucks are associated with higher median CO2 emissions compared to smaller vehicles like compacts and mid-sized cars.


CO2 Emissions vs. Fuel Consumption: A scatterplot indicated a negative correlation between CO2 emissions and fuel efficiency (in mpg). As CO2 emissions increase, fuel efficiency decreases. This suggests a potential non-linear relationship.



Regression Models
The core of the analysis involved linear regression to predict CO2 emissions.

Null Model
A simple linear regression model was used, calculating the average CO2 emissions with just an intercept. The average emissions were about 250.5 grams per kilometer.


Raw Model
A multiple linear regression model was developed including predictors like car make, engine size, cylinders, and fuel type. This model achieved an R-squared value of 0.9938, indicating it explained almost all the variability in CO2 emissions. The residual standard error was about 4.662.




Diagnostics: Diagnostic plots for the raw model suggested issues such as potential non-linearity in the data, deviations from normality in the Q-Q plot, heteroscedasticity in the scale-location plot, and the presence of influential outliers in the residuals versus leverage plot.


Actual vs Predicted: The scatterplot showed good predictive accuracy, though accuracy diminished somewhat at higher emission levels.


Multicollinearity Check: High Variance Inflation Factor (VIF) values were observed for Fuel Consumption City, Fuel Consumption Highway, and Combined Fuel Consumption, indicating strong interdependence among these predictors.

Raw Model 1 (After addressing multicollinearity)
To address multicollinearity, 

Combined Fuel Consumption was chosen as the sole fuel consumption variable. This model achieved an R-squared of 0.9928 and a residual standard error of 5.009.



Diagnostics: Observations from the diagnostic plots suggested that assumptions of linear regression may not hold, specifically problems with non-constant variance (heteroscedasticity) and non-normally distributed residuals.


Actual vs Predicted: Deviations from the line, especially a funnel shape, suggested heteroscedasticity or that the model was not capturing all relevant factors, particularly at higher emission levels.

Clean Model 1 (After removing outliers)
Outliers were removed to improve model performance. This model achieved an R-squared of 0.9973.


Diagnostics: Post-cleaning, the QQ plot of residuals more closely aligned with theoretical quantiles, suggesting improved adherence to normality. The Residuals vs. Fitted plot exhibited a more random pattern, indicating better conformity with homoscedasticity and linearity assumptions.



Actual vs Predicted: The improved alignment of points around the line of perfect fit indicated a refined model with enhanced prediction accuracy and increased explained variance in CO2 emissions.

Clean Model 2 (After further data cleaning)
Subsequent data cleaning further refined the model, resulting in an even higher Multiple R-squared of 0.9982 and a small residual standard error of 2.46.



Diagnostics: The QQ plot showed residuals neatly following the normal line, affirming the normality assumption. The Residuals vs. Fitted plot revealed a random scatter of points, signifying that both linearity and homoscedasticity assumptions were satisfied. These improvements reflected a robust model.




Actual vs Predicted (Training Data): This plot showed a denser congregation of data points along the identity line, a clear sign of improved model accuracy post-data cleaning.


Actual vs Predicted (Test Data): The scatter plot for the test set showed a tight and consistent alignment of data points along the diagonal, indicating a strong positive correlation and high effectiveness in capturing the underlying pattern and variance in the data. This outcome signified that the predictive model adapted effectively to the test set without overfitting or underfitting.


Main Results
"Clean Model 2" was identified as the best model for our chosen dataset.


Predictive Accuracy: The model can very accurately predict a car's CO2 emissions, with a Multiple R-squared of 0.9982.

Key Predictors:

The intercept suggests the starting point for CO2 emissions is around 30.88 grams per kilometer.

Each make of car and its specific features contributes differently to CO2 emissions; for example, having a BUGATTI increases emissions by about 4.56 grams per kilometer compared to the base level.

Fuel consumption has a significant impact on emissions, with a 21.18 gram increase per km for every additional liter per 100 km consumed.

The effect of fuel type is also substantial, with electric cars (Fuel Type E) resulting in a large reduction in predicted CO2 emissions. Fuel type, particularly types N and E, emerged as the most powerful predictors in the data.




Model Reliability: The model's F-statistic is extremely high, indicating the collective effect of all variables is highly significant. Very low p-values across most predictors confirm their individual significance. The small residual standard error (2.46) indicates that the model's predictions are very close to the actual values.



Statistical Methods Used
This comprehensive statistics project employed a variety of statistical methods to analyze a large dataset containing details of 7,385 vehicles.


Descriptive Statistics and Histogram Analysis: Used to summarize key features of the dataset and visually represent the distribution of CO2 emissions and combined fuel consumption, highlighting central tendency and dispersion.



Scatterplot and Correlation Analysis: Utilized to explore relationships between variables, such as the negative correlation between CO2 emissions and fuel efficiency (mpg).


Simple and Multiple Linear Regression Models: The core of the analysis, starting with a simple model for baseline understanding and advancing to a multiple linear regression model for prediction with high effectiveness (R-squared of 0.9938).



Diagnostic Plot Analysis: Crucial for assessing model reliability by revealing potential issues like non-linearity, deviations from normality, heteroscedasticity, and influential outliers.


Variance Inflation Factor (VIF) Analysis: Included to analyze multicollinearity, with high VIF values for fuel consumption variables indicating strong interdependence among predictors.


Model Validation and Predictive Accuracy Assessment: Involved comparing actual versus predicted CO2 emissions through plots, showing high predictive accuracy, especially post-data cleaning.

Conclusion
In conclusion, this project successfully utilized statistical methods to analyze a comprehensive dataset of 7,385 vehicles, providing valuable insights into the relationship between vehicle characteristics and environmental impact. The analysis revealed that fuel types N and E were the most powerful predictors of CO2 emissions, underscoring the significant role of fuel choice in determining a vehicle's environmental footprint. Through descriptive statistics, correlation analysis, and advanced regression modeling, the study not only highlighted patterns in fuel consumption and emissions but also demonstrated the intricate interplay between various vehicle attributes. The project's findings are instrumental for automotive manufacturers and policymakers in making informed decisions aimed at reducing emissions and promoting sustainable practices in the automotive sector. The rigorous statistical approach adopted ensures that the conclusions drawn are both reliable and applicable to real-world scenarios, contributing meaningfully to the ongoing discourse on sustainable transportation.
