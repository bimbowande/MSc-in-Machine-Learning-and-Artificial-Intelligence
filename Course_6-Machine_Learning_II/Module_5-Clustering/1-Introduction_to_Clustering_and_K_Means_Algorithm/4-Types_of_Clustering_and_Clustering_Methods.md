# Types of Clustering and Clustering Methods

In this segment, you will learn about the different types of clustering and clustering models used in the industry. Let's watch the upcoming video to learn more about this.

**VIDEO**

Clustering is of two types

1. Hard Clustering 
2. Soft Clustering

![Hard and Soft Clustering](https://i.ibb.co/Y38yLjG/Hard-and-Soft-Clustering.png)

| Hard Cluster                                                                                                                     | Soft Cluster                                                                                                                                                                                               |
| -------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| In a hard cluster, a data point either belongs to a cluster entirely or it does not belong to it at all. There is no in-between. | In a soft cluster, a data point could belong to more than one cluster at the same time. For each cluster, a data point is associated with that cluster with a likelihood.## Types of Clustering Algorithms |

Just like there are different types of clusters, there are different types of clustering algorithms as well. You can differentiate between algorithms based on their clustering model. In the next video, you will learn about these models in detail.

**VIDEO**

There are different types of clustering methods. Some of the important methods are as follows:  
 

- **Partition clustering**: In this technique, the dataset is divided into fixed sets of partitions/clusters. It is also known as a centroid-based cluster. The number of clusters depends on the number of cluster centroids defined by the user. A cluster centroid is iteratively modified by learning the data to form final clusters. You can consider each cluster centroid as the centre of a circle that encompasses all the observations belonging to that cluster, as shown in the image below. 
  
  ![Partition Clustering](https://i.ibb.co/hDjP5bn/Partition-Clustering.png)

    An observation is assigned to the cluster based on its proximity with a cluster centroid. In other words, when the distance between an observation and a cluster centroid is minimal as compared to the distance between the observation and other cluster centroids, the observation becomes a part of that cluster. K-means clustering is an example of partition clustering. You will learn more about the K-means algorithm and all the internals involved in the algorithm in the upcoming segments.  
     
    
    ![Cluster Centroid](https://i.ibb.co/sp7fZDn/Cluster-Centroid.png)  
     

- **Hierarchical clustering**: In this technique, the user does not specify the number of clusters (like the previous method). This type of clustering is known as a connectivity-based cluster. It provides a hierarchy of clusters, as clusters merge together to form new clusters. The output is represented in the form of a tree or a dendrogram, as shown in the picture below. You will learn how to interpret a dendrogram in the session on Hierarchical Clustering.
  
  ![Dendogram](https://i.ibb.co/HG7vxrM/Dendogram.png)  
   

- **Density-based clustering**: In this technique, clusters are formed by segregation of various density-based regions depending on the density in the dataset. DBSCAN is one of the popular techniques belonging to this type of clustering.
  
  ![Density Based Clustering](https://i.ibb.co/X80xX1f/Density-Based-Clustering.png)  
   

- **Distribution model-based clustering**: In this technique, clusters are formed by assigning the observation to the cluster having the highest probability of belonging to that cluster. The most popular algorithm in this technique is the Expectation-Maximisation (EM) algorithm.  
   ![Distribution Model-Based Clustering](https://i.ibb.co/cLqz5N8/Distribution-Model-Based-Clustering.png)
   

- **Fuzzy clustering**: This technique is a part of soft clustering methods. In this type of clustering, a point can belong to multiple clusters. Each point is assigned a certain membership in each cluster, which indicates the degree to which the point belongs to the cluster. Fuzzy C-means is an example of fuzzy clustering.

Now, let's attempt to answer the questions given below.

#### Types of Clustering Algorithms

Qn: State whether the following statement is true or false.

*"DBSCAN is a type of soft clustering."*

- True

- False

Ans: B. *DBSCAN or **Density-based spatial clustering of applications with noise** is a type of density model-based clustering, which assigns each observation to a single cluster. Hence, DBSCAN is a type of hard clustering.*

Qn: In which of the following techniques is the number of clusters predefined by the user? (Note: More than one option may be correct.)

- Partition-based clustering

- Hierarchical clustering

- Density-based clustering

- Distribution model-based clustering

Ans: A & D. *Partition-based clustering and distribution model-based clustering both involve redefining the number of clusters required at the end of the clustering exercise. In the case of hierarchical and density-based clustering, based on the cluster results you arrive at, you finalise on the number of clusters best suited for the clustering exercise.*

Qn: Which type of clustering technique results in the following structure?

![Hierarchical Clustering Dendogram](https://i.ibb.co/Ks6X0gt/Hierarchical-Clustering-Dendogram.jpg)

- Partition clustering

- Hierarchical clustering

- Density-based clustering

- Distribution model-based clustering

- Fuzzy clustering

Ans: B. *The hierarchical clustering technique results in a dendrogram or a tree structure that represents the hierarchy in which the clusters are merged*