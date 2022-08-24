# Cost Function

Now that you are aware of the different steps involved in the algorithm, let’s learn about the cost function associated with this algorithm. In the previous modules, you learnt that the objective of any machine learning algorithm is to minimise its corresponding cost function. In the next video, you will understand the cost function for the k-means algorithm.

**VIDEO**

In the video above, you learnt that the cost function for the K-means algorithm is mathematically given by the **Sum of squared errors (SSE)**, which is as follows:
$$\Large J=\sum^n_{i=1}||Xi−\mu_{k(i)}||^2=\sum^K_{K=1}\sum_{i\epsilon c_k}||X_i−\mu_k||^2$$
The Euclidean distance is calculated from each data point to its nearest centroid. These distances are squared and summed to obtain the SSE. This type of distance is also known as intracluster or within-cluster distance and can be visualised using the image given below.

![Intra-Cluster Distance](https://i.ibb.co/j6kKYx6/Intra-Cluster-Distance.png)

Essentially, the cost function tries to minimise the SSE (i.e., the intra-cluster sum of distances), and by minimising the cost function, the K-means algorithm aims to form clusters of data points that are similar to each other. Note that the SSE considers all the clusters formed using the K-means algorithm.

With every iteration, the centroids get updated in such a way that the cost function is minimised. The iteration stops when the maximum number of iterations is reached, or the change of the within-cluster sum of squares in two successive iterations is less than the threshold value. The updated cluster centres for the last iteration are known as the Final Cluster Centres.

## Mathematical Representation of Assignment and Optimisation Step

In the assignment step, you assign every data point to K clusters. The algorithm goes through each of the data points, and depending on the cluster that is closer, it assigns the data points to one of the closest cluster centroids.

Let's assume that Xi represents the ith observation in the data set. As you have already learnt, in the assignment step, we assign each point to the closest centroid. So, if we have K clusters, then we can assign points to cluster numbers 0, 1, 2..K, as shown in the table below.

![Clustering Sample Table](https://i.ibb.co/jgmSBqZ/Clustering-Sample-Table.png)

Now for each observation, $i$, we want to mathematically represent the cluster that the point will be assigned to, based on the closest distance. This equation for the assignment step can be represented as follows:
$$\Large Z_i=argmin_k||X_i−\mu_k||^2$$
**Note**: argmin refers to the index of the minimum element in an array. You can understand this concept better by referring to NumPy's argmin function given [here](https://numpy.org/doc/stable/reference/generated/numpy.argmin.html). 

So, let's take a look at an example to understand this equation better. Suppose we are given K = 3, and the centroid values are $\mu_1\ (0,\ 4)$, $\mu_2\ (0,\ 0)$, $\mu_3\ (4,\ 0)$, and we want to assign the point Xi(1, 1) to one of these centroids, as shown below.  
![Centroid Sample Graph](https://i.ibb.co/sjGfs9M/Centroid-Sample-Graph.png)

In order to assign the point to one of the centroids, we first calculate the distance of the point to each centroid, as shown in the table below, and create the following distance matrix:

![Centroid Sample Table 1](https://i.ibb.co/F0QC4g1/Centroid-Sample-Table1.png)

From the table above, it is clear that point $X_i$ should be assigned to  $\mu_2$. However, since we want our equation to return the cluster number, we have added the argmin function, which automatically returns the cluster number(index) whose distance value is the least. Had we not used the argmin function (or used min function instead), the equation would only return the minimum distance, which would not be of much use.

So, for the example given above, the argmin function would return the value of 2 (assuming the index values start from 1 and not 0). Hence, we can update the table by adding that the point has been assigned to cluster number 2.

![Centroid Sample Table 2](https://i.ibb.co/vDj082D/Centroid-Sample-Table2.png)

By performing this computation for all the observations, you store only the values of $X_i$ and their respective $Z_i$ values (cluster number).

After completing the assignment step, you proceed to the optimisation step, wherein the algorithm computes the new cluster centroids. In the optimisation step, the algorithm calculates the average of all the points in a cluster and moves the centroid to that average location.

Once we have all the points for each cluster, we can directly compute the new centroid values using the following equation:
 $$\mu_k=\dfrac{1}{n_k}\sum_{i:z_i=k}X_i$$
Hence, for $K=2$, you can calculate the centroid for only those observations for which $Z_i=k=2$. Similarly, you can compute the other centroids by iterating over different values of K.

The process of assignment and optimisation is repeated until there is no change in the clusters, which essentially implies that the algorithm has converged.