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
df.head()df['Date'] = pd.to_datetime(df['Date'], dayfirst=True)
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
<img width="1218" height="587" alt="image" src="https://github.com/user-attachments/assets/c1b2803d-1ef9-415d-a8f4-55abb92d1c28" />
<img width="1277" height="622" alt="image" src="https://github.com/user-attachments/assets/631855e9-72d6-471b-b81c-ea68edd3fac0" />

# RESULT:
Thus we have created the python code for plotting the time series of given data.
