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

# OUTPUT
<img width="790" height="299" alt="Image" src="https://github.com/user-attachments/assets/483478c4-6344-4e67-981f-dcf5caf04108" />
<img width="725" height="167" alt="Image" src="https://github.com/user-attachments/assets/85f39a41-d0ad-478c-b5bb-bc50d6a596b7" />
<img width="852" height="326" alt="Image" src="https://github.com/user-attachments/assets/662dc9cb-5f07-467f-a71b-515deb052d24" />
<img width="1054" height="521" alt="Image" src="https://github.com/user-attachments/assets/736562c7-a8c0-4c90-a49e-da266a10250e" />
<img width="672" height="308" alt="Image" src="https://github.com/user-attachments/assets/c73c116b-6453-471d-b978-d2952a018230" />
<img width="965" height="622" alt="Image" src="https://github.com/user-attachments/assets/c522b847-c1b2-4528-a3e6-4aa755d2568e" />
<img width="794" height="309" alt="Image" src="https://github.com/user-attachments/assets/d043066d-85bc-4768-b53a-632e18caadee" />
<img width="1074" height="635" alt="Image" src="https://github.com/user-attachments/assets/846078a3-3a9b-4591-a34c-89d4debb669d" />

