# EX-08 : Implementation of K-Means Clustering for Customer Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot libraries.
2. Read the dataset and transform it.
3. Import KMeans and fit the data in the model.
4. Plot the Cluster graph.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: J.JENISHA
RegisterNumber:  212222230056
```

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
y_pred
data["cluster"] = y_pred 
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
#### data.head()
<img src="https://github.com/Jenishajustin/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119405070/7a54f201-0a1b-4ac5-92c9-5cf5ded0c468" height=200 width=500>

#### data.info()
<img src="https://github.com/Jenishajustin/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119405070/f3531a2a-6069-43eb-a342-484bf3cff02d" height=250 width=500>

#### Null values
<img src="https://github.com/Jenishajustin/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119405070/9240a003-e5be-4b82-ac8c-86ed1f3160fd" height=150 width=300>

#### Elbow Graph
<img src="https://github.com/Jenishajustin/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119405070/cab7366d-41b7-4931-ae63-4535284b8e0e" width=500 height=400>

#### Cluster formation
![image](https://github.com/Jenishajustin/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119405070/7eef56a1-4aad-4fe1-9a10-77613d66cd4e)

#### Predictions by K-means cluster 
<img src="https://github.com/Jenishajustin/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119405070/8b434376-1357-45ac-a86a-6d86a564f367" height=200 width=500>

#### Customer segements graph
<img src="https://github.com/Jenishajustin/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119405070/a057acb3-9029-4185-bd4d-d892be1140a6" width=500 height=400>

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
