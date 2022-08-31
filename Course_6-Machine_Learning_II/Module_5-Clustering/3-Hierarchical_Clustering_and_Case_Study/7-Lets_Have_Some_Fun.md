# Let's Have Some Fun

So far, you have learnt how to create clusters using the hierarchical clustering algorithm. Now, let's apply this knowledge as we play around with clusters. We will be using the example of the level of education in Indian states, which we used in the previous sessions.

The dataset on the literacy level of Indian states is provided below.

Download [Indian Census Data](../2-Executing_K_Means_in_Python/Indian_Census_Data.xlsx)

You can download the data set and run the hierarchical algorithm on it. You can try to create the clusters on different attributes.

You can observe the effects of various elements of the hierarchical clustering on the clusters formed.

To create the visualisation given above, we cleaned the data to include only two factors under consideration. You can download the clean data from the file attached below.

Download [Cleaned Census File](../2-Executing_K_Means_in_Python/Indian_Census_Data_Cleaned.xlsx)

#### Hierarchical Clustering

Qn: Use the different linkages that you have learnt about so far and compare the results. Which linkage provides a well-separated dendrogram? Are there any advantages of using that particular linkage? Write down your answer in the space provided below.

Ans: *The average linkage and complete linkage methods provide a well-separated dendrogram, whereas single linkage creates dendrograms that are not quite well-separated. Ideally, you would want well-separated clusters.*

Qn: Use various linkages and different numbers of clusters. You will be able to observe the number of natural clusters from the dendrogram itself. If you want, you can change the scale as well. Next, compare the results. Which group of parameters gives you the best result? (Note: For the best result, you can use your general knowledge about various Indian states and determine which clusters make logical sense.) Write down your answer in the space provided below.

Ans: 