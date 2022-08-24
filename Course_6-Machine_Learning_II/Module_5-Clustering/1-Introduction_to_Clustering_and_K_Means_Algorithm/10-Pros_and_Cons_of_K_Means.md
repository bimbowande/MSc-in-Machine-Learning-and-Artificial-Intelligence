# Pros and Cons of K-Means

Now that you have developed an understanding of the various concepts about the K-means algorithms, it is now time to discuss the pros and cons of the algorithm. Let's watch the next video to learn about them in detail.

**VIDEOCho**

The pros of the K-means algorithm can be summarised as follows:

-   Compared to other clustering algorithms, the K-means algorithm is considered one of the simplest algorithms to implement.
-   One of the important properties of any machine learning algorithms is scalability. And, the K-means algorithm can be used with large as well as small data sets.
-   The K-means algorithm guarantees convergence after a number of iterations. At the point of convergence, the cost function reaches its minima and the centroids are not updated with any more iterations. Hence, if you have fixed the number of iterations and the algorithm does not converge until the final iteration, you can simply increase the number of iterations with the surety that it will converge after a certain point. 
    

The cons of the K-means algorithm can be summarised as follows:

-   **Choosing the best K**: The value of K needs to be chosen manually. In the image given below, you can observe the different clusters obtained by using different values of K. You can clearly conclude that the optimal value of K for the data set should be 3. However, the task of finding the best value of K becomes all the more difficult when you are unable to visualise the data.  
    ![Choosing the Best K](https://i.ibb.co/0VB5Sjb/Choosing-the-Best-K.png)  
     
-   **Varying cluster shapes**: The K-means algorithm works best when clusters are in the spherical shape. K-means is not suitable for all shapes, sizes and densities of clusters. If the natural clusters of a data set are vastly different from a spherical shape, then the K-means will face great difficulties in detecting them. K-means will also fail if the sizes and densities of the clusters are different by a large margin. This is mostly due to the use of the SSE as the objective function, which is more suited for spherical shapes. The SSE is not suited for clusters with non-spherical shapes and varied cluster sizes and densities. In the image shown below, you can observe the ideal clusters on the left and the clusters resulting through the K-means algorithm on the right. 
    
    ![Varying Cluster Shape](https://i.ibb.co/yXD8DYV/Varying-Cluster-Shape.png)  
     
-   **Initial centroids:** The K-means algorithm is highly dependent on the initial value of the centroids. In the three cases shown below, with a different set of initial cluster centres, you obtain three different clusters.
    
    ![Initial Centroids](https://i.ibb.co/5MYj9Mp/Initial-Centroids.png)  
     
-   **Impact of outliers:** Since the K-means algorithm tries to allocate each of the data points to one of the clusters, outliers have a serious impact on the performance of the algorithm and prevent optimal clustering.  
    ![Impact of Outliers](https://i.ibb.co/B2dHVbs/Impact-of-Outliers.png)  
      
    Considering the image given above, both datasets are the same, except the fact that the dataset on the right has a single outlier. If you observe carefully, you will realise that the addition of an outlier results in four points from Cluster A being transferred to Cluster B, resulting in erroneous clusters. Essentially, the inclusion of outliers in the dataset results in a shift in the cluster centroid, thereby changing the cluster assignment.   
     
-   **Categorical data:** The K-means algorithm cannot be used while dealing with categorical data, as the concept of distance for categorical data does not make much sense. So, instead of the K-means algorithm, you need to use different algorithms (for example, the K-modes algorithm) in the case of categorical data. You can refer to the optional segment on the K-modes algorithm to understand the internals involved in the algorithm.
    
-   **Scaling with the number of dimensions:** As the number of dimensions increases, distance-based measures such as the Euclidean distance measure converges to a constant value between any given data points. Hence, for large dimensions, it is recommended that you reduce the dimensionality using algorithms such as PCA. For a better understanding of this, refer to the additional links provided at the end of the segment.

#### K-means Algorithm

Qn: State whether the following statement is true or false.

*"If you are worried about K-means getting stuck in bad local optima, then a way to solve this problem is using multiple random initialisations."*

You can read about the local optimum and the global optimum [here](https://en.wikipedia.org/wiki/Local_optimum).

- True

- False

Ans: A. *Since each run of the K-means algorithm is independent, multiple runs can find different local optima, and this can help in choosing the global optimum value.*

#### Additional Links

1.  [Why is the Euclidean distance not a good metric in high dimensions?](https://stats.stackexchange.com/questions/99171/why-is-euclidean-distance-not-a-good-metric-in-high-dimensions)
2.  [Is the Euclidean distance meaningful for high dimensional data?](https://indico.io/blog/is-euclidean-distance-meaningful-for-high-dimensional-data/#:~:text=At%20high%20dimensions%2C%20Euclidean%20distance%20loses%20pretty%20much%20all%20meaning.&text=Basically%20once%20you%20get%20up,not%20infinity%2C%20but%20a%20constant.)