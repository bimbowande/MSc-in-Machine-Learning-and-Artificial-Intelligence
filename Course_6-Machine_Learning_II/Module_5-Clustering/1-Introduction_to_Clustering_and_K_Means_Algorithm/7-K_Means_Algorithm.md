# K-Means Algorithm

In the previous segments, you got a basic idea of the concept of clustering. You learnt about the various applications of clustering, the different types of clustering models and the common distance measures used in building a clustering model. In the upcoming segments, you will learn about one of the most popular partitioning clustering algorithms known as the k-means algorithm.

Before understanding how the k-means algorithm works, it is important for you to understand the underlying idea of centroids. If you recall your high school geometry, you will remember that centroids are essentially the centre points of triangles that best represent a triangle, or in other words, in a triangular object, the distribution of its mass is best represented by its centroid. Similarly, in the case of clustering, centroids are the centre points of the clusters that are being formed. In the next video, you will learn how to calculate the centroid value for a certain cluster.

**VIDEO**

As you saw in the video above, the centroid value in the case of clustering is essentially the mean of all the observations that belong to a particular cluster. For example, considering the data set given in the video.

![K-Means Data Sample](https://i.ibb.co/61GZG8G/K-Means-Data-Sample.jpg)

The centroid is calculated by computing the mean of each and every column/dimension that you have, and then arranging them in order in the same way as shown above.

You will obtain the following values for the data represented above:

1. $\text{Mean of Height}=\dfrac{(175+165+183+172)}{4}=173.75$
2. $\text{Mean of Weight}=\dfrac{(83+74+98+80)}{4}=83.75$
3. $\text{Mean of Age}=\dfrac{(22+25+24+24)}{4}=23.75$

Thus, the centroid of the aforementioned group of observations is (173.75, 83.75 and 23.75).

#### Centroid Calculation

Qn: Find the centroid of the five observations given in the table below.

| X   | Y   | Z   |
| --- | --- | --- |
| 12  | 23  | 45  |
| 31  | 31  | 31  |
| 17  | 15  | 25  |
| 19  | 27  | 45  |
| 13  | 11  | 27  |

- 18.4, 21.4, 32.1

- 34.6, 21.4, 18.4

- 18.4, 21.4, 34.6

- 21.4, 32.1, 18.4

Ans: C. *For computing the centroids, you have to compute the mean of columns X, Y and Z each for all the five observations. On calculating the values, the answer is [18.4, 21.4, 34.6].*

Now that you have understood the concept of cluster centroid, let's start exploring the algorithm in detail. If you recall from the previous segments, partition-based or centroid-based clustering algorithms have the following properties:

- The number of clusters is predefined and identified as K.

- The distance between the data point and the cluster centroid decides the membership to a centroid.

K-means is a centroid-based algorithm, wherein we calculate the distances to assign a point to a cluster, and each cluster is associated with a centroid. Let's watch the next video to learn about this in detail.

**VIDEO**

In the video above, learnt that the algorithm involves two important steps, which are as follows. 

1. **Assignment Step**: Assign each observation Xi to the closest cluster centroid μk.
2. **Optimisation Step**: Update each centroid to the mean of the points assigned to it.

Now that you are aware of the two critical steps in the algorithm, let's take look at a working example to understand the algorithm better.

## Working example of K-means

In the next video, you will look at a practical example. Given a set of points (1, 1), (2, 1), (1,2), (3,4) and,(4,3), you need to form clusters using the k-means algorithm. The graph given below is a two-dimensional representation of the points in the XY coordinate plane.

![Working Example K-Means](https://i.ibb.co/r76txxX/Working-Example-K-Means.jpg)

**VIDEO**

Let’s quickly reiterate the steps of K Means and find the clusters for this data set.

**Assignment step:** 

Let P1(1,1) and P2(4,3) (randomly chosen) be the initial centroids to build your clusters. Now, let’s compute the Euclidean distances from the chosen centroids.

The distance from (3,4) to the centroid (1,1) equals the following: 

$d=\sqrt{(1−3)^2+(1−4)^2}=3.606$

Similarly, computing other distances, you will get the values given in the table below.

| Points | Distance from P2(1, 1) | Distance from P2(4, 3) |
| ------ | ---------------------- | ---------------------- |
| (1, 1) | 0                      | 3.605                  |
| (1, 2) | 1                      | 3.162                  |
| (2, 1) | 1                      | 2.828                  |
| (3, 4) | 3.605                  | 1.414                  |
| (4, 3) | 3.605                  | 0                      |

The points (1, 1), (1, 2) and (2, 1) are closer to the centroid (1, 1), so these form one cluster (C1),

and the points (3, 4) and (4, 3) are assigned to the centroid (4, 3), so they form another cluster(C2).

**Optimisation step:**

Here, you need to recompute a new centroid based on the points in your cluster. The new centroids for Cluster(C1) and Cluster(C2) would be as follows:

|           | Points                 | Centroid Calculation     | Centroid     |
| --------- | ---------------------- | ------------------------ | ------------ |
| Cluster 1 | (1, 1), (1, 2), (2, 1) | $(1+1+2)/3$, $(1+2+1)/3$ | (1.33, 1.33) |
| Cluster 2 | (3, 4), (4, 3)         | $(3+4)/2$, $(4+3)/2$     | (3.5, 3.5)   |

Now that you have obtained the new clusters' centroids, you need to perform the assignment step again in the second iteration.

| Points | Distance from P2(1.33, 1.33) | Distance from P2(3.5, 3.5) |
| ------ | ---------------------------- | -------------------------- |
| (1, 1) | 0.46                         | 3.53                       |
| (1, 2) | 0.74                         | 2.91                       |
| (2, 1) | 0.74                         | 2.91                       |
| (3, 4) | 3.15                         | 0.71                       |
| (4, 3) | 3.15                         | 0.71                       |

The points (1, 1), (1, 2) and (2, 1) are closer to the centroid (1.33, 1.33), so they now form one cluster C1, and the points (3, 4) and (4, 3) being closer to (3.5, 3.5) form another cluster(C2).

At this step, you stop the algorithm, as the points no longer get reassigned, and the centroid remains the same. So, these are the final clusters.

## Steps of the algorithm

Let’s go through all the steps involved in this algorithm. To use the algorithm, you will first need to state the number of clusters ‘K' that will be present in our result. 

- The algorithm first selects K objects randomly to act as initial cluster centres. These objects are called cluster centroids or means. 

- Next, you need to assign the remaining objects to their closest centroids. The Euclidean distance between the cluster centroids and the objects determines their proximity.

- After you assign the objects to their respective centroids, the algorithm calculates the mean value of the clusters. 

- After this re-computation, you recheck the observations to determine whether or not they might be closer to a different cluster. Then, you need to reassign the objects to the centroids accordingly. 

- You need to keep repeating these steps until the assigning of clusters stops. This means that you need to stop repeating the iterations when the clusters that are formed in an iteration are the same as those in their previous iteration.

So, how do we know if the k-means algorithm has converged? Ideally, if the assignment of points to cluster centroids in the last two consequent iterations are same, then the algorithm is considered to have converged. At this point, we can conclude that the k-means algorithm has come to a stop, as the points remain in the same cluster, and the clusters at hand are the final optimal clusters. 

You can observe the k-means algorithm in action using a visualisation tool. This tool can be found on [Visualizing K-Means Clustering](https://www.naftaliharris.com/blog/visualizing-k-means-clustering/). You can refer to this link and play around with the different options available to get an intuitive understanding of the k-means algorithm.

In the next segment, you will gain an understanding of the k-means cost function and learn how to compute the cost function for each iteration in the k-means algorithm.

#### K-means Algorithm

Qn: Arrange the following steps of the k-means algorithm in the order in which they occur:

1. Randomly select the cluster centroids.

2. Update the cluster centroids iteratively.

3. Assign the cluster points to their nearest centre.
- 1-2-3

- 1-3-2

- 2-1-3

- 3-1-2

Ans: B. *First, the cluster centres are pre-decided. Next, all the points are assigned to their nearest cluster centre, and then, the centre is recalculated as the mean of all the points that fall in that cluster. Finally, clustering is repeated with the new centres, and the centres are updated according to the new cluster points.*

Qn: Assume that you have a dataset on which you are applying the K-means algorithm with K-random initial centroids. For different sets of the initially chosen centroids, will the algorithm converge in the same number of iterations?

- Yes

- No

Ans: B. *There is no guarantee that the K-means algorithm will always converge after a fixed number of iterations. The number of iterations is dependent on the choice of the initial centroids.*

Qn: State whether the following statement is true or false.

*"Given different initializations to the K-means for a data set, the K-means will always converge to the same set of clusters."*

- True

- False

Ans: B. *Given different initializations to the K-means for a data set, the K-means need not form the same set of clusters. For example, the K-means algorithm can return different clusters for different initialization of centroids.*

Qn: In this exercise, you will perform K-means clustering manually on a small data set. Consider the data set with two features and six observations given in the table below.

| Observation Number | X1  | X2  |
|:------------------:|:---:|:---:|
| 1                  | 1   | 4   |
| 2                  | 1   | 3   |
| 3                  | 0   | 4   |
| 4                  | 5   | 1   |
| 5                  | 6   | 2   |
| 6                  | 4   | 0   |

Use k = 2 for the entire exercise.

1. Choose the first two observations as your initial cluster centroids.

2. Assign each observation to the centroid to which it is closest (using euclidean distance). Report the new cluster labels for each observation.

3. Recompute the cluster centroid on the basis of the points assigned to the cluster

4. Repeat all the steps until the clusters stop changing.

 The observations (identified by their row numbers) belonging to the final  two clusters, respectively, are _______.

- (1, 3, 5) and (2, 4, 6)

- (1, 5, 6) and (2, 3, 4)

- (1, 2, 3) and (4, 5, 6)

- (1, 3, 4) and (2, 5, 6)

Ans: C. *You will notice that the solution converges after two iterations. After the first one, observations 1 and 3 are clustered together and observations 2, 4, 5 and 6 are clustered together. By the end of the second iteration, observations 1, 2 and 3 are clustered together and observations 4, 5 and 6 are clustered together. If you run another iteration, the assignment of the points does not change, and the new cluster centroids remain the same. Hence, you can consider these as the final clusters and terminate the algorithm.*

