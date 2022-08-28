# Advantages and Drawbacks of DBSCAN

Now that you have gained an understanding of the various concepts related to the DBSCAN algorithm, it is time to discuss the advantages and drawbacks of this algorithm. In the upcoming video, our expert will discuss them in detail.

**VIDEO**

Some of the advantages of the DBSCAN algorithm over the K-means algorithm are as follows:

1.  **In DBSCAN, we do not have to specify the number of clusters.** 
    
2.  **DBSCAN is not sensitive to outliers and noise in data.** In fact, it is frequently used to eliminate outliers and noise from data sets, owing to its ability to identify noise points. In the image given below, you can see that for the same data set, DBSCAN has captured the noise accurately, whereas K-means has failed to capture any of the noise.  
    
3.  **K-means works well only when clusters are spherical. DBSCAN has no such limitation.** As you can see in the image given below, K-means has failed to form the right clusters in most of the cluster. On the other hand, DBSCAN has done this accurately.  

Some of the drawbacks of the DBSCAN algorithm are as follows:

1.  **DBSCAN cannot cluster a data set with large differences in densities.**  
    Consider the image given below. The left figure shows the ideal clusters that are expected to be formed. There are a total of six clusters, and you can clearly see that each cluster has a different density of data points.  
    ![DBSCAN Dataset Large Differences in Densities](https://i.ibb.co/h2KXCw7/DBSCAN-Dataset-Large-Differences-in-Densities.png)  
    In the middle and the right figures, we have shown the results of the execution of the DBSCAN algorithm for two different values of EPS. For the middle figure, an EPS value of 9.92 was used, and you can see that DBSCAN has generated three clusters, which are depicted in three different colours: blue, red and green. After running DBSCAN on the right figure, the algorithm again produced three clusters (shown in blue, red and green) when using an EPS value of 9.75, although the clusters are not the same as those in the middle figure.
    
2.  **It can be difficult to choose the threshold EPS as the data and scale vary.**  
    As you saw in the three figures above, the clustering performed by DBSCAN is highly sensitive to the value of the EPS that is chosen. Now, let’s consider the data set that Ankit explained in the previous video. As you can see in the image below, choosing an EPS value that is larger than the optimal EPS can result in different clusters. Hence, it is important to choose the optimal EPS before executing the DBSCAN algorithm on the data set.
    
    ![DBSCAN Difficult to Chose Threshold](https://i.ibb.co/zhY9FXd/DBSCAN-Difficult-to-Chose-Threshold.png)


In the next segment, you will learn about a technique that can be used to generate the optimal value of the EPS.