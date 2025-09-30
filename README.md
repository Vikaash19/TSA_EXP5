# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 23.9.2025
### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv("gold.csv")
decomposition = seasonal_decompose(data["Close"], model="additive", period=12)

plt.figure(figsize=(10, 12))
plt.subplot(411)
plt.plot(data["Close"], label="Gold Price (Close)")
plt.legend(loc="upper left")
plt.title("Gold Price Time Series")

plt.subplot(412)
plt.plot(decomposition.trend, label="Trend", color="orange")
plt.legend(loc="upper left")
plt.title("Trend Plot")

plt.subplot(413)
plt.plot(decomposition.seasonal, label="Seasonal", color="green")
plt.legend(loc="upper left")
plt.title("Seasonality Plot")

plt.subplot(414)
plt.plot(decomposition.resid, label="Residual", color="red")
plt.legend(loc="upper left")
plt.title("Residual Plot")

plt.tight_layout()
plt.show()
```
### OUTPUT:
PLOTTING THE DATA:
<img width="1247" height="378" alt="1 original" src="https://github.com/user-attachments/assets/0fe2c6bc-7a9e-4297-b700-1522876ae6a1" />

TREND PLOT REPRESENTATION :
<img width="1238" height="372" alt="2 trend" src="https://github.com/user-attachments/assets/5afa29b8-abca-45f5-a5f0-4f531ebd30f7" />

SEASONAL PLOT REPRESENTATION :
<img width="1237" height="368" alt="3 seasonal" src="https://github.com/user-attachments/assets/3c4b1886-0e02-425c-bb3a-7f3d73e20f59" />

RESIDUAL PLOT REPRESENTATION:
<img width="1220" height="372" alt="4 residual" src="https://github.com/user-attachments/assets/a81668ba-b0d6-4c3f-955e-e3a55720673f" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
