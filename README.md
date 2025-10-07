# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 23.09.2025

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
import statsmodels.api as sm
from statsmodels.tsa.seasonal import seasonal_decompose

data = sm.datasets.sunspots.load_pandas().data

data.head()

decomposition = seasonal_decompose(data['SUNACTIVITY'], model='additive',period=12)

plt.figure(figsize=(10, 12))
plt.subplot(411)
plt.plot(data['SUNACTIVITY'], label='Sun Activity')
plt.legend(loc='upper left')
plt.title('Sun Activity')

plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()

```
### OUTPUT:

PLOTTING THE DATA:
<img width="1164" height="346" alt="image" src="https://github.com/user-attachments/assets/def8223d-555c-45a2-9e42-4a9a163ce670" />

SEASONAL PLOT REPRESENTATION :
<img width="1163" height="342" alt="image" src="https://github.com/user-attachments/assets/3aec5d5e-7261-4763-909c-0c9a7d95e9ea" />

TREND PLOT REPRESENTATION :
<img width="1157" height="319" alt="image" src="https://github.com/user-attachments/assets/9483d66d-b419-45de-b70f-a69fa78534a0" />

OVERALL REPRESENTATION:
<img width="1161" height="337" alt="image" src="https://github.com/user-attachments/assets/851b8003-8fcd-4183-895d-dc443439183e" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
