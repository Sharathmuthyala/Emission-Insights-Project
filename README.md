Emission Insights: Analyzing CO2 Emissions in Vehicles Using R

Overview

This project presents a detailed analysis of a comprehensive dataset on various vehicles, exploring the relationship between car features and environmental impact, specifically focusing on CO2 emissions. The study categorizes cars by brand, model, and type, and examines specifics like engine size, transmission, and fuel consumption in urban and highway settings. Through statistical methods, patterns are discerned, revealing correlations between vehicle attributes and fuel efficiency. The findings are essential for manufacturers aiming to develop cars that align with consumer preferences and environmental standards, providing a foundation for future vehicle innovation and sustainable practices.

Environmental Context

CO2 emissions significantly contribute to the greenhouse effect, leading to global warming and various adverse effects such as rising global temperatures, sea-level rise, changes in weather patterns, and ecosystem disruptions. Reducing CO2 emissions is crucial for mitigating climate change and minimizing its harmful effects. This project aims to quantify the environmental impact of different vehicle types, which is critical in the current context of growing environmental concerns.

Project Goal

The primary goal of this project is to create a sophisticated predictive model that accurately forecasts CO2 emissions from vehicles. This model utilizes a rich dataset encompassing various vehicle characteristics such as make, model, engine size, number of cylinders, type of transmission, and fuel consumption metrics. By analyzing and understanding the correlations between these variables and CO2 emissions, the project endeavors to provide valuable insights into how automobile design and consumer choices can be optimized for lower carbon footprints.

Data Description

The dataset used for this analysis includes 7,385 vehicles with the following attributes:
	•	Make: The brand of the vehicle (e.g., ACURA).
	•	Model: Specific model of the vehicle (e.g., ILX).
	•	Vehicle.Class: The category of the vehicle (e.g., COMPACT, SUV - SMALL).
	•	Engine.Size.L.: The size of the engine in liters (continuous numeric).
	•	Cylinders: The number of cylinders in the engine (integer).
	•	Transmission: Type of transmission (e.g., M6, AV7).
	•	Fuel Type: Type of fuel used (e.g., Z).
	•	Fuel Consumption City (L/100 km): Fuel consumption in city (continuous numeric).
	•	Fuel Consumption Hwy (L/100 km): Fuel consumption on the highway (continuous numeric).
	•	Fuel Consumption Comb (L/100 km): Combined fuel consumption (continuous numeric).
	•	Fuel Consumption Comb (mpg): Combined fuel consumption in miles per gallon (integer).
	•	CO2 Emissions(g/km): Carbon dioxide emissions in grams per kilometer (integer).

No missing values were found in the dataset after initial checks.
