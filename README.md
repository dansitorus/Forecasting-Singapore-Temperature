# Forecasting Singapore Temperature
## Data Preperation 
- The original dataset was adjusted for forecasting by removing commas from numeric values using Excel's substitute function, ensuring compatibility with R. After cleaning, the dataset was imported into R using the read_excel function. The data was then transformed into a numeric format, and the "Year" column was pivoted into a long format. Subsequently, the "Data Series" column was pivoted to a wide format and ordered by year, with 1960 as the starting point. The dataset is now ready for forecasting and analysis.
