# Clustering-Algorithms-in-PySpark

This repository contains the implementation of the k-means and k-means++ algorithms from scratch in PySpark.

The k-means (and its improvement, the k-means++) algorithm is an unsupervised learning method
that is used to identify naturally occurring homogeneous subgroups (clusters) in the data, in 
the absence of a target variable. These clusters are determined through an iterative process,
such that the distance of the points within a cluster is minimized and the distance between 
clusters is maximized. These distances between points/cluster centers were calculated using both the
Euclidean and Manhattan distance calculation methods. The algorithm is said to have converged when 
when the value of a cost function (sum of squared distances) reaches its minimum.

The number of clusters was fixed at ten, for both versions of the algorithm.

In the k-means approach, ten random data points were assigned the role of initial cluster centers.
The k-means algorithm used these ten data points as the starting point, and iteratively assigned
data points to clusters, based on the condition that hte distance between the 

The k-means algorithm progressed as follows:
1. Ten random data points were picked from the data, and assigned the role of initial cluster centers.
2. With the initial cluster centers as starting points, the rest of the data points were assigned to
   the cluster whose center was closest to the data point (both Euclidean and Manhattan distances were
   used). Each data point could be assigned to one cluster only.
3. After all the data points were assigned appropriate clusters, the new center of each cluster was determined
   by calculating the centroid of the data points in the cluster (including the initial centroid).
4. The cost function was calculated at each iteration as the sum of the squares of each data point's
   distance (Euclidean/Manhattan) from the center of the cluster that it was a member of.
5. Steps 1 through 4 took place on an iterative basis, until 20 iterations were reached.
6. On plotting the cost function against the number of iterations, the cost function seemed to
   drop in value to a minimum, after which it seemed to stay constant, for the remnant of the iterations. 
   At this minimum, the algorithm is believed to have converged. The cluster that a data point belonged to 
   at the corresponding iteration, was considered the cluster that the data point was the final member of.

The k-means++ algorithm followed the steps above in an almost identical fashion, except for one 
minor adjustment. Where all the initial cluster centers were picked from the data at random on the
k-means approach, in the k-means++ approach, only the first cluster center was picked at random from 
the data. All the other centers were picked by identifying the farthest data point from all other
cluster centers. Once the ten initial cluster centers were determined, steps 1 - 6 listed above were
used to reach convergence, following which cluster membership became easy to determine.

The final result of the project was the identifying of the cluster that a data point belonged to, based on how
similar it was to the other data points in the cluster, and how different it was from the data points in the 
other clusters.


