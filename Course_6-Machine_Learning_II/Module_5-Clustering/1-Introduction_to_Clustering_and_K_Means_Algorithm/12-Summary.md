# Summary

In this segment, we will summarise your learnings from this session. First, you developed an understanding of the concept of clustering and learnt about the various practical applications of clustering. In clustering, a group of different data objects is classified as similar objects. One group refers to a cluster of data. Data sets are divided into different groups in the cluster analysis, which is based on the similarity of the data.

Some of the applications of clustering are as follows:

-   Clustering is used in many areas, including market research, pattern recognition and image processing.
    
-   In the e-commerce industry, clustering is used to identify different segments of customers within the customer base. The characteristics/profiles of these customer clusters are used to devise cluster-specific marketing campaigns.
    
-   In the banking industry, clustering is used for detecting outliers within the customer base. It can help in various use cases, such as loyalty tiering and fraud.
    
-   Clustering is used in data mining to understand the distribution of data, and get specific insights into different clusters.
    
-   In the telecom industry, clustering is used to identify network congestion within specific markets. It helps in estimating the capacity for network expansion.
    

Clustering can either be hard or soft. All clustering algorithms can be broadly divided into the following methods.

-   Partition clustering
    
-   Hierarchical clustering
    
-   Density-based clustering
    
-   Fuzzy clustering
    

The three different types of classical distance measures are as follows:

-   Manhattan distance
    
-   Euclidean distance
    
-   Minkowski distance
    

You also learnt that outliers have an impact on clusters, and thus, outlier-infested data may not give you the most optimal clusters. Similarly, since the most common measure of distance is the Euclidean distance, you need to bring all the attributes to a common scale using standardisation.

Finally, you learnt about the Hopkins statistic, which is used to evaluate the clustering tendency of a dataset. A high Hopkins statistic indicates that the data is highly clusterable and good clusters can be formed, and vice versa.

As is evident, cluster analysis is a highly valuable method, no matter which language or environment it is implemented in. Whether you want to derive insights, eke out patterns or carve out profiles, cluster analysis is a highly useful tool and provides results that can be practically implemented. Proficiency in working with the various clustering algorithms can enable you to perform accurate and truly valuable data analysis.

In the second half of the session, you learnt about one of the most popular partitioning algorithms known as the K-means algorithm. You gained an understanding of the K-means intuitively by grouping 26 random points in two clusters.

The algorithm begins by choosing K random cluster centres. Next, the two steps, assignment and optimisation, continue iteratively until the clusters stop updating. This gives you the most optimal clusters, that is, those with a minimum intra-cluster distance and a maximum inter-cluster distance.

You also learnt about the K-means cost function, which is given by the following equation:
$$\Large J=\sum^n_{i=1}||Xi−\mu_{k(i)}||^2=\sum^K_{K=1}\sum_{i\epsilon c_k}||X_i−\mu_k||^2$$
Next, you learnt about the following two methods that are used to find the optimal value of K:

-   Elbow method
    
-   Silhouette method
    

Further, you learnt about the pros and cons of K-means, which can be summarised as follows:

**Pros**

-   It is relatively simple to implement.
    
-   It scales to large data sets.
    
-   It guarantees convergence.
    

**Cons**

-   You need to choose the K value manually.
    
-   The final clusters depend on the initial value of the centroids. Hence, the K-means algorithm is non-deterministic. This means that the final outcome of clustering can be different each time the algorithm is run,  even when it is run on the same data set. 
    
-   Outliers have an impact on clusters, and thus, outlier-infested data may not give you the most optimal clusters. Similarly, since the most common measure of the distance is the Euclidean distance, you need to bring all the attributes into the same scale using standardisation.
    
-   You cannot use categorical data for the K-means algorithm. Other customised algorithms are available for such categorical data.
    
-   As the number of dimensions increases, distance-based measures, such as the Euclidean distance measure, converge to a constant value between any given data points. Hence K-means does not work well with data with high dimensionality.
    

Finally, you learnt about the K-means++ algorithm. In the K-means++ algorithm, you pick the initial centroids using an algorithm that tries to initialise centroids that are farthest from each other. Apart from the initialisation, both the algorithms work in the same way.