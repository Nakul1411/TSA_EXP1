# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 02.02.2026

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("chocosales.csv")
df.head()
df.columns
df['Date'] = pd.to_datetime(df['Date'], dayfirst=True)
df.head()df.columns
df['Date'] = pd.to_datetime(df['Date'], dayfirst=True)
df['Amount'] = df['Amount'].replace({'\$': '', ',': ''}, regex=True).astype(float)
mean_amount = df['Amount'].mean()
print("Mean Sales Amount:", mean_amount)
monthly_sales = df.resample('M', on='Date')['Amount'].mean()

import matplotlib.pyplot as plt
plt.figure()
plt.plot(monthly_sales)
plt.xlabel("Month")
plt.ylabel("Average Sales Amount")
plt.title("Monthly Chocolate Sales")
plt.show()
yearly_sales = df.resample('Y', on='Date')['Amount'].mean()

plt.figure()
plt.plot(yearly_sales)
plt.xlabel("Year")
plt.ylabel("Average Sales Amount")
plt.title("Yearly Chocolate Sales")
plt.show()

```
# OUTPUT:
<img width="1293" height="581" alt="image" src="https://github.com/user-attachments/assets/4ce8fd09-c64a-4438-83a6-c1f2c4b57b18" />
<img width="1251" height="601" alt="image" src="https://github.com/user-attachments/assets/584ecd0c-706e-4f2f-aa1e-b83ea33dc0f5" />


# RESULT:
Thus we have created the python code for plotting the time series of given data.
