# Kovai.co-DS-Task

INSIGHTS:
insight 1:
the rapid route has the highest number of passengers on average each day. this means most people prefer using rapid routes for their daily travel, so it’s important to keep these routes well managed and reliable to meet people’s needs.

insight 2:
the rapid route and local route have the highest passenger counts, showing that these services are the most widely used by the public. in contrast, peak service and school routes have much lower ridership, meaning they are used only by a smaller group or during specific times. this suggests that most daily travel depends on rapid and local routes, so keeping these routes frequent and reliable should be the main focus.

insight 3:
weekday ridership is much higher than weekend ridership across all services, especially for rapid route and local route. this means most people use public transport mainly for work, school, and daily commuting, while travel demand drops noticeably on weekends.

insight 4:
there is a strong positive relationship between local route, light rail, and rapid route, meaning when one of these services gets more passengers, the others usually do too.
this suggests that people often use these services together or that they serve similar travel needs, showing a connected travel pattern across the main routes.

insight 5:
the rapid route and local route consistently have the highest number of passengers, while peak service stays very low throughout.
there are noticeable drops in ridership at certain months, likely due to holidays or external factors, followed by steady recoveries.
this means most people rely on rapid and local routes for regular travel, and these services play the main role in overall transport demand.

MODEL PARAMETERS:

1️ Data Understanding and Preparation
The dataset contains historical passenger counts for multiple transport service types — Local Route, Light Rail, Peak Service, Rapid Route, and School. Each record includes the travel date and the corresponding number of passengers. Data preprocessing involved cleaning missing values, removing duplicates, and converting date columns to the proper datetime format. The data was then grouped by service type and aggregated into daily time series to prepare for model training.

2️ Stationarity Check
For time series forecasting, the data must be stationary, meaning the mean and variance remain constant over time. To verify this, the Augmented Dickey-Fuller (ADF) test was performed for each service type.
•	If the p-value > 0.05, the data was considered non-stationary.
•	First-order differencing was applied to make the series stationary.
•	After differencing, all series became stationary and ready for ARIMA modeling. This ensured that the ARIMA model’s statistical assumptions were satisfied for each service.

3️ Model Selection – ARIMA
The ARIMA (Auto-Regressive Integrated Moving Average) model was selected for forecasting passenger trends because it effectively models non-seasonal time series.
The model parameters are:
•	p (Auto-Regressive term): accounts for the influence of past values.
•	d (Integrated term): represents the order of differencing applied to achieve stationarity.
•	q (Moving Average term): captures the impact of past forecast errors.
After experimentation, ARIMA(1,1,1) was chosen as the best configuration, providing stable and interpretable results for all service types.

4️ Model Training and Forecasting
Separate ARIMA models were trained for each transport service:
•	Local Route
•	Light Rail
•	Peak Service
•	Rapid Route
•	School
Each model was fitted using historical passenger count data and used to forecast passenger journeys for the next 7 days.
The model also generated confidence intervals, showing the upper and lower bounds of expected passenger numbers.
This enabled short-term, data-driven forecasting for each route, improving planning and operational efficiency.

5️ Insights
•	Passenger volume showed clear short-term fluctuations across all routes.
•	Rapid Route and Light Rail consistently had higher passenger volumes, indicating higher mobility in urban corridors.
•	Peak Service displayed sharper variations, aligning with commuter travel behavior.
•	School routes showed predictable weekday-based demand patterns.
•	The ARIMA predictions provided stable and realistic short-term forecasts, useful for operational planning.

6️ Result
The final ARIMA models successfully produced accurate 7-day forecasts for all transport services.
These forecasts help transport authorities anticipate changes in passenger demand and plan accordingly.
Outcome: Reliable short-term forecasts for all service categories using ARIMA(1,1,1).
Application: Supports transport scheduling, fleet management, and decision-making with data-driven insights.

<img width="451" height="686" alt="image" src="https://github.com/user-attachments/assets/1f1cbce8-0751-454b-b909-806ae25af013" />

<img width="451" height="483" alt="image" src="https://github.com/user-attachments/assets/32adb2a9-eeae-458e-95d8-df1bc0cd8ef2" />
