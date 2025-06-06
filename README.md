# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of the contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. predict the cluster and plot data graphs.
5. Print the outputs and end the program.


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: V.SHREYA
RegisterNumber:  212224230266
*/
```
``` python
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("C:\\Users\\admin\\Downloads\\Mall_Customers.csv")
data.head()
data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i, init = "k-means++")
  kmeans.fit(data.iloc[:, 3:])
  wcss.append(kmeans.inertia_)
  
plt.plot(range(1, 11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c = "red", label = "cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c = "black", label = "cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c = "blue", label = "cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c = "green", label = "cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c = "magenta", label = "cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### data.head():
![image](https://github.com/user-attachments/assets/3e21dcac-04ba-41da-bff4-52ab7d2af32e)
### data.info():
![image](https://github.com/user-attachments/assets/37890483-d1cf-4cc9-9912-bb23abcd9fca)
### data.isnull():
![image](https://github.com/user-attachments/assets/38c25a5e-4b6f-497f-b3d0-da3f0ce5d044)
### elbow graph:
![image](https://github.com/user-attachments/assets/cc92f8c3-8d6a-468c-95ba-d8660519e91f)
### cluster formation:
![image](https://github.com/user-attachments/assets/205f149b-5d4d-49d6-964c-8f2271a4fd63)
### predicted value:
![image](https://github.com/user-attachments/assets/a33d7a70-e7fd-4b5b-9b24-018a9260fd74)
### final graph:
![image](https://github.com/user-attachments/assets/ab82ede2-6a10-4957-85a8-d76f36131251)







## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
