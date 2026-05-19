# Website-Traffic-Sources-TASK-3
# NAME:MEHA MARY SAMUVEL
# DOMAIN:DATA ANALYTICS
# DURATION:4 WEEKS
# INTERN ID:CITS712
# PROJECT 3:  Website-Traffic-Sources
# INTERN PERIOD: 17TH MAY-14JUNE

# SOURCE CODE
import pandas as pd
import matplotlib.pyplot as plt

# Load dataset
df = pd.read_csv("website_traffic.csv")

# Display first rows
print(df.head())

# Dataset information
print(df.info())

# Check missing values
print(df.isnull().sum())

# Convert Date column
df['Date'] = pd.to_datetime(df['Date'])

# --------------------------------
# 1. Website Traffic Source Analysis
# --------------------------------

traffic = df.groupby('Traffic_Source')['Visitors'].sum()

traffic.plot(kind='pie', autopct='%1.1f%%')

plt.title("Website Traffic Sources")
plt.ylabel("")

plt.show()

# --------------------------------
# 2. Daily Website Visitors
# --------------------------------

daily_visitors = df.groupby('Date')['Visitors'].sum()

daily_visitors.plot(kind='line')

plt.title("Daily Website Visitors")
plt.xlabel("Date")
plt.ylabel("Visitors")

plt.show()

# --------------------------------
# 3. Device Type Analysis
# --------------------------------

device = df.groupby('Device_Type')['Visitors'].sum()

device.plot(kind='bar')

plt.title("Visitors by Device Type")
plt.xlabel("Device Type")
plt.ylabel("Visitors")

plt.show()

