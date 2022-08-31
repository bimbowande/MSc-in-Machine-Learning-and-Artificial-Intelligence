# EPS and MinPts

As you learnt in the previous segment, DBSCAN is a density-based clustering algorithm that divides a data set into subgroups of high-density regions. DBSCAN groups the points that are close to each other based on two parameters, a distance measurement (usually the Euclidean distance) and the minimum number of points. The points that lie in the low-density region are marked as outliers by the algorithm.

The DBSCAN algorithm requires the following parameters:

1.  Epsom, or EPS, and
2.  Min Points or MinSamples.
    

In the upcoming video, you will learn about these two parameters in detail.

**VIDEO**

In the video above, you learnt about the two parameters that are crucial while using the DBSCAN algorithm: EPS and Min Points.

## **EPS**

EPS is a distance parameter, which defines the radius of the neighbourhood to search for nearby neighbours. You can imagine each data point as the centre of a circle of radius EPS. 

The value of EPS that is chosen to cluster the data has a significant impact on the results. If the value of EPS is too small, then decidedly fewer data points will be considered in one cluster and a large part of the data will remain unclustered. The unclustered data points will be marked as outliers because they do not fulfil the number of points that are required to create a dense region. If the EPS value chosen is very high, then no real clusters will be formed, as all of the clusters will be merged in the same cluster. The EPS value should be chosen based on the distance of the data set (we can use a k-distance graph to find this distance), but in general, small EPS values are preferable.

## **Min Points**

Min Samples or Min Points is the minimum number of points within the EPS radius that is required to form a dense region or cluster. For example, if you set min_samples as 5, then you need at least 5 points to form a dense cluster. 

Minimum points can be selected from certain dimensions (D) in the data set. As a general rule, min points >= D + 1. 

In the next segment, you will learn how DBSCAN uses these parameters to characterise data points into the following three categories: **core points, border points and noise points**. You will learn about these points in detail in the next segment.

#### Min Points

Qn: How is the density of a point p defined in density-based clustering?

- MinPts minus number of data points in an epsilon-neighbourhood

- Number of data points in an epsilon-neighbourhood of p

- Reciprocal value of the distance from p to the nearest neighbour

Ans: B. *Minpts is defined as the minimum number of points within the EPS radius.*
