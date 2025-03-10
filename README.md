# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
```
import pandas as pd
import numpy as np
df=pd.read_csv("Superstore.csv")

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

#4.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#5.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#6.Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

#7.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#8.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()              

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
```
# OUPUT
![81](https://user-images.githubusercontent.com/93427253/171038819-35e99928-5e79-4045-ad4a-acf466d17776.png)
## Data Visualization Using Seaborn:
![one](https://user-images.githubusercontent.com/93427253/171088126-d9789627-424b-492c-bb2b-b3e20b321c97.png)
![8one2](https://user-images.githubusercontent.com/93427253/171087530-76851f17-5e09-4f5c-8a2d-4034370f0319.png)
![8two1](https://user-images.githubusercontent.com/93427253/171087550-da3c1477-79f7-4505-9347-730740f29926.png)
![8two2](https://user-images.githubusercontent.com/93427253/171087565-bab9ec2d-51bb-4856-8d3a-12dd77ecde35.png)
![8three](https://user-images.githubusercontent.com/93427253/171087578-2d98f730-1ec1-4d49-9769-1cdd8e985d3e.png)
![8four](https://user-images.githubusercontent.com/93427253/171087595-57690d40-ee26-4621-8961-e709e9690fdc.png)
![8four2](https://user-images.githubusercontent.com/93427253/171087614-2c2c621c-6d39-405b-ae9d-3ebad1ad26e1.png)
![8five](https://user-images.githubusercontent.com/93427253/171087626-cb71493c-3d72-471a-885f-5cc3f0072920.png)
![8five2](https://user-images.githubusercontent.com/93427253/171087640-a7ee345d-c767-4c36-8568-6e1721978785.png)
![88](https://user-images.githubusercontent.com/93427253/171039117-1f54432f-3ea6-4583-adb0-d7ccd802cf0a.png)
![89](https://user-images.githubusercontent.com/93427253/171039123-35069435-4de6-4d10-9c38-83f819549c7a.png)
## Data Visualization Using Matplotlib:
![90](https://user-images.githubusercontent.com/93427253/171039171-f8efac90-b63b-4053-b7d8-cb00a75f76ec.png)
![91](https://user-images.githubusercontent.com/93427253/171039187-47e635f3-1fe5-44f7-a125-4d4b4b586b47.png)
![92](https://user-images.githubusercontent.com/93427253/171039214-c379c324-c7ee-4aa1-9209-1f60bf550507.png)
![93](https://user-images.githubusercontent.com/93427253/171039238-52e1daac-6b87-434a-bf04-5f42555a9e9e.png)
![94](https://user-images.githubusercontent.com/93427253/171039263-795f2f2b-8992-45e8-977b-fc2ad43c96a0.png)
![95](https://user-images.githubusercontent.com/93427253/171039282-3361382d-b612-4632-8b17-49863e11d496.png)

# RESULT
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
