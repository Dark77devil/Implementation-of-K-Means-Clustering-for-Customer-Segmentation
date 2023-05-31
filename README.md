# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

~~~
1.Import pandas and matplot libraries.
2.import Kmeans algorithm to solve customer segmentation.
3.Using the for loop cluster the given data
4.Predict the output and plot data graphs.
5.Display the output

~~~

## Program:

Program to implement the K Means Clustering for Customer Segmentation.  
Developed by: M.MANO  
RegisterNumber: 212221040100 

```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Dataset-20230524.zip")
data

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
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```



## Output:


DATA.HEAD():

![image](https://github.com/Dark77devil/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/115543366/496e4fa5-eae0-4056-b287-f56ae12bf7f3)  




DATA.info():


![image](https://github.com/Dark77devil/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/115543366/88b65222-8868-46ef-8733-914327ba87fa)  





NULL VALUES:


![image](https://github.com/Dark77devil/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/115543366/e79a2011-6708-4b48-8129-c8215e97b5d4)  




ELBOW GRAPH:


![image](https://github.com/Dark77devil/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/115543366/cefec210-b79e-44e0-bcca-d0f856df9edd)  





CLUSTER FORMATION:


![image](https://github.com/Dark77devil/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/115543366/1c6fb8d4-16ec-4cda-8d15-5db780260121)  





PREDICICTED VALUE:


![image](https://github.com/Dark77devil/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/115543366/d7476df0-5cd4-4144-bb11-138733e10c6a)  





FINAL GRAPH(D/O):




![image](https://github.com/Dark77devil/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/115543366/04265ccf-4587-441c-bb08-6e3d0bfd3fb5)  



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
