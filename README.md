# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print head,info of the dataset
2.check for null values 
3.Import kmeans and fit it to the dataset 
4.Plot the graph using elbow method 
5.Print the predicted array
6.Plot the customer segments
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: R.PRIYANGA
RegisterNumber: 212223230161 
*/
```



```

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

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

plt.xlabel("No_of_Clusters")

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

plt.title("Customer Segment")

```


## Output:

## DATA.HEAD():

![image](https://github.com/user-attachments/assets/d6cdf6b7-efd0-4d8d-883f-f4a709c5f124)    
## DATA.INFO():

![image](https://github.com/user-attachments/assets/57d7b52b-4aff-4d96-a044-80686c643e20)

## DATA.ISNULL().SUM()

![image](https://github.com/user-attachments/assets/3c8fafd3-eeb2-4b86-b7c4-c88b94da89f8)

## PLOT USING ELBOW METHOD:

![image](https://github.com/user-attachments/assets/5b254ed0-f772-4fe6-9e1f-487b47ad31c6)

## 5.K-MEANS CLUSTERING:

![image](https://github.com/user-attachments/assets/3cf440b0-2081-4a93-a13b-f32f4aac3e94)

##  6.Y_PRED ARRAY:

![image](https://github.com/user-attachments/assets/a4435f08-9c06-4232-a0f9-d4d3f53862f9)

## CUSTOMER SEGMENT:

![image](https://github.com/user-attachments/assets/1fbcb79e-bcae-4783-b100-a8bdc011322e)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
