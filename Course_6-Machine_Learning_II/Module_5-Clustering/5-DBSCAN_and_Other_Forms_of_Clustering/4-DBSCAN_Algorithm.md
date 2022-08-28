# DBSCAN Algorithm

In this segment, you will learn about the end-to-end DBSCAN algorithm in detail. Let’s watch the upcoming video as our expert Ankit explains the steps involved in implementing the DBSCAN algorithm.

**VIDEO**

The algorithmic steps for the DBSCAN Clustering are as follows:

1. Initially, all the points are marked as unvisited. The algorithm proceeds by arbitrarily selecting a point in the data set (until all points have been visited).  
    

2.  If the selected point is a core point, then we consider all other points within its EPS radius to be part of the same cluster, as shown below. 
   
   ![DBSCAN Algorithm 1](https://i.ibb.co/0KPvGJJ/DBSCAN-Algorithm-1.png)  
   If the point does not turn out to be a core point, then the algorithm will choose another point until it finds a core point.

3. The clusters are then expanded by recursively repeating the calculation for each neighbouring point and marking them as visited. Essentially, we check again if any of the neighbouring points are core points. By doing this, the algorithm clusters all the **density-connected points** together.  
   
   Now, let’s try to understand what the term 'density-connected points' means.  
    
   
   **Density-Connected Point**  
   Suppose point c (in the image given below) was chosen arbitrarily as the first point and was classified as a core point. In the image given below, assume that point d and point b are also core points. From this image, let’s try to understand when the cluster grows in the direction of point b.
   
   ![DBSCAN Algorithm 2](https://i.ibb.co/n8CyCSC/DBSCAN-Algorithm-2.png)
   
   So, as you can see in the image given above, point c, point d and point e are all core points. In addition, **point d lies in the neighbourhood of point c, and point e lies in the neighbourhood of point d**. Hence, they will all be part of the same cluster, and all their neighbourhood points will also be considered part of the same cluster and will be marked as visited.  
   
   Now, as mentioned before, point b is also a core point in the neighbourhood of point c. Hence, the cluster will grow in the direction of point b. **Point b lies in the neighbourhood of point c, and point a lies in the neighbourhood of point b.** Hence, similar to the previous case, they will also be part of the same cluster, and all their neighbourhood points will also be considered part of the same cluster and will be marked as visited.
   
   ![DBSCAN Algorithm 3](https://i.ibb.co/jvRYnHq/DBSCAN-Algorithm-3.png)
   
   Hence, all the points in the image above are density-connected points. Therefore, they will all fall under the same cluster, as shown in the image below. Now, if you take a look at point p and point q in the image given below, you will notice that point p lies in the neighbourhood of point f only, which is not a core point (but a border point). Hence, point p is not density-connected to the points in this cluster and will not be a part of this cluster. Similarly, point q, which does not lie in the neighbourhood of any point, will also not be a part of this cluster.
   
   ![DBSCAN Algorithm 4](https://i.ibb.co/dWgGLQ2/DBSCAN-Algorithm-4.png)
   
   Thus, using the concept of density-connected points, we have clustered the following points as shown in the previous video.
   
   ![DBSCAN Algorithm 5](https://i.ibb.co/tzvgBRT/DBSCAN-Algorithm-5.png)  
   
   **Note**: Through this step, all the core points and border points get clustered together while the noise points are left out.  
    

4. The next step is to iterate through the remaining unvisited points in the data set. (All the points that are assigned a cluster will be marked as visited.)  
    

5. For each core point, if it is not assigned to a cluster already, create a new cluster.  
    

6. Those points that do not belong to any cluster are noise points, as shown in the image given below.
   
   ![DBSCAN Algorithm 6](https://i.ibb.co/zJYQmr9/DBSCAN-Algorithm-6.png)

At times, it can be difficult to visualise the entire DBSCAN algorithm. So, in the upcoming video, Ankit will reiterate the steps of the DBSCAN with the help of a visualisation, which is available in this [link](https://www.naftaliharris.com/blog/visualizing-dbscan-clustering/) (choose the ‘Pimpled Smiley’ data set).

**VIDEO**

In the video above, Ankit showed the visualisation of the DBSCAN algorithm on the ‘**Pimpled Smiley**’ data set. Similarly, you can try out the data sets that have been provided, and experiment with different EPS and Minpts values. In the next segment, you will learn about the advantages and drawbacks of the DBSCAN algorithm.

#### DBSCAN Algorithm

Qn: How will DBSCAN work on a uniformly distributed data set?

Ans: *DBSCAN will either merge all the points in a uniform data set into one cluster or classify them all as noise points, depending on the threshold. There might be some boundary issues for the points at the edge of the region. However, DBSCAN can often find clusters in random data, as it does have some variation in density.*

#### DBSCAN Algorithm

Qn: Based on your understanding of the algorithm that you have just learnt, what will be its time complexity?

- $O(n)$

- $O(n^2)$

- $O(n^3)$

- None of the above

Ans: B. *This algorithm iterates over each point in a data set, and for every single point, it searches for neighborhood points by checking all other points. Hence, the time complexity of the algorithm is given by $O(n^2)$*

#### Additional Resources

Application of DBSCAN at Netflix: [Read Here](https://medium.com/netflix-techblog/tracking-down-the-villains-outlier-detection-at-netflix-40360b31732)

Application of DBSCAN in geolocated data: [Read Here](https://www.oreilly.com/ideas/clustering-geolocated-data-using-spark-and-dbscan)

The original paper on DBSCAN posted by Martin Ester on KDD: [Read Here](https://www.aaai.org/Papers/KDD/1996/KDD96-037.pdf)