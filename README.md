# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required packages.
2. Import the dataset to work on.
3. From sklearn module import kmeans.
4. Define number of clusters to be made.
5. Assign the cluster values.
6. Plot the cluster using matplotlib.pyplot.
7. End the program.
## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: S.Kishore
RegisterNumber:  212222240050

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import kMeans
wcss=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of clusters")
plt.ylabel("wcss")
plt.title("elbow method")
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
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="red",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
## data.head() function :
![image](https://github.com/Kishore2o/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118679883/515c2fcf-42a1-41ad-a775-dce8422c55e4)
## data.info()
![image](https://github.com/Kishore2o/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118679883/a1b2ece3-e688-4814-835c-cb56a06737e8)
## data.isnull().sum() function
![image](https://github.com/Kishore2o/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118679883/a52254d9-e8c0-4344-82f0-0104a118ab95)
## Elbow method Graph
![image](https://github.com/Kishore2o/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118679883/ae7413ef-e47d-4a53-82c7-eaa3732437a7)
##  KMeans clusters
![image](https://github.com/Kishore2o/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118679883/ebb6a58c-66cb-4d3a-a137-8e66edf9374f)
## Customer segments Graph
![image](https://github.com/Kishore2o/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118679883/0f438e41-bf92-4f0a-b8de-fa13e35b67cc)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
