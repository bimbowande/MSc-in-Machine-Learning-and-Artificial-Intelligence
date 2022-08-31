# Optimal K

How can we determine what value of K to use to get the optimal clusters?

So far, you have learnt about the different steps of the algorithm and also the cost function of the algorithm. If you observe the steps of the algorithm carefully, you will realise that one of the important steps in k-means clustering is defining the value of K. But how do we decide this value? You will find the answer to this question in this segment. Determining the value of K is a fundamental problem in K-means. The following two methods can help in identifying the correct value of K:

- Elbow method

- Silhouette method  
   

## Elbow Method

Let’s watch the next video to learn about the Elbow method.

**VIDEO**

The fundamental idea of clustering is to define the clusters in order to minimise the total intra-cluster distance (distance within the cluster sum of squares). The elbow method uses the same distance to find the optimal value of K. The steps involved in the Elbow method can be broadly broken down into three steps, which are as follows:

- **Calculate the Within-Cluster Sum of Squares (WCSS) for different values of K**  
  The Within-Cluster Sum of Squares (WCSS) measures the squared average distance between all the points within a cluster to the cluster centroid. The WCSS for K = 2 for a certain cluster cab be represented as follows:
  
  ![Within-Cluster Sum of Squares](https://i.ibb.co/p3fcLDP/Within-Cluster-Sum-of-Squares.png)  
   

- Create a plot with the WCSS on the y-axis and the number of clusters on the x-axis.

- Choose the value of K at which the curve begins to flatten, as shown in the graph below. This point is known as the Elbow point. Essentially, the elbow point represents the value of K at which the addition of clusters does not improve the WCSS.  
   
  
  ![Elbow Method for Optimal K](https://i.ibb.co/k1Th20P/Elbow-Method-for-Optimal-K.png)  
   

## Silhouette Method

This method is used to determine the K value and is known as the Silhouette method. Let's watch the next video to learn more about this method.

**VIDEO**

The Silhouette method measures the extent of similarity of the point with its own cluster compared with the nearest cluster. The range of this measure is between -1 and 1.  
$$\Large S(i)=\dfrac{b(i)−a(i)}{max(b(i),\ a(i))}$$
For a point $x_i$,

$b(i)$ = Average distance between a point and the points in the next closest cluster

$a(i)$ = Average distance between a point and other points within the cluster

| Silhouette Coefficient |         Conclusion         |
|:----------------------:|:--------------------------:|
|       Close to 1       |     Properly clustered     |
|       Close to 0       |    Overlapping clusters    |
|       Close to -1      | Assigned to wrong clusters |

The silhouette score reaches the highest value at the optimal K.

**Which metrics to choose?**

Ideally, both metrics should be used together. The Elbow method is a decision rule, whereas the silhouette method validates the clustering results. By using both methods together, you can be more confident about the final output.

#### Inter-Cluster vs Intra-Cluster distance

Qn: Match the following rows.

|     |                                                               |     |                                                                                 |
|:---:|:-------------------------------------------------------------:|:---:|:-------------------------------------------------------------------------------:|
| 1   | High Intra-Cluster Distance<br>High Inter-Cluster Distance | i   | ![1](https://i.ibb.co/Twq9wQF/Inter-Cluster-vs-Intra-Cluster-Distance-Qn-1.png) |
| 2   | Low Intra-Cluster Distance<br>  High Inter-Cluster Distance   | ii  | ![2](https://i.ibb.co/z76n4y8/Inter-Cluster-vs-Intra-Cluster-Distance-Qn-2.png) |
| 3   | Low Intra-Cluster Distance<br> Low Inter-Cluster Distance     | iii | ![3](https://i.ibb.co/f8w75n3/Inter-Cluster-vs-Intra-Cluster-Distance-Qn-3.png) |

- 1-ii, 2-i, 3-iii

- 1-iii, 2-i, 3-ii

- 1-iii, 2-ii, 3-i

- 1-ii, 2-ii, 3-i

Ans: B. *A high intra-cluster distance indicates that there is very high variability between the points within the clusters. A high inter-cluster distance indicates that the clusters are more apart hence and are less similar to each other.*

