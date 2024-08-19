# Forecasting Singapore Temperature
## Data Preperation 
- The original dataset was adjusted for forecasting by removing commas from numeric values using Excel's substitute function, ensuring compatibility with R. After cleaning, the dataset was imported into R using the read_excel function. The data was then transformed into a numeric format, and the "Year" column was pivoted into a long format. Subsequently, the "Data Series" column was pivoted to a wide format and ordered by year, with 1960 as the starting point. The dataset is now ready for forecasting and analysis.
![image](https://github.com/user-attachments/assets/102eded7-247a-4d6d-aa75-5984a7afe8ef)

## Forecasting Models
- Time Series Analysis
The time series plot below highlights the trend in Singapore's average daily maximum temperature over the past 60 years. The red line indicates an upward trend, demonstrating that temperatures have increased, consistent with global warming patterns. This preliminary analysis provides a clear visual representation of the warming trend before any further data preparation.
![image](https://github.com/user-attachments/assets/2a3e0f2a-bbda-4a27-90eb-210f575dc4e8)
- Moving Average Decomposition
A 3-year moving average was applied to the time series data to smooth out daily fluctuations, reducing noise and providing a clearer view of the trend. In the plot, the red line represents the moving average, while the black line shows the raw data. The decomposition reveals periods of both decrease and increase in temperature over time. However, the recent years indicate a rising trend, possibly reflecting the impact of global warming.
![image](https://github.com/user-attachments/assets/9868e3f6-8bf5-489e-875e-cc6d025b09fd)
- Double Exponential Smoothing Model
A double exponential smoothing model was applied to the dataset due to the presence of a trend and the absence of seasonality in the annual data. This model offers a reliable short-term forecast. The red line in the plot represents the smoothed data, which effectively dampens sudden changes and spikes. Towards the end of the series, the forecasted values indicate an upward trend, aligning with the observed data pattern.
![image](https://github.com/user-attachments/assets/87606ce0-8399-4b99-b7ff-266d5f625a5a)
- ARIMA Model
Various ARIMA models were compared, and ARIMA(1,1,1) was selected as the best fit, with the lowest AIC value of 43.78. Differencing was applied with a lag of 1 to improve accuracy, as the first lag was identified as the only significant one. The ARIMA model order was confirmed using the ACF and PACF plots, ensuring the chosen model accurately captures the underlying data patterns.
![image](https://github.com/user-attachments/assets/934a15fa-2619-4820-ab1b-caa2951c841e)
![image](https://github.com/user-attachments/assets/032e38f3-7cfd-47eb-9303-7ef4ad744025)
The plot below showcases the forecasting of the next 10 years with the Arima model after the model has been checked through diagnostic in R. The red line shows the forecasted values with Arima and forecasts a steep increase followed by a gradual increase in temperature.
![image](https://github.com/user-attachments/assets/c163b801-7f14-44d9-8d6b-438e5502dcb5)

