# Summary

With this, you reached the end of this session. Now, let's summarise your learnings from this session.

Given a set of N items to be clustered, the steps involved in hierarchical clustering are as follows: 

-   Calculate the NxN distance (similarity) matrix, which will give you the distance between a certain data point and other data points. 
-   Start by assigning each item to its own cluster such that if you have N items, you have N clusters each containing just one item. 
-   Find the closest (most similar) pair of clusters and merge them into a single cluster so that you have one less cluster.
-   Compute the distances (similarities) between the new cluster and each of the old clusters. 
-   Repeat steps 3 and 4 until all the items are clustered into a single cluster of size N. 

By now, you have the dendrogram ready. It shows which data points are grouped together in which cluster and at what distance. Once you have the dendrogram prepared, the clusters can be obtained by cutting the dendrogram at an appropriate level. The number of vertical lines intersecting the cutting line represents the number of clusters.

Determining the number of groups is often the primary goal of cluster analysis. Typically, you are supposed to look for natural groupings that are defined by long stems.

You also learnt that hierarchical clustering can proceed in two ways: agglomerative and divisive. If you are starting with n distinct clusters and iteratively reach a point where you end up with only one cluster, then the process is called agglomerative clustering. On the other hand, if you begin with one big cluster and subsequently keep partitioning the cluster until you reach n clusters each containing one element, then the process is called divisive clustering.

You learnt about three types of linkages, which are as follows:

**Single linkage:** Here, the distance between two clusters is defined as the shortest distance between the points in the two clusters.

**Complete linkage:** Here, the distance between two clusters is defined as the maximum distance between any two points in the clusters.

**Average linkage:** Here, the distance between two clusters is defined as the average distance between every point of one cluster and every other point of the other cluster.

Next, you learnt about the advantages and disadvantages of hierarchical clustering, which are as follows:

Advantages

-   We do not need to specify the number of clusters at the beginning of the algorithm.
    
-   It is easy to implement. 
    
-   A dendrogram is useful in visualising data.
    

Disadvantages

-   You cannot undo the previous step, i.e., the decision made upstream cannot be changed.
    
-   Time complexity can result in long computation times.
    
-   Using dendrograms for large data sets is quite difficult.
    

Next, you learnt about a hybrid algorithm known as **Bisecting K-means**. The steps involved in this method are as follows:

-   You need to set all data points to a single cluster.
    
-   Using K = 2, you need to create two subclusters.
    
-   You need to measure the intra-cluster distance for both these clusters.
    
-   The algorithm selects the clusters with the highest intra-cluster distance as the next cluster to be broken.
    
-   The algorithm further breaks the cluster into two subclusters using K-means.
    
-   The above-mentioned steps are repeated until all observations become individual clusters.
    

Finally, you learnt about the differences between the K-means algorithm and the hierarchical clustering algorithm and also learnt how these methods are used in the industry.