# Industry Insights

Now, before learning how to choose between the K-means algorithm and the hierarchical clustering algorithm based on the given business problem, let's hear from our industry experts as they compare the two algorithms.

**VIDEO**

As you learnt in the video above, the decision to choose between the K-means algorithm and the hierarchical clustering algorithm depends on your hardware and the data you are dealing with.

In the next video, you will learn about a statistical hack that can be used to solve segmentation problems and to obtain meaningful segments. You will use both the hierarchical clustering algorithm and the K-means algorithm in such a way that they complement each other.

**VIDEO**

So, in the video above, you learnt how these clustering methods can be used in such a way that they complement each other. You learnt about the differences between the two methods and also went through the cases in which one method can be preferred over the other.

#### Hierarchical vs K-Means

Qn: What are the advantages of choosing hierarchical clustering over K-means clustering? And, what are its disadvantages?

Ans: *Generally, hierarchical clustering produces better clusters than K-means clustering but is more computationally intensive.*

| K-Means Clustering                                                                                                                                                         | Hierarchical Clustering                                                                                                                                                                                                        |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| K-Means, using a pre-specified number of clusters, the method assigns records to each cluster to find the mutually exclusive cluster of spherical shape based on distance. | Hierarchical methods can be either divisive or agglomerative.                                                                                                                                                                  |
| K-Means clustering needed advance knowledge of K i.e. no. of clusters one want to divide your data.                                                                        | In hierarchical clustering, one can stop at any number of clusters, one find appropriate by interpreting the dendrogram.                                                                                                       |
| One can use median or mean as a cluster centre to represent each cluster.                                                                                                  | Agglomerative methods begin with ‘n’ clusters and sequentially combine similar clusters until only one cluster is obtained.                                                                                                    |
| Methods used are normally less computationally intensive and are suited with very large datasets.                                                                          | Divisive methods work in the opposite direction, beginning with one cluster that includes all the records, and Hierarchical methods are especially useful when the target is to arrange the clusters into a natural hierarchy. |
| In K-Means clustering, since one start with random choice of clusters, the results produced by running the algorithm many times may differ.                                | In Hierarchical Clustering, results are reproducible in Hierarchical clustering.                                                                                                                                               |
| K-Means clustering a simply a division of the set of data objects into non-overlapping subsets (clusters) such that each data object is in exactly one subset.             | A hierarchical clustering is a set of nested clusters that are arranged as a tree.                                                                                                                                             |
| K-Means clustering is found to work well when the structure of the clusters is hyper spherical (like circle in 2D, sphere in 3D).                                          | Hierarchical clustering don’t work as well as, k means when the shape of the clusters is hyper  spherical.                                                                                                                     |
| Advantages:<br> 1. Convergence is guaranteed.<br> 2. Specialized to clusters of different sizes and shapes.<br>                                                            | Advantages:<br> 1. Ease of handling of any forms of similarity or distance.<br> 2. Consequently, applicability to any attributes types.<br>                                                                                    |
| Disadvantages:<br> 1. K-Value is difficult to predict.<br> 2. Didn’t work well with global cluster.                                                                        | Disadvantage:<br> 1. Hierarchical clustering requires the computation and storage of an n×n distance matrix. For very large datasets, this can be expensive and slow.                                                          |

Qn: Can you use a dendrogram to create meaningful clusters? (Hint: By observing which elements leave and join at what height)

Ans: *Yes. A dendrogram is a useful tool. You can observe the stage at which an element is joining a cluster and, hence, see how similar or dissimilar it is to the rest of the cluster. If it joins at a higher height, it is quite different from the rest of the group. You can also observe which elements are joining which cluster and at what stage and, thus, apply your business understanding to cut the dendrogram more accurately.*

With this, we come to the end of the discussion on hierarchical clustering algorithms. In the next session, you will take a look at a case study focussing on the usage of clustering in the music industry.