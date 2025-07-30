# Emission Insights: Analyzing CO2 Emissions in Vehicles Using R

## Overview

[cite_start]This project presents a detailed analysis of a comprehensive dataset on various vehicles, exploring the relationship between car features and environmental impact, specifically focusing on CO2 emissions[cite: 5, 7]. [cite_start]The study categorizes cars by brand, model, and type, and examines specifics like engine size, transmission, and fuel consumption in urban and highway settings[cite: 6, 7]. [cite_start]Through statistical methods, patterns are discerned, revealing correlations between vehicle attributes and fuel efficiency[cite: 8]. [cite_start]The findings are essential for manufacturers aiming to develop cars that align with consumer preferences and environmental standards, providing a foundation for future vehicle innovation and sustainable practices[cite: 9].

## Environmental Context

[cite_start]CO2 emissions significantly contribute to the greenhouse effect, leading to global warming and various adverse effects such as rising global temperatures, sea-level rise, changes in weather patterns, and ecosystem disruptions[cite: 11, 12, 13]. [cite_start]Reducing CO2 emissions is crucial for mitigating climate change and minimizing its harmful effects[cite: 14]. [cite_start]This project aims to quantify the environmental impact of different vehicle types, which is critical in the current context of growing environmental concerns[cite: 38].

## Project Goal

[cite_start]The primary goal of this project is to create a sophisticated predictive model that accurately forecasts CO2 emissions from vehicles[cite: 37]. [cite_start]This model utilizes a rich dataset encompassing various vehicle characteristics such as make, model, engine size, number of cylinders, type of transmission, and fuel consumption metrics[cite: 37]. [cite_start]By analyzing and understanding the correlations between these variables and CO2 emissions, the project endeavors to provide valuable insights into how automobile design and consumer choices can be optimized for lower carbon footprints[cite: 39].

## Data Description

[cite_start]The dataset used for this analysis includes 7,385 vehicles [cite: 442] with the following attributes:

* [cite_start]**Make**: The brand of the vehicle (e.g., ACURA)[cite: 24].
* [cite_start]**Model**: Specific model of the vehicle (e.g., ILX)[cite: 25].
* [cite_start]**Vehicle.Class**: The category of the vehicle (e.g., COMPACT, SUV - SMALL)[cite: 26].
* [cite_start]**Engine.Size.L.**: The size of the engine in liters (continuous numeric)[cite: 27].
* [cite_start]**Cylinders**: The number of cylinders in the engine (integer)[cite: 28].
* [cite_start]**Transmission**: Type of transmission (e.g., M6, AV7)[cite: 29].
* [cite_start]**Fuel Type**: Type of fuel used (e.g., Z)[cite: 30].
* [cite_start]**Fuel Consumption City (L/100 km)**: Fuel consumption in city (continuous numeric)[cite: 31].
* [cite_start]**Fuel Consumption Hwy (L/100 km)**: Fuel consumption on the highway (continuous numeric)[cite: 32].
* [cite_start]**Fuel Consumption Comb (L/100 km)**: Combined fuel consumption (continuous numeric)[cite: 33].
* [cite_start]**Fuel Consumption Comb (mpg)**: Combined fuel consumption in miles per gallon (integer)[cite: 34].
* [cite_start]**CO2 Emissions(g/km)**: Carbon dioxide emissions in grams per kilometer (integer)[cite: 35].

[cite_start]No missing values were found in the dataset after initial checks[cite: 46].

## Data Analysis and Modeling

### Univariate Exploratory Data Analysis (EDA)

[cite_start]Univariate EDA was performed to examine the distribution of the data, using boxplots and histograms for continuous variables, and table functions and bar plots for categorical variables[cite: 42, 43, 44].

* [cite_start]**CO2 Emissions Distribution**: The histogram of CO2 Emissions shows that the majority of vehicles emit CO2 within a middle range, with fewer vehicles having very low or very high emissions[cite: 62, 63].
    [cite_start]![Histogram of CO2 Emissions](https://raw.githubusercontent.com/your-repo/your-project/main/images/CO2_Emissions_Histogram.png) * **Fuel Consumption Distribution**: The histogram for combined fuel consumption (mpg) indicates a concentration of more fuel-efficient vehicles in the lower consumption range[cite: 78, 79].
    [cite_start]![Histogram of Fuel Consumption](https://raw.githubusercontent.com/your-repo/your-project/main/images/Fuel_Consumption_Histogram.png) * **Vehicle Class Frequencies**: The dataset includes a variety of vehicle classes such as compact, SUVs, and pickups[cite: 81].

### Bivariate Analysis

* [cite_start]**CO2 Emissions by Vehicle Class**: Boxplot analysis revealed that larger vehicle categories such as SUVs and pickup trucks are associated with higher median CO2 emissions compared to smaller vehicles like compacts and mid-sized cars[cite: 107, 108].
    [cite_start]![CO2 Emissions by Vehicle Class Boxplot](https://raw.githubusercontent.com/your-repo/your-project/main/images/CO2_Emissions_Vehicle_Class_Boxplot.png) * **CO2 Emissions vs. Fuel Consumption**: A scatterplot indicated a negative correlation between CO2 emissions and fuel efficiency (in mpg)[cite: 121, 122]. [cite_start]As CO2 emissions increase, fuel efficiency decreases[cite: 122]. [cite_start]This suggests a potential non-linear relationship[cite: 124].
    ![Scatterplot of CO2 Emissions vs Fuel Consumption](https://raw.githubusercontent.com/your-repo/your-project/main/images/CO2_Fuel_Consumption_Scatterplot.png) ### Regression Models

[cite_start]The core of the analysis involved linear regression to predict CO2 emissions[cite: 454].

#### Null Model

[cite_start]A simple linear regression model was used, calculating the average CO2 emissions with just an intercept[cite: 455]. [cite_start]The average emissions were about 250.5 grams per kilometer[cite: 127].

#### Raw Model

[cite_start]A multiple linear regression model was developed including predictors like car make, engine size, cylinders, and fuel type[cite: 457]. [cite_start]This model achieved an R-squared value of 0.9938, indicating it explained almost all the variability in CO2 emissions[cite: 137, 138]. [cite_start]The residual standard error was about 4.662[cite: 139].

* [cite_start]**Diagnostics**: Diagnostic plots for the raw model suggested issues such as potential non-linearity in the data, deviations from normality in the Q-Q plot, heteroscedasticity in the scale-location plot, and the presence of influential outliers in the residuals versus leverage plot[cite: 183, 184, 185, 186, 187].
    [cite_start]![Raw Model Diagnostics](https://raw.githubusercontent.com/your-repo/your-project/main/images/Raw_Model_Diagnostics.png) * **Actual vs Predicted**: The scatterplot showed good predictive accuracy, though accuracy diminished somewhat at higher emission levels[cite: 205, 206].
    [cite_start]![Raw Model Actual vs Predicted](https://raw.githubusercontent.com/your-repo/your-project/main/images/Raw_Model_Actual_Predicted.png) * **Multicollinearity Check**: High Variance Inflation Factor (VIF) values were observed for `Fuel Consumption City`, `Fuel Consumption Highway`, and `Combined Fuel Consumption`, indicating strong interdependence among these predictors[cite: 208, 209, 210, 211].

#### Raw Model 1 (After addressing multicollinearity)

[cite_start]To address multicollinearity, `Combined Fuel Consumption` was chosen as the sole fuel consumption variable[cite: 214]. [cite_start]This model achieved an R-squared of 0.9928 and a residual standard error of 5.009[cite: 219, 220].

* [cite_start]**Diagnostics**: Observations from the diagnostic plots suggested that assumptions of linear regression may not hold, specifically problems with non-constant variance (heteroscedasticity) and non-normally distributed residuals[cite: 266, 267].
    [cite_start]![Raw Model 1 Diagnostics](https://raw.githubusercontent.com/your-repo/your-project/main/images/Raw_Model_1_Diagnostics.png) * **Actual vs Predicted**: Deviations from the line, especially a funnel shape, suggested heteroscedasticity or that the model was not capturing all relevant factors, particularly at higher emission levels[cite: 284].
    ![Raw Model 1 Actual vs Predicted](https://raw.githubusercontent.com/your-repo/your-project/main/images/Raw_Model_1_Actual_Predicted.png) #### Clean Model 1 (After removing outliers)

Outliers were removed to improve model performance. [cite_start]This model achieved an R-squared of 0.9973[cite: 286].

* [cite_start]**Diagnostics**: Post-cleaning, the QQ plot of residuals more closely aligned with theoretical quantiles, suggesting improved adherence to normality[cite: 333]. [cite_start]The Residuals vs. Fitted plot exhibited a more random pattern, indicating better conformity with homoscedasticity and linearity assumptions[cite: 334].
    [cite_start]![Clean Model 1 Diagnostics](https://raw.githubusercontent.com/your-repo/your-project/main/images/Clean_Model_1_Diagnostics.png) * **Actual vs Predicted**: The improved alignment of points around the line of perfect fit indicated a refined model with enhanced prediction accuracy and increased explained variance in CO2 emissions[cite: 350, 351].
    ![Clean Model 1 Actual vs Predicted](https://raw.githubusercontent.com/your-repo/your-project/main/images/Clean_Model_1_Actual_Predicted.png) #### Clean Model 2 (After further data cleaning)

[cite_start]Subsequent data cleaning further refined the model, resulting in an even higher Multiple R-squared of 0.9982 [cite: 355] [cite_start]and a small residual standard error of 2.46[cite: 363].

* [cite_start]**Diagnostics**: The QQ plot showed residuals neatly following the normal line, affirming the normality assumption[cite: 403]. [cite_start]The Residuals vs. Fitted plot revealed a random scatter of points, signifying that both linearity and homoscedasticity assumptions were satisfied[cite: 404]. [cite_start]These improvements reflected a robust model[cite: 405].
    [cite_start]![Clean Model 2 Diagnostics](https://raw.githubusercontent.com/your-repo/your-project/main/images/Clean_Model_2_Diagnostics.png) * **Actual vs Predicted (Training Data)**: This plot showed a denser congregation of data points along the identity line, a clear sign of improved model accuracy post-data cleaning[cite: 420].
    [cite_start]![Clean Model 2 Actual vs Predicted Training](https://raw.githubusercontent.com/your-repo/your-project/main/images/Clean_Model_2_Actual_Predicted_Training.png) * **Actual vs Predicted (Test Data)**: The scatter plot for the test set showed a tight and consistent alignment of data points along the diagonal, indicating a strong positive correlation and high effectiveness in capturing the underlying pattern and variance in the data[cite: 436, 437]. [cite_start]This outcome signified that the predictive model adapted effectively to the test set without overfitting or underfitting[cite: 439].
    ![Clean Model 2 Actual vs Predicted Test](https://raw.githubusercontent.com/your-repo/your-project/main/images/Clean_Model_2_Actual_Predicted_Test.png) ## Main Results

[cite_start]"Clean Model 2" was identified as the best model for our chosen dataset[cite: 440].

* [cite_start]**Predictive Accuracy**: The model can very accurately predict a car's CO2 emissions, with a Multiple R-squared of 0.9982[cite: 355].
* **Key Predictors**:
    * [cite_start]The intercept suggests the starting point for CO2 emissions is around 30.88 grams per kilometer[cite: 356].
    * [cite_start]Each make of car and its specific features contributes differently to CO2 emissions; for example, having a BUGATTI increases emissions by about 4.56 grams per kilometer compared to the base level[cite: 357, 358].
    * [cite_start]Fuel consumption has a significant impact on emissions, with a 21.18 gram increase per km for every additional liter per 100 km consumed[cite: 359].
    * [cite_start]The effect of fuel type is also substantial, with electric cars (Fuel Type E) resulting in a large reduction in predicted CO2 emissions[cite: 360]. [cite_start]Fuel type, particularly types N and E, emerged as the most powerful predictors in the data[cite: 469, 473].
* [cite_start]**Model Reliability**: The model's F-statistic is extremely high, indicating the collective effect of all variables is highly significant[cite: 361]. [cite_start]Very low p-values across most predictors confirm their individual significance[cite: 362]. [cite_start]The small residual standard error (2.46) indicates that the model's predictions are very close to the actual values[cite: 363, 364].

## Statistical Methods Used

[cite_start]This comprehensive statistics project employed a variety of statistical methods to analyze a large dataset containing details of 7,385 vehicles[cite: 442, 443].

* [cite_start]**Descriptive Statistics and Histogram Analysis**: Used to summarize key features of the dataset and visually represent the distribution of CO2 emissions and combined fuel consumption, highlighting central tendency and dispersion[cite: 445, 447, 448, 449].
* [cite_start]**Scatterplot and Correlation Analysis**: Utilized to explore relationships between variables, such as the negative correlation between CO2 emissions and fuel efficiency (mpg)[cite: 450, 451, 452].
* [cite_start]**Simple and Multiple Linear Regression Models**: The core of the analysis, starting with a simple model for baseline understanding and advancing to a multiple linear regression model for prediction with high effectiveness (R-squared of 0.9938)[cite: 454, 455, 457, 458].
* [cite_start]**Diagnostic Plot Analysis**: Crucial for assessing model reliability by revealing potential issues like non-linearity, deviations from normality, heteroscedasticity, and influential outliers[cite: 459, 460].
* [cite_start]**Variance Inflation Factor (VIF) Analysis**: Included to analyze multicollinearity, with high VIF values for fuel consumption variables indicating strong interdependence among predictors[cite: 462, 463].
* [cite_start]**Model Validation and Predictive Accuracy Assessment**: Involved comparing actual versus predicted CO2 emissions through plots, showing high predictive accuracy, especially post-data cleaning[cite: 464, 465, 466].

## Conclusion

[cite_start]In conclusion, this project successfully utilized statistical methods to analyze a comprehensive dataset of 7,385 vehicles, providing valuable insights into the relationship between vehicle characteristics and environmental impact[cite: 472]. [cite_start]The analysis revealed that fuel types N and E were the most powerful predictors of CO2 emissions, underscoring the significant role of fuel choice in determining a vehicle's environmental footprint[cite: 473]. [cite_start]Through descriptive statistics, correlation analysis, and advanced regression modeling, the study not only highlighted patterns in fuel consumption and emissions but also demonstrated the intricate interplay between various vehicle attributes[cite: 474]. [cite_start]The project's findings are instrumental for automotive manufacturers and policymakers in making informed decisions aimed at reducing emissions and promoting sustainable practices in the automotive sector[cite: 475]. [cite_start]The rigorous statistical approach adopted ensures that the conclusions drawn are both reliable and applicable to real-world scenarios, contributing meaningfully to the ongoing discourse on sustainable transportation[cite: 476].
