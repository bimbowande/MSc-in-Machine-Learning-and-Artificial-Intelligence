# Summary

In this segment, we will summarise your learnings so far from this session.

DBSCAN stands for **D**ensity-**B**ased **S**patial **C**lustering of **A**pplications with **N**oise. Unlike the K-means algorithm, the DBSCAN algorithm does not require you to predefine the number of clusters. The fundamental idea of DBSCAN is based on the fact that clusters are dense regions in the data space, which are separated by regions of lower density.

The DBSCAN algorithm requires the user to predefine the following parameters:

1.  **Epsom, or EPS:** EPS is a distance parameter, which defines the radius of the neighbourhood to search for nearby neighbours. You can imagine each data point as the centre of a circle of radius EPS. 
2.  **Min Points or MinSamples:** Min Samples or Min Points is the minimum number of points within the EPS radius that is required to form a dense region or cluster.
    

In the DBSCAN algorithm, each point is classified into the following three categories:

-   **Core points**: All the points that have at least the minPts within their EPS distances are known as core points.
    
-   **Border points:** All the points that have at least one core point within their EPS radius are known as border points.
    
-   **Noise points**: All the points that are neither core points nor border points are called noise points.
    

The steps involved in implementing the DBSCAN algorithm are as follows:

1.  Initially, all the points are marked as unvisited. The algorithm proceeds by arbitrarily selecting a point in the data set (until all points have been visited).
2.   If the point that is selected is a core point, then we consider all the other points within its EPS radius to be part of the same cluster. If the point does not turn out to be a core point, then the algorithm will choose another point until it finds a core point.
3.  The clusters are then expanded by recursively repeating the calculation for each neighbouring point. By doing this, the algorithm clusters all the **density-connected points** together.
4.  The next step is to iterate through the remaining unvisited points in the data set. (All the points that have been assigned a cluster will be marked as visited.)
5.  For each core point, if it is not assigned to a cluster already, you need to create a new cluster.
6.  Those points that do not belong to any cluster are known as noise.

The advantages of using the DBSCAN algorithms are as follows:

-   In DBSCAN, we do not have to specify the number of clusters. 
-   DBSCAN is not sensitive to outliers and noise in the given data. In fact, it is frequently used to eliminate outliers and noise from data sets, owing to its ability to identify noise points.
-   K-means works well only when clusters are spherical in shape. DBSCAN has no such limitation.

The drawbacks of using the DBSCAN algorithm are as follows:

1.  DBSCAN cannot cluster a data set with large differences in densities.
2.  It can be difficult to choose the threshold EPS, as the data and scale vary.

EPS is a value that deals with the density of the clusters that you are trying to find. To arrive at an optimal value of this parameter, we usually perform an elbowing technique similar to the K-means algorithm for finding the optimal value of K. 

The steps for calculating the EPS value are as follows:

1.  You need to calculate the average of the distances of all the points from their k-nearest neighbours.
2.  Next, you need to sort these k-distances in ascending order. Now, you need to plot the number of points on the x-axis and the average distances that you calculated on the y-axis.
3.  Determine the ‘knee’ of the graph, which corresponds to the optimal EPS parameter.

Finally, you learnt how to perform DBSCAN in Python using the sklearn library.  The two parameters that are required to be provided by the user are EPS and MinPts or min_samples and the Python code to be used is as follows:

from sklearn.cluster import DBSCAN

```python
model = DBSCAN(eps = 0.6,  min_samples = 5).fit(dataset)
```
