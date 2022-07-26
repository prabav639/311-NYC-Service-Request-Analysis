# 311 NYC Service Request Analysis and Time Series Forecasting

## About the data: 

311 NYC Services receives non-emergency calls from people in the particular city like Noise complaints, Driveway blocks, Rodent
issues etc. These requests are reported at 311 and based on the issue, the request will be forwarded to the concerned department like NYPD, HPD
etc. The calls data is publicly available and can be downloaded from:

https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9

The data consists of features like Unique_number (1 Unique_numbe is considered as 1 complaint), Timestamp of complaint recorded, Complaint_type, Agency (Department), incident_zip and borough available for the year 2016. The data was preprocessed and cleaned for preparing the data for analysis.

The analysis also includes weather data from different cities like New York, Vancouver etc. I have aggregated the weather data for New York as city 
attributes, temperature, humidity, pressure, wind speed, wind description. The weather data is publicly available and can be downloaded from:

https://www.kaggle.com/selfishgene/historical-hourly-weather-data

## Problem Statement:

In our analysis I have tried to gain insights about the call patterns, departments received the most calls etc., and forecast the inbound call counts
for the next day.

## Insights: 

The insights gained are:

1. Heat/Hot water has been the most reported complaint
2. Brooklyn borough reported the most complaints
3. Heat/ Hot water complaint was the most reported from Brooklyn
4. New York Police Department (NYPD) received the most complaints
5. Noise/Residential complaint was the most reported at NYPD
6. January month received the maximum complaints
7. Heat/Hot water complaint was the most reported when the Temperature fell below 0 Celsius

## Approach:

After aggregation and merging of dataframes, I am performing a correlation to find the relationship of weather in the number of calls and Granger-Causality test to check for causality inference of weather on Call counts.

After obtaining results for correlation and granger causality, I was able to understand that the correlation is weak and has very less impact.

After feature engineering, I have divided the data into training and test data of 280 days and 90 days (includes 5 days of synthetic samples)

I have fed the training data into the model to forecast the future values and the Time Series Forecasting models implemented are:

1) ARIMA (Auto-regressive Integrated Moving Average)
2) Prophet model by Facebook

Finally, I have evaluated the models using the Scikit learn's metrics:
1) MAPE (Mean Absolute Percentage Error)
2) MAE (Mean Absolute Error)
