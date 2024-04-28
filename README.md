# EX 08 Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:

To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:

1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import pandas and matplotlib.pyplot

2.Read the dataset and transform it

3.Import KMeans and fit the data in the model

4.Plot the Cluster graph

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Dhivyapriya.R
RegisterNumber:  212222230032

```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:

### data.head() function:

![image](https://github.com/dhivyapriyar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477552/022ae6d2-85b7-4c44-92e2-c72d2d6ed450)

### data.info():

![image](https://github.com/dhivyapriyar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477552/7aa31596-1206-42e4-84dd-4f65d5e11d66)

### data.isnull().sum():

![image](https://github.com/dhivyapriyar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477552/acc959c7-1499-4d6c-b5b4-a393d8116a02)

### Elbow Method Graph:

![image](https://github.com/dhivyapriyar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477552/0c9fd14c-6701-479b-9ff7-905c129d32f4)

### KMeans Clusters:

![image](https://github.com/dhivyapriyar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477552/c6382403-4a9c-4d69-974e-4ac821dacbd7)

### y-pred:

![image](https://github.com/dhivyapriyar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477552/ee8b6134-5831-4d7d-a3e5-075ef3d0518a)

### Customer Segment Graph:

![image](https://github.com/dhivyapriyar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477552/9b126ca3-cb24-4fa5-a205-d3736b85b7bf)

## Result:

Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
