# Hierarchical Clustering Algorithm

One of the major considerations while using the K-means algorithm is deciding the value of K beforehand. The hierarchical clustering algorithm does not have this restriction. The output of the hierarchical clustering algorithm is quite different from that of the K-means algorithm. It appears to be an inverted tree-shaped structure and is called the dendrogram. An example of a dendrogram is given below.

![Dendogram Example](https://i.ibb.co/7zTqCWz/Dendogram-Example.png)

You will learn how to construct and interpret a dendrogram in the upcoming videos. In this segment, you will first learn how the Hierarchical Clustering algorithm works.

The hierarchical clustering algorithm can be broadly categorised into two different types, which are as follows:

1. Hierarchical Agglomerative Clustering

2. Hierarchical Divisive Clustering

In the next video, you will learn about Hierarchical Agglomerative Clustering.

**VIDEO**

#### Hierarchical Agglomerative Clustering

Qn: Is the following statement true?  

*"The agglomerative clustering algorithm builds clusters starting from having all the data points in one cluster and, at each step, dividing the cluster into smaller clusters for a specific number of steps."*

- No

- Yes

Ans: A. *The agglomerative clustering algorithm uses a bottom-up approach considering each point as a single cluster and iterates until all the points come under one cluster.*

As you learnt in the video above, in hierarchical clustering, data is not partitioned into a particular cluster in a single step (unlike it is done in the K-means algorithm). Instead, a series of partitions/merges occur, which may run from a single cluster containing all objects to n clusters each containing a single object or vice versa.

**The steps involved in performing agglomerative clustering are as follows:**

- Calculate the distance matrix between all the points in the data set.

- Treat each point as a separate cluster. If you have n data points, then you will have n clusters at the beginning.

- Merge two clusters based on the lowest distance on the distance matrix. The total cluster at the end of this step will be n-1.

- Update the distance matrix.

- Now, keep repeating steps 3 and 4 until you have one cluster.

- Repeat the aforementioned steps until there are no more clusters left to join.

## Comprehension

Consider the 1D plot given below and answer the following questions.

![Hierarchical Agglomerative Clustering Qn](https://i.ibb.co/LSKnff1/Hierarchical-Agglomerative-Clustering-Qn.png)

**Note**: Use Hierarchical Agglomerative Clustering to solve the questions.

#### Hierarchical Agglomerative Clustering

Qn: How many clusters do you have initially (before any fusions have occured)? 

- None

- 3

- 4

- 5

Ans: C. *Since this is agglomerative clustering, initially, each point is a cluster.*

Qn: Select the correct distance matrix for the given plot from below.

- |     | A    | B    | C    | D   |
  | --- | ---- | ---- | ---- | --- |
  | A   | 0    |      |      |     |
  | B   | 2.00 | 0    |      |     |
  | C   | 4.00 | 2.00 | 0    |     |
  | D   | 6.00 | 4.00 | 1.00 | 0   |

- |     | A    | B    | C    | D   |
  | --- | ---- | ---- | ---- | --- |
  | A   | 0    |      |      |     |
  | B   | 2.00 | 0    |      |     |
  | C   | 3.00 | 1.00 | 0    |     |
  | D   | 6.00 | 4.00 | 3.00 | 0   |

- |     | A    | B    | C    | D   |
  | --- | ---- | ---- | ---- | --- |
  | A   | 0    |      |      |     |
  | B   | 2.00 | 0    |      |     |
  | C   | 4.00 | 2.00 | 0    |     |
  | D   | 5.00 | 4.00 | 1.00 | 0   |

- |     | A    | B    | C    | D   |
  | --- | ---- | ---- | ---- | --- |
  | A   | 0    |      |      |     |
  | B   | 2.00 | 0    |      |     |
  | C   | 4.00 | 3.00 | 0    |     |
  | D   | 5.00 | 4.00 | 1.00 | 0   |

Ans: B. *The distance matrix indicates the pairwise distance between each point/cluster.*

![Hierarchical Agglomerative Clustering Qn](https://i.ibb.co/LSKnff1/Hierarchical-Agglomerative-Clustering-Qn.png)

*d(A, B) = 2*

*d(A, C) = 3*

*d(A, D) = 6*

*d(B, C) = 1*

*d(C, D) = 3*

*d(B, D) = 4*

*You can now create the distance matrix using the measures obtained.*

Now that you have the distance matrix given below, which of the two points will merge in the first iteration?

|     | A    | B    | C    | D   |
| --- | ---- | ---- | ---- | --- |
| A   | 0    |      |      |     |
| B   | 2.00 | 0    |      |     |
| C   | 3.00 | 1.00 | 0    |     |
| D   | 6.00 | 4.00 | 3.00 | 0   |

- A-B

- B-C

- A-C

- A-D

Ans: B. *Observing the distance matrix, you will find the minimum distance is that between point B and point C. Hence, these will be the first two single-point cluster to merge in the hierarchical clustering algorithm.*

Qn: Using the distance matrix, you have created a distance matrix, as shown below, and have identified the two points that are closest together and will be merged. Calculate the updated distance matrix and fill in the blank spaces in the given matrix.

![Hierarchical Agglomerative Clustering Qn1](https://i.ibb.co/z24C0mq/Hierarchical-Agglomerative-Clustering-Qn1.jpg)

|      | A   | B, C | D   |
| ---- | --- | ---- | --- |
| A    |     |      |     |
| B, C |     |      |     |
| D    |     |      |     |

- |      | A   | B, C | D   |
  | ---- | --- | ---- | --- |
  | A    | 0   |      |     |
  | B, C | 3   | 0    |     |
  | D    | 6   | 4    | 0   |

- |      | A   | B, C | D   |
  | ---- | --- | ---- | --- |
  | A    | 0   |      |     |
  | B, C | 3   | 0    |     |
  | D    | 6   | 2    | 0   |

- |      | A   | B, C | D   |
  | ---- | --- | ---- | --- |
  | A    | 0   |      |     |
  | B, C | 2   | 0    |     |
  | D    | 6   | 3    | 0   |

- |      | A   | B, C | D   |
  | ---- | --- | ---- | --- |
  | A    | 0   |      |     |
  | B, C | 3   | 0    |     |
  | D    | 6   | 3    | 0   |

Ans: C. 

*distance({B, C}, A) = min(distance(B, A), (distance(C, A) ) = min(2, 3) = 2*

*distance({B, C}, D) = min(distance(B, D), (distance(C, D) ) = min(4, 3) = 3*

*Replace these values in the corresponding blanks in the matrix.*

Qn: Considering the updated matrix in the previous question, which of the following points will be clustered?

|      | A   | B, C | D   |
| ---- | --- | ---- | --- |
| A    | 0   |      |     |
| B, C | 2   | 0    |     |
| D    | 6   | 3    | 0   |

- D-{B, C}

- A-{B, C}

- A, D

Ans: B. *If you observe the data, you will notice that points A and {B, C} have the minimum distance. between them*

Qn: What is the distance between {A, B, C} and D?

- 2

- 3

- 4

- 5

Ans: B. *distance({A, B, C}, D) = min(distance(A, D), distance(B, D), distance(C, D)) = min(6, 4, 3) = 3*

As you learnt earlier in this session, dendrograms are used to visualise and define clusters. In the next segment, you will learn how dendrograms are built for hierarchical agglomerative clustering.