# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Start the program

2.Import the necessary python libraries

3.Read the dataset of Mall_Customers csv file

4.From sklearn libraary select the cluster and import KMeans Clustering

5.Find the sum of squared distance between each points and the centroid in a cluster using Elbow Method

6.Plot the graph x and y as Number of Clusters and wcss respectively

7.Using the matplotlib library draw the scatter plot for the given number of clusters (ie. here n_clusters = 5)

8.Stop the program

## Program:

Program to implement the K Means Clustering for Customer Segmentation.

Developed by: THIRISHA.S

RegisterNumber:  212222230160

```python
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
data["cluster"] = y_pred

df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="olive",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="orange",label="cluster4")
```
## Output:

# Data Head:

<img width="290" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121222763/fe89920e-ea7b-433c-a804-744f6c0d543c">


# Checking For Null Data:

<img width="132" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121222763/9e10a520-2922-423a-88d1-5d54e01a7f52">


# Data Information:

<img width="231" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121222763/45f5a105-2030-4289-8ff7-0c29f99d800c">


# Elbow Method Graph:

<img width="303" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121222763/0a3669e3-b245-4fd4-9c28-0625950daabc">

# K-means Cluster:

<img width="92" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121222763/c3e2d07b-d27a-44cd-9d21-faaa863fe79f">


# Customer Segments Graph:
 
<img width="288" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121222763/e5927521-25c7-493e-9a0f-fedd06680d31">



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
