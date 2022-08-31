# Bisecting K-Means

In this segment, you will learn about the bisecting K-means algorithm, which is a form of hierarchical clustering. Bisecting K-means is a hybrid of divisive hierarchical clustering and K-means clustering.

A major disadvantage of HAC algorithms is its large time complexity. A large time complexity arises due to the creating and updating process of the distance matrix. Although bisecting K-means is a type of divisive clustering, it avoids the formation of a distance matrix. The runtime of bisecting K-means is better than that of agglomerative hierarchical clustering techniques, which makes it suitable for big data processing.

The Spark ML library comes with an inbuilt implementation of the [bisecting K-means](http://spark.apache.org/docs/latest/ml-clustering.html#bisecting-k-means) algorithm.  In order to build a BisectingKMeans model, you need to create an object of the BisectingKmeans class first and then fit the training data to generate your model as shown in the code snippet below.

```python
# Trains a bisecting k-means model.
bkm = BisectingKMeans().setK(2).setSeed(1)
model = bkm.fit(dataset)

# Make predictions
predictions = model.transform(dataset)
```

Let's watch the next video to learn more about the bisecting K-means algorithm.

**VIDEO**

There are two types of hierarchical clustering. In the previous segments, you studied Agglomerative Clustering in depth. The other type of clustering is called **Divisive Clustering**, which is the **opposite of agglomerative clustering**. In this type, all the data objects are considered as a **single cluster**. In each step, the algorithm **splits the cluster**. This is repeated until only single data points remain, which are considered as singleton clusters.

In the video above, you learnt about a variant of the Divisive Clustering algorithm known as Bisecting K-means. The steps involved in implementing the bisecting K-means algorithm are as follows:

-   You need to set all data points to a single cluster.
    
-   Using K = 2, you need to create two subclusters.
    
-   Next, you need to measure the intra-cluster distance for both the clusters.
    
-   The algorithm selects the clusters with the highest intra-cluster distance as the next clusters to be broken.
    
-   The algorithm further breaks the selected cluster into two subclusters using K-means.
    
-   The algorithm keeps repeating the aforementioned steps until all the observations become individual clusters.
    

**Why is bisecting K-means more efficient than K-means for large data sets?**

For the K-means algorithm, the computation involves all the data points of the data set and k centroids. On the other hand, in each step of bisecting K-means, only the data points of one cluster and two centroids are involved in the computation. Thus, the computation time is reduced.