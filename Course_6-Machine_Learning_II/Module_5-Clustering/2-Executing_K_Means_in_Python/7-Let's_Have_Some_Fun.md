# Let's Have Some Fun

So far, you have learnt how to create clusters using the K-means algorithm. Now, let's apply this knowledge as we experiment with clustering using the K-means algorithm.

The dataset on the literacy level of Indian states is given below.

Download [Indian Census Data](Indian_Census_Data.xlsx)

The given data set contains state-level information on attributes such as the number of literates, the number of illiterates, the number of literates who are graduate and above, etc.

But there’s one problem: the number of variables is quite large. So, after forming the clusters, it may become difficult to describe each cluster’s characteristics.

This is not an uncommon problem. You may have come across data sets with as many as 100-200 variables. There are certain techniques that you can use to ‘reduce the number of variables while retaining as much information as possible’.

Two such techniques, also called variable reduction techniques, are factor analysis and principal component analysis.

Lawmakers can cluster certain states to determine which states have similar education statistics and thus assign the budget accordingly. Clustering can also help them design the best policies for these clusters.

You can download the data set and run the K-means algorithm on it. You can try to make the clusters on different attributes. 

In the image given below, you can see the effect of various elements of the K-means clustering on the clusters formed. You can zoom in by selecting and double-clicking the map to look at these clusters closely.

To create the visualisation given above, we cleaned the data by taking only two factors into consideration. However, you had the option to choose any other factors. Here, factors refer to the variables that you will use to build the clustering model. You can download the file attached below to answer the questions.

Download [Cleaned File](Indian_Census_Data_Cleaned.xlsx)

#### K - Means in Python

Qn: Which parameters do you think are the most important for segmenting the states? On what basis did you choose these parameters?

Ans: *The parameters to be used are dependent on the question at hand. We can choose different age groups and different categories such as graduate or above etc.*

Qn: How will you check if the segmenting is good, or whether you need to use different factors for segmenting?

Ans: *An easy way is to check if the segments are logically correct. For example, we can check if the states in a similar geography and economic situation are clustered together or not. You can also run a hypothesis test to check whether the population of different clusters is significantly different or not. If you look at the data, you will observe that some specific customers or some specific states should be grouped together.*

Qn: What are the differences between the clusters formed before scaling and the ones formed after scaling?

- The illiteracy percentage gets a higher weightage when there is no scaling done.

- The graduate and above percentage gets a higher weightage when there is no scaling done.

- There is no difference in the clusters formed.

Ans: A. *Take a look at the clusters formed with and without scaling. You will observe that for the ones formed without scaling, the states with similar literacy rates will fall in the same cluster, even though their graduate percentage differs.*
