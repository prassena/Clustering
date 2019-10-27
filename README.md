# Clustering

Clustering is a unsupervised learning technique ,where labeling each data point is time consuming and difficult we use clustering technique.
In this we Applying Different Clustering Techniques on Doners choose dataset.

Clustering is a technique of grouping data points based on similarity.
To evaluate two model which one is good,we should calcuating (min inter cluster distance)/(max inta cluster distance) which ever model gives higher value is the best model.

In this i have applied 3 widly used clustering technique:

>K-Mean clustering

>Hierarchical clustering

>DBSCAN 

# K-Mean Clustering:
this is a centroid based clustering Technique.
In this K in K-Mean is number of cluster to be formed .so their will be K centroid one for each cluster and k set of point (points belong to each cluster),no point will belong to two cluster.
the loss we minimize here is sum of difference between centroid and the point belonging to that centroid should be low.This is a hard to solve problem.so to simplify it they came up with Lloyd's algorithm.
1.Randomly initilize k data points as centroids.
2.Assign each point to its nearst centroid .
3.Compute new centroid from the data points assigned to each cluster .
4.Reassign the data points to new centroid.
5.Repeat step 3 and 4 till their is no significant change between old and new centroids.

As the k mean clustering is sensitive to centroid initilization ,their emerged new technique called K-Mean++.the only difference here is initilization of centroid .

here we randomly pick one point from dataset and compute the distance between that point and all other points in dataset.
then select second point in such a way that probablity of selecting the point is high when the distance is high,this is to avoid the selection of outlier point as the next point.now compute the distance between data point and the selected points . then take the minimum distance and sort them ,select next point using probablity approch do this till you get k number of cluster .

The K-Mean cluster will cluster points with roughly same number of points in each cluster 

# Hierarchical clustering:
There are 2 approch in Hierarchical clustering - Agglomerative and Divisive based approch.

Agglomerative : Agglomerative clustering uses a bottom-up approach, wherein each data point starts in its own cluster. These clusters are then joined greedily, by taking the two most similar clusters together and merging them.

Divisive: Divisive clustering uses a top-down approach, wherein all data points start in the same cluster.

All this Hierarchical division or combining is captured in a graph called dendrogram.x axis is data points y axis is distance between cluster.From the dendogram we can come to conclusion how many clusters need to be formed .when their is no clustering happening for very long distance then we can conclude number of clusters to be formed .

# DBSCAN :
There are 2 hyper paramater here eps and min points.

when their is min num of points in eps radius from a point ,then the point is called core point .

When the point is not a core point but if it is a neibhour of core point then it is called border point .

If the point is neither core or border point is noise point.

Density-connected A point "p" and "q" are said to be density connected if there exist a point "r" which has min number of points in its neighbors and both the points "p" and "q" are within the epi distance. This is chaining process. So, if "q" is neighbor of "r", "r" is neighbor of "s", "s" is neighbor of "t" which in turn is neighbor of "p" implies that "q" is neighbor of "p".

If the core point is not assigned to a cluster then make a new cluster with the core point and its density connected point.Assign the border point to its nearest core point .here we dont want to give number of clusters need to be formed .

# Facing error while loading IPYNB "Sorry, something went wrong. Reload?"
please click the following link https://nbviewer.jupyter.org/github/prassena/Clustering-/blob/master/Clustering.ipynb
