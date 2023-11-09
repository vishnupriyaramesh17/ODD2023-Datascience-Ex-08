# Ex-08-Data-Visualization-
# AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Clean the Data Set using Data Cleaning Process

## STEP 3
Apply Feature generation and selection techniques to all the features of the data set

## STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
### inserting libraries
```
import pandas as pd
import seaborn as sns
from matplotlib import pyplot as plt
df=pd.read_csv("/content/Superstore - Superstore.csv (1).csv")
df.head()
df.info()
df.isnull().sum()
```
## Data Visualization using seaborn
### lineplot
```
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

sns.lineplot(x='Ship Mode', y='Category',hue="Segment",data=df)
plt.title("Multiline Plot")
plt.show()
```

### barplot
```
sns.barplot(x="Category",y="Sales",data=df)

sns.barplot(x='Region', y='Sales', data=df,palette='Set1')
plt.title("Sales in different Regions")
plt.show()
```
### scatter plot
```
sns.scatterplot(x='Category',y='Sub-Category',data=df)
plt.title("Scatterplot")
plt.show()

sns.scatterplot(x='Category',y='Sub-Category',hue='Segment',data=df)
plt.show()
```
### box plot
```
sns.boxplot(x="Sub-Category",y="Discount",data=df)
plt.xticks(rotation=90)

sns.boxplot( x="Profit", y="Category",data=df)
```

### pointplot
```
sns.pointplot(x=df["Quantity"],y=df["Discount"])
```
### violinplot
```
sns.violinplot(x="Profit",data=df)
```
### countplot
```
sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)
plt.xticks(rotation=90)
```
### histogram
```
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
```
### KDEplot
```
sns.kdeplot(x="Discount", data = df,hue='Category')
```
## Data Visualization using Matplotlib
### plot
```
plt.plot(df['Region'], df['Sales'])
plt.show()
```
### Heatmap
```
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
```
### piechart
```
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
```
### Histogram
```
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="black",bins=10)
plt.xticks(rotation =90)
plt.show()
```
### barplot
```
plt.bar(df['Category'],df.index)
plt.show()
```
### scatterplot
```
plt.scatter(df["Region"],df["Profit"], c ="red")
plt.show() 
```
### boxplot
```
plt.boxplot(x="Sales",data=df)
plt.show()
```
# OUTPUT:
### Initial data:
![279990103-0d5ba5f2-444f-46af-aeee-f6732b7d8290](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/806543eb-30c7-4d67-89d3-a98ee4568f17)


### Data information:
![279990295-bbf5145e-72ef-4ec0-abaa-1f5fdf7dda31](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/965851e1-a8b1-4982-a0f4-8ed840f892c7)


### Null values:
![279990633-248e390a-386a-4bac-aa93-fe04edc0b152](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/88c35595-d142-4a4a-af6e-765314a2a2d6)


## Data visualization using Seaborn
### Lineplot:
![279991163-b8f46101-7341-403f-a5e4-377a241442ba](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/f458d5c6-3ee6-41cf-9b27-767c19ec942b)
![279991351-712d4eed-6dad-4a27-9b0b-01d4eaf8b3d4](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/8f301755-072a-4b01-b4b0-a6a541148976)



### Barchart:
![279991696-1ae3c2c6-0ea8-4606-a8b0-4710616c49c5](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/f43d2f4f-5cec-4507-8e2f-973a0f72d31c)
![279991783-bec47d50-f269-4dd7-9e2b-86338bddf814](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/a6f54502-3b44-4a2b-b3a5-d5540b29065b)

### Scatterplot:
![279991965-9109b9d6-3703-4796-9615-e9b9110d44c8](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/c47b4535-9f62-48c4-9227-425d5da66159)
![279992150-5ad3e3a2-4057-410b-ac42-08f3d1131416](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/27373a3b-c959-4e5f-99ce-4cf8ffa6bb6f)

### Boxplot:
![279992811-88106430-bfb4-4fa9-92aa-74bdc60a8c8d](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/8506d5a8-07ac-449b-88c0-222faf6da536)
![279992918-08f2de62-e096-4a6c-8f1f-8c6c2d7ff690](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/040e0579-d590-49be-96a2-a6e15900dae5)

### Pointplot:
![279993110-af9f7bf3-617f-4743-b88f-484a7e46c41a](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/189862e1-1815-4105-ab71-3b362012ea13)

### Violinplot:
![279993313-92a139bf-d99b-474f-a517-f51b1ebdd542](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/dee8a629-fb6e-48c5-8ef8-50e7315ecc8d)

### Countplot:
![279993522-47c060f3-c05a-4c7c-914a-dbd88d85ae78](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/80a1e3a1-9fa2-4093-9eed-75ceb02c30da)

### Histogram:
![279993762-c39bd74a-a42f-4f7c-943b-78c8fee66961](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/7046d7cf-163e-471f-a18e-36022dbcbda9)
![279993908-ddbbf630-5680-4179-938d-b56e07eb26a0](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/767ebbce-ca91-4587-98f0-7a2014d59a34)

### KDEplot:
![279994069-0e39ae85-c901-4508-a3a7-8b91c34edf95](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/ab6d3635-e4ad-4e29-b1dd-32bed1b10b7f)

## Data visualization using Matplot
### Plot:
![279994691-23304f05-423f-463f-81ea-4d09076637c6](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/d3cb5a16-263c-41cd-800c-2f3f53780472)

### Heatmap:
![279994904-07ff67be-f7ae-4eaa-9520-c926705583b5](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/983a7b2c-6bdf-4e59-80eb-5e01943c501b)

### Piechart:
![279995078-99beb450-b262-4a3e-a7d1-d88980c78f17](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/98f78800-4ddd-4cb0-b82d-d3bfe40a5dfa)
![279995203-2ee148e7-cc79-4039-bdf0-4fe0555b81d1](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/52d58f26-bd53-44f9-8778-ef0a38b984db)

### Histogram:
![5d20a2ab-09b5-4ed0-ab0d-1a5e013a5b6a](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/648324dd-b50d-46de-b9e6-fa3236b9e661)

### Barplot:
![279995913-cb5899b5-a43b-40af-884c-5bd7056c3f1e](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/73853754-75a3-4084-aff7-37369a08fd05)

### Scatterplot:
![279996084-afeb8364-a4da-457f-916e-d326f92ef741](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/881f2169-b103-4e5e-bc38-80bf021c9c81)

### Boxplot:
![279996328-ee388fcb-f049-4aca-9f9b-a191ff35e6fc](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-08/assets/119393589/7a2ddeed-f217-4469-afd3-14358593b1c5)

# Result :
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.




