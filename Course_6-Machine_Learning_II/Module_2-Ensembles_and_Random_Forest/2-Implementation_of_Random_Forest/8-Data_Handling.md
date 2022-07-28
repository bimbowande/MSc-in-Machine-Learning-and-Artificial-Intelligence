# Data Handling

In the previous segments, you gained an in-depth understanding of the random forest model and also implemented both regression and classification random forest trees. You also learnt that random forests are capable of handling missing values. In this segment, you will learn how it does that. 

So far, you have dealt with missing values by either dropping them or imputing them with mean, mode or median values. However, a random forest model can overcome the missing values using inherent features. Let's try to understand it in the next video.

**VIDEO**

As mentioned in the video, random forests use the concept of **proximity matrix**. Here, the following is expected:

1.  First, a random forest model is built using general imputation methods such as maximum count and average.
2.  Once the first random forest model is built on the data set with a number of decision trees, it generates a proximity matrix.
3.  This matrix is a n x n matrix that records the frequency of the occurrence of two data points together in a leaf node of all the trees divided by the total number of trees in the forest.

$$\text{Proximity score(i, j)}=\dfrac{\text{Frequency of i and j appearing together}}{\text{Number of trees}}$$
  
where i and j are two data points from the data set.

The score can be used to measure the similarity between data points, as two points will end up in the same leaf node only if they have similar attributes. Higher the proximity score, higher are the chances that two observations have identical features.

![Proximity Score Matrix](https://i.ibb.co/pxgpbj4/Proximity-Score-Matrix.jpg)

  
In the next video, you will learn how a proximity matrix can be used in the process of imputation of missing values.

**VIDEO**

Random forest uses an **iterative method** to replace the missing values. The proximity matrix can be used to impute the missing values in both training and testing sets. 

![RF Iterative Method](https://images.upgrad.com/c6f77236-a467-4ba9-9fff-bfef6d56c0ea-img-16.jpg)

The entire process is summarised below: 

-   **Training set:**
    1.  The missing values in the data set are first replaced by **general methods** (average, maximum count, etc.). 
    2.  The first iteration of the random forest model is built on the data set after the step given above, which generates the first proximity matrix.
    3.  For further iterations:
        -   The proximity matrix is used to replace the missing values in the data set again. The new values are computed as the weighted average of non-missing values with the proximity score as the weight.
        -   The random forest model is again built on the new data set, which results in the new proximity matrix.

The above-mentioned steps are repeated until satisfactory results are obtained. Generally, it is recommended that you run 4–6 iterations to reduce the impact of missing values.

-   **Test set**: The value of the target variable is absent along with other features:
    1.  Since the target variable is absent in test data, the observation is replicated with a copy for each class label. For example, if it is a binomial problem (0/1), the data point will have two copies wherein one point has value 0 and the other has value 1. This is done because you will require a majority vote to calculate the final prediction value.
    2.  The random forest model is then built with imputed values. The observation that gets the maximum votes is selected to impute the final label. Please note that this process is done for the purpose of **imputation and not for final prediction**.

This is how random forests can efficiently deal with missing values. Another problem that is faced during data preparation is that of outliers. In the next video, you will learn how the random forest model deals with them.

**VIDEO**

The process used to build the random forest inherently takes care of the outlier values. Owing to random sampling, the impact of outliers is reduced to a minimum, as every observation will not appear in the training set of every decision tree. Moreover, since decision trees are not sensitive to outliers, random forest, being an ensemble of decision trees, is also not sensitive to outliers.

#### Outliers

Qn: Select the correct option associated with Outliers and Decision Trees.

- Decision trees are insensitive to outliers as they take the median of the values instead of average to find the split point within the variable. The split value is the median which is insensitive to outliers.

- Decision trees are insensitive to outliers as they sort and bin the values in a variable to find the best split value. The split value is estimated using the values at which the bins are created.

- Decision trees are sensitive to the outliers.

Ans: B. *Outliers go to one of the bins and are not able to affect the bin generation as bin generation is completely random.*

After learning how random forest deals with the problems associated with data preparation, in the next segment, you will learn about the time complexity of the model.