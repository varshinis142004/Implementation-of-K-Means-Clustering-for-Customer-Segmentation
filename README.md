# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step 1. Start the program

Step 2. Import the necessary python libraries

Step 3. Read the dataset of Mall_Customers csv file

Step 4. From sklearn libraary select the cluster and import KMeans Clustering

Step 5. Find the sum of squared distance between each points and the centroid in a cluster using Elbow Method

Step 6. Plot the graph x and y as Number of Clusters and wcss respectively

Step 7. Using the matplotlib library draw the scatter plot for the given number of clusters (ie. here n_clusters = 5)

Step 8. Stop the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: VARSHINI S
RegisterNumber: 212222220056
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("C:/Users/admin/Downloads/printed pdfs/Mall_Customers.csv")

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
plt.xlabel("No of Cluster")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

KMeans(n_clusters=5)

y_pred = km.predict(data.iloc[:,3:])
y_pred


data["cluster"]=y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
## head :
![image](https://github.com/user-attachments/assets/e1d8328a-0ac9-45ee-bc33-c686b77ead99)

## Info :
![image](https://github.com/user-attachments/assets/bd2d38f4-4ed4-4532-bb00-d9463c10b8d3)

## No.of Null-Values :
![image](https://github.com/user-attachments/assets/a849602f-d3e3-4ead-9d3d-f08a841400db)

## Graph:
![image](https://github.com/user-attachments/assets/154cef8e-c91c-44dc-972c-274630f3a75e)

## No.of clusters :
![image](https://github.com/user-attachments/assets/bbd7ca4e-a52a-48b2-bfe2-f1bd4cc369be)

## Predicted values :
![image](https://github.com/user-attachments/assets/e53b1ffc-bfdc-4773-ae38-ec3d45fe1273)

## Customer Segments :
![image](https://github.com/user-attachments/assets/e22ff6e8-9ebb-44a5-a9bf-2ed1a5a36a4c)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
