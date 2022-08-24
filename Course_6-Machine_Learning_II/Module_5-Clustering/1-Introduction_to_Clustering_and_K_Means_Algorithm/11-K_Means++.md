# K-Means++

In the previous segment, you learnt that one of the disadvantages of the K-means algorithm is that it is sensitive to centroid initialisation. A poor centroid initialisation can result in poor clustering, as shown below.  
 
![Good and Bad Clustering](https://i.ibb.co/pvC2zrZ/Good-Bad-Clustering.png)

Centroid initialisation in a cluster is one of the most important steps of the K-means algorithm. Often, a random selection of the initial centroid does not lead to an optimal solution. In order to overcome this problem, the algorithm should be run multiple times with different random initialisations. The sum of squared errors (SSE) is calculated for different initial centroids. And, the set of centroids with the minimum SSE is selected. Even though this is a very simple method, it is not foolproof. The results of multiple random cluster initialisations will depend on the data set and the number of clusters selected; however, this will not give an optimum output every time.

To choose the cluster centres smartly, you will need to use a type of centroid initialisation known as the K-Means++ algorithm. K-Means++ is just an initialisation procedure for K-means. In K-means++, you pick the initial centroids using an algorithm that tries to initialise centroids that are distant from each other. Apart from the initialisation, both algorithms work in the same way.

Let's watch the next video to understand this algorithm.

**VIDEO**

**Note**: Please note that at 1:23, the probability of any data element being selected is proportional to $d(X)^2$ and not $d(X)$

The main points about the K-means++ algorithm can be summarised as follows:

-   You choose one centre as one of the data points at random.
    
-   For each data point $X_i$, you compute the distance between $X_i$ and the nearest centre that had already been chosen.
    
-   You choose the next cluster centre using the weighted probability distribution where a point $X$ is chosen with probability proportional to $d(X)^2$
    
-   You repeat steps 2 and 3 until K centres have been chosen.
    

The K-Means++ is the default initialisation technique for the sklearn implementation of K-means (you will learn about this in the next session. This procedure will ensure that the selection is random, and the centroids are far apart. **The disadvantage of this method is that calculating the farthest point will be expensive**. In order to avoid this problem, initialisation is carried out on a subset of the data set.

In the previous segments, you learnt how to use the K-means algorithm to cluster objects. With this, you have reached the end of the session on the K-means algorithm. As part of the optional resources, you can learn about K-mode and K-prototype clustering. They are an extension of the K-means algorithm for handling categorical data.

In the next session, you will learn about the implementation of the K-means algorithm in Python for customer segmentation in an online retail store.