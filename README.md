# TSA-Ex-5
# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION



### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.


Dataset used: ice_cream

Software Required: Google colab



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

# Step 1: Load the dataset
data = pd.read_csv(
    '/content/ice_cream.csv',
    parse_dates=['DATE'],
    index_col='DATE'
)

data.head()

# Step 2: Perform seasonal decomposition
decomposition = seasonal_decompose(
    data['IPN31152N'],
    model='additive',
    period=12
)

# Step 3: Plot the decomposition
plt.figure(figsize=(10, 12))

# Original Data
plt.subplot(411)
plt.plot(data['IPN31152N'], label='Ice Cream Data')
plt.legend(loc='upper left')
plt.title('Original Ice Cream Data')

# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()
```


### OUTPUT:

<img width="1362" height="1008" alt="image" src="https://github.com/user-attachments/assets/e7703195-177b-46b0-b6ad-e3f6b659f0bb" />


<img width="1384" height="343" alt="image" src="https://github.com/user-attachments/assets/37daad17-2a84-4e8c-bded-15f1023cd84a" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
