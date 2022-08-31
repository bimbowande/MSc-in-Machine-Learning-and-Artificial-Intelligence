# Pros and Cons of Hierarchical Clustering

In this segment, you will learn about the pros and cons of hierarchical clustering. Let's watch the next video to learn about this in detail.

**VIDEO**

The advantages and disadvantages of hierarchical clustering can be summarised as follows:

**Advantages**

-   Unlike the K-means algorithm, you **do not need to specify the number of clusters** at the beginning of the algorithm.
    
-   Compared to other clustering algorithms, hierarchical clustering algorithms are relatively **simple to implement**.
    
-   Dendrograms are useful in **visualising the data as well as the clusters** formed after cutting the dendrogram.
    

**Disadvantages**

-   **Final merging decisions:** Merging decisions, once given by the algorithm, cannot be undone at a later point in time.
    
-   **Time and space complexity:** Hierarchical clustering algorithms are quite time-consuming, as they involve continuous calculation and updating of the distance matrix, which itself is a very complex operation. The time and space complexity of agglomerative clustering is higher than K-means clustering, and in some cases, it is prohibitive.
    
-   **Dendrograms**: Building dendrograms for large data sets is quite difficult. The dendrogram given below is obtained from a data set of mere 700 points. You can imagine the complexity of building a dendrogram if the data set is scaled to about a million points.  
    ![Dendogram Hierarchical Clustering](https://i.ibb.co/9vmKxWB/Dendogram-Hierarchical-Clustering.png)  
     
    
-   **Objective function:** The SSE is the objective function for K-means. Similarly, there is no global objective function for hierarchical clustering. The algorithm considers proximity locally before merging two clusters.
    

**Note**: The running time of the hierarchical clustering algorithm is O(n3); hence, the algorithm is suitable for small data sets only. The Spark ML library does not support the implementation of this agglomerative clustering approach.

#### Hierarchical Clustering

Qn: Is the following statement is true?

*"Agglomerative clustering algorithms build clusters by collecting all the data points in a single cluster. At every step, they divide each cluster into smaller clusters for a specific number of steps."*

- No

- Yes

Ans: A. *This is incorrect. The algorithm given above is a divisive algorithm that repeatedly divides the clusters, whereas agglomerative clustering algorithms build the clusters from the bottom.*

Qn: While clustering using the hierarchical algorithm approach, at a particular step, you need to calculate the distances between different points in the cluster. Considering you have N points in the cluster, what is the time and space complexity of this step?

To read more about time and space complexity visit [link1](https://en.wikipedia.org/wiki/Time_complexity) and [link2](https://en.wiktionary.org/wiki/space_complexity)

- $N^2,\ N$

- $N,\ N$

- $N^3,\ N^2$

- $N,\ N^2$

Ans: C. *During the computation of the matrix, you calculate the distance of each point to every other point, hence the time complexity comes out to be $O(N^3)$. You then store this matrix so that you can use it at a later stage of the algorithm. This matrix occupies a space of $O(N^2)$.*

With this, we have reached the end of the theory part on Hierarchical Clustering. In the next segment, we will continue using the Online Customer Retail problem to form meaningful clusters.