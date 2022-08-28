# Optimal EPS

How can we determine an optimal value for **EPS** and **Minpts**? Eps and Minpts are both considered hyperparameters, and there is no algorithm to determine perfect values for these hyperparameters, given a data set. Instead, they must be optimised largely based on the problem that you are trying to solve.

EPS is a value that deals with the density of the clusters that you are trying to find. To arrive at an optimal value of this parameter, we usually perform an elbowing technique similar to identifying the optimal value K in the K-means algorithm. Let’s watch the upcoming video and learn about this technique from Ankit.

**VIDEO**

In the video, you learnt about the steps to calculate the optimal value of EPS, which are as follows:

1.  Let k = the number of nearest neighbours.  
    You need to calculate the average of the distances of all the points from their k-nearest neighbours. (The value of k is specified by the user and usually corresponds to MinPts.)  
      
    **Note**: Some sources also suggest using the kth nearest neighbour distance instead of the average distance from the k-nearest neighbours. Both results will likely lead you to a similar value.  
     
2.  Next, you need to sort these k-distances in ascending order. Now, you need to plot the number of points on the x-axis and the average distances that you calculated on the y-axis.  
     
3.  The resulting graph should be increasing (as long as you sort your arrays in increasing order by average distance) and concave upwards. Determine the ‘knee’ of the graph, which corresponds to the optimal EPS parameter.

In the next segment, you will learn how to work with the DBSCAN algorithm using the sklearn library.