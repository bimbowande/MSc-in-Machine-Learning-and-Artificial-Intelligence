# Building a Dendrogram

Now that you know how the algorithm works, it's time to understand how a dendrogram is built and interpreted. For the demonstration, we will use the scatter plot given below and create a dendrogram based on it.

![Building a Dendogram](https://i.ibb.co/GWzWzhF/Building-Dendogram.png)

Let's watch the next video to learn more about the process.

**VIDEO**

In the dendrogram given in the video above, samples 1 and 2 have the highest number of similarities and, hence, join to form the first cluster, followed by samples 1-2 and 3. The last two clusters to fuse together to form the final single cluster are 9 and 1-2-3-4-5-6-7-8, as shown in the image given below.

![Dendogram Distance](https://i.ibb.co/026pY0V/Dendogram-Distance.png)

The y-axis of the dendrogram is the measure of distance at which the clusters merge, or in other words, it represents the distance or dissimilarity between clusters. Once you have created a dendrogram, you can obtain the required number of clusters by drawing a horizontal line and cutting the dendrogram such that the number of cuts is equal to the number of clusters. As you can see in the image given below, we cut the previous dendrogram at two points, which resulted in 4 and 6 clusters, respectively.

![Dendogram Different Clusters](https://i.ibb.co/n1bPtM0/Dendogram-Different-Clusters.png)

## Comprehension

Consider the dendrogram given below for agglomerative clustering and answer the following questions.

![Dendogram Distances](https://i.ibb.co/vZs7vSZ/Dendogram-Distances.png)

#### Hierarchical Clustering

Qn: Considering the threshold value is 10,000, find the total number of clusters.

- 3

- 4

- 5

- 7

Ans: C. *When you draw a horizontal line at the given height, the dendrogram is cut at five vertical lines, all of which represent a cluster.*

Qn: Considering the number of clusters to be formed is four, find the threshold value.

- 5,000

- 10,000

- 15,000

- 20,000

Ans: C. *When you draw a horizontal line at the height of 15,000, the line will cut four vertical lines, or in other words, form four clusters.*
