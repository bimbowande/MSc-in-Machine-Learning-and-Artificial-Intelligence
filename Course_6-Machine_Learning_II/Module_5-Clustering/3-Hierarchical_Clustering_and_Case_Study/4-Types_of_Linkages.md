# Types of Linkages

During our earlier discussion on the workings of the algorithm, we considered the minimum value of all pairwise distances between the points of the two clusters as the distance between two clusters. This measure of distance between the data points is called a single linkage. Apart from using the minimum value, you can use other methods to compute the distance between clusters.

In this segment, you will learn about three types of linkages, which are as follows:

-   Single linkage
    
-   Complete linkage
    
-   Average linkage
    

## Single Linkage

In the next video, you will learn about single linkage in detail.

**VIDEO**

As you learnt in the video above, in single linkage clustering, the distance between two clusters is defined as the shortest distance between points in the two clusters.

The pros and cons of using single linkage are as follows:

**Pros**

-   Single linkage is highly **effective in handling non-elliptical shapes**. Earlier, you saw a similar scenario where the K-means algorithm failed to perform because of its high dependency on the cluster centroid. However, you do not deal with any centroid in the case of hierarchical clustering; instead, solely based on the distance between two points, you combine different points to form clusters. Due to this reason, clusters of different shapes are formed, as shown in the image below.
    
    ![Eliptical and Non-Eleptical Shapes](https://i.ibb.co/HxBC5WY/Eliptical-and-Non-Eleptical-Shapes.png)
    

**Cons**

-   **Chaining effect**  
    Since the distance between two clusters (or a cluster and a data point) is recognised by the minimum distance between them, they are one of the first clusters to be merged while moving upwards and cannot be distinguished after the dendrogram is created. This leads to a high tendency in merging clusters that are close to each other, resulting in a chaining effect.  
     
-   **Sensitive to noise and outliers**  
    Adding a single outlier can drastically change the cluster sizes. In the image given below, the first plot is properly clustered. However, adding an outlier results in improper clusters. The third plot has been picked up from scikit-learn's image repository. As you can see, the data contains a lot of noise, resulting in no well-defined clusters.
    
    ![Data with Outliers](https://i.ibb.co/pjWnfR6/Data-with-Outliers.png)
    

Now that you have learnt about single linkage, in the next video, you will learn about complete linkage.

## Complete Linkage

**VIDEO**

#### Linkages

What would be the output if I use a single linkage instead?

- ![Linkages Qn1](https://i.ibb.co/Jq2dwVC/Linkages-Qn1.png)

- ![Linkages Qn2](https://i.ibb.co/SRQQJQc/Linkages-Qn2.png)

- ![Linkages Qn3](https://i.ibb.co/9g1PD1z/Linkages-Qn3.png)

Ans: A. *Single linkage has the opposite tendency. Due to it's chaining effect, it will merge as many points as possible into a single cluster. Due to its strong tendency to merge clusters together, it will result in all the points being clubbed into a single cluster.  If you look at the diagram more closely, the orange and green points are the clusters that were merged last before completing the dendrogram.*

Here, the distance between two clusters is defined as the maximum distance between any two points in the clusters as shown in the image below.

![Complete Linkage Distances](https://i.ibb.co/tz3hdjS/Points-Distances.png)

The pros and cons of using complete linkage are as follows: 

**Pros**

-   Complete linkage is **less susceptible to noise and outliers.**

**Cons**

-   This type of linkage **tends to break large clusters.**
-   Complete linkage is **biased towards globular clusters** or, in other words, clusters that are spherical in shape, as shown below.
    
    ![Complete Linkage and Cluster Shapes](https://i.ibb.co/Cv13MqK/Complete-Linkage-and-Cluster-Shapes.png)
    

## Average Linkage

Since both single linkage and complete linkage have their own pros and cons, many data scientists prefer using the average linkage as a middle ground between two. Let's hear from our expert Ankit as he talks about average linkage in detail.

**VIDEO**

Here, the distance between two clusters is defined as the average distance between every point of one cluster and every point of the other cluster, as shown in the image below.

![Average Linkage](https://i.ibb.co/6WMsQ46/Average-Linkage.png)

The pros and cons of using average linkage are as follows:

**Pros**

-   Average linkage is **less susceptible to noise and outliers.**

**Cons**

-   It is biased towards **globular clusters.**

#### Hierarchical Clustering

Qn: Select the correct statement regarding the single linkage method from below.

- In single-linkage hierarchical clustering, the distance between two clusters is defined as the shortest distance between two points in each cluster.

- In single-linkage hierarchical clustering, the distance between two clusters is defined as the longest distance between two points in each cluster.

- In single-linkage hierarchical clustering, the distance between two clusters is defined as the distance between the centroids of the clusters.

- In single-linkage hierarchical clustering, the distance between two clusters is defined as the average distance between all the points in each cluster.

Ans: A. *A single-linkage cluster defines the distance between two clusters as the shortest distance between any two points in each of the clusters.*

Qn: Suppose you have two clusters. 

Cluster A = {(1,2), (3,4)} and

Cluster B = {(5,6), (3,5)} 

Using the single linkage concept discussed by Ankit, what would be the distance between clusters?

- $\sqrt{13}$

- 1

- $4\sqrt{2}$

- $2\sqrt{2}$

Ans: B. *The pairwise distance between the points in the clusters are as follows:* 

*The distance between (1,2 ) and (5,6) is $4\sqrt{2}$.*  
*The distance between (1,2) and (3,5) is $\sqrt{13}$.*  
*The distance between (3,4 ) and (5,6) is $2\sqrt{2}$.* 
*The distance between (3,4 ) and (3,5) is  1.*

*In the single linkage measure, you consider the minimum value among the pairwise distances as the distance between the clusters, which, in this case, is 1.*

Qn: Suppose you have the following two clusters: 

Cluster A = {(1,2), (3,4)}, and

Cluster B = {(5,6), (3,5)}.

Using the complete linkage method discussed by Ankit, find the distance between two clusters and select the correct option from below.

- $\sqrt{13}$

- 1

- $4\sqrt{2}$

- $2\sqrt{2}$

Ans: C. *The pairwise distance between the points in the clusters are as follows:* 

*The distance between (1,2 ) and (5,6) is $4\sqrt{2}$.*  
*The distance between (1,2) and (3,5) is $\sqrt{13}$.*  
*The distance between (3,4 ) and (5,6) is $2\sqrt{2}$.* 
*The distance between (3,4 ) and (3,5) is  1.*

*According to the complete linkage method, you consider the maximum value among the pairwise distances as the distance between the clusters, which is $4\sqrt{2}$ in this case.*

