# Hierarchical Clustering in Python

In this segment, we will use the same online retail case study and data set that we used for the K-means algorithm. We will use the hierarchical algorithm for creating customer segments.

We will start at the point where we have completed the data preparation process and have the RFM data set in place, which has been treated for missing values and outliers and is also standardised.

The two basic steps involved in hierarchical clustering are as follows:

-   Creating the dendrogram, and
    
-   Cutting the dendrogram at an appropriate level. 
    

**VIDEO**

Now, in the next video, we will use the single linkage method to cluster the data set.

**VIDEO**

As you saw in the video above, the single linkage method did not produce a satisfactory result for us to analyse the clusters. So, in the next video, we will use the complete linkage method and analyse the clusters once again.

P**VIDEO**

As you saw in the video above, after we obtained the ClusterIDs for each customer, we appended the obtained ClusterIDs to the RFM data set and analysed the characteristics of each cluster to derive business insights from the different customer segments (or clusters), in the same way as we did in the K-means algorithm.

As you learnt in the previous segment, the hierarchical clustering algorithm is not suitable for large data sets, owing to its large time complexity. The Spark MLLib contains a version of hierarchical clustering known as **Bisecting K-means**. Bisecting K-means is a hybrid of the hierarchical divisive clustering and K-means methods, thereby earning the name **Bisecting K-means**. In the next segment, you will learn about the bisecting K-means algorithm in detail.