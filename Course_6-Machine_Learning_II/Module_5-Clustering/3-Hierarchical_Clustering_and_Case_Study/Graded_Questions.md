# Graded Questions

#### Hierarchical Clustering

Consider the dendrogram given below. Suppose you have decided to cut the dendrogram at Threshold 2. What clusters will you obtain?

![Hierarchical Clustering - Graded Question 1](https://i.ibb.co/3p9H7sp/Hierarchical-Clustering-Graded-Question-1.jpg)

- {A}, {B}, {C}, {D}

- {A.B}, {C,D}

- {A,B,C,D}

- {A,B}, {C}, {D}

Ans: D. *From the dendrogram, you can observe that at threshold 2, {A, B} are already grouped. Point C and Point D are still in their own clusters.*

Qn: The figure given below represents two clusters, which contain three points each. The points and the clusters are appropriately labelled. The points are in the Euclidean space. Now, suppose the single linkage method uses the Euclidean measure as a distance measure. What would be the distance between the clusters 1 and 2 as computed by the complete linkage algorithm?

![Hierarchical Clustering Graded - Questions 2](https://i.ibb.co/bL5s7SX/Hierarchical-Clustering-Graded-Questions-2.jpg)

- The distance between clusters 1 and 2 is the distance between b1 and a2.

- The distance between clusters 1 and 2 is the distance between a1 and c2.

- The distance between clusters 1 and 2 is the distance between a1 and b2.

- The distance between cluster 1 and 2 is the distance between c1 and c2.

Ans: B. *You need to find the distance between the clusters using the complete linkage algorithm.  The distance between clusters is the distance between a1 and c2 since these are the farthest points among all other pairs of points.*

#### Clustering

Qn: What is the advantage of using hierarchical clustering over K-means clustering?

- Hierarchical clustering is computationally faster than K-means clustering.

- You do not have to assign the number of clusters at the beginning in the case of hierarchical clustering.

- There is no difference. Both are equally proficient.

- None of the above.

Ans: B. *A great advantage of hierarchical clustering is that you do not have to specify the number of clusters at the beginning, and with the help of the dendrogram, you can decide the number of clusters you want to create. You cannot do this in K-means clustering.*

#### Hierarchical Clustering

Qn: Which of the following approaches can be used in Hierarchical Clustering?

- Agglomerative clustering

- Divisive clustering

- Both of the above

- None of the above

Ans: C. *Agglomerative and divisive clustering are two different types of hierarchical clustering algorithms, wherein you either assume each point as a single cluster and iteratively merge clusters to form a single cluster in the end or vice versa.*

A set of six points that have to be clustered using the agglomerative clustering method is given in the table below.

| **Point Label** | **X** | **Y** |
| --------------- | ----- | ----- |
| A               | 6     | 0     |
| B               | 1     | 2     |
| C               | 2     | 7     |
| D               | 4     | 6     |
| E               | 5     | 3     |
| F               | 11    | 1     |

Use the single linkage method for clustering and answer the following questions.

#### Hierarchical Clustering

Qn: What is the distance between points B and E?

- 4.1

- 5.0

- 5.1

- 8.6

Ans: A. *The distance between points B and E $=\sqrt{(5−1)^2+(3−2)^2}$*

Qn: Based on the concept of agglomerative clustering, which of the two points will be clustered first?

- A-B

- B-C

- C-D

- D-E

Ans: C. *The distance between C and D is $\sqrt{5}$, which is lower than any other pair of clusters.*

Download the data set on the batting figures of batsmen in ODI matches provided below and analyse the data to answer the following questions.

Download [Cricket](../2-Executing_K_Means_in_Python/Cricket.csv)

You need to choose strike rate and average as the two factors on which you will cluster the data. You do not need to clean the data. But remember to **scale the data** and start creating the cluster.

#### Hierarchical Clustering

Qn: Create a dendrogram using the complete linkage method and cut the tree at k = 4, and select the correct statement from below.

- Virat Kohli and Sachin Tendulkar are in the same cluster.

- CH Gayle and V Sehwag are in the same cluster.

- SC Ganguly, R Dravid and SR Tendulkar are in the same cluster.

- RG Sharma is in the cluster with the highest average strike rate.

Ans: C.