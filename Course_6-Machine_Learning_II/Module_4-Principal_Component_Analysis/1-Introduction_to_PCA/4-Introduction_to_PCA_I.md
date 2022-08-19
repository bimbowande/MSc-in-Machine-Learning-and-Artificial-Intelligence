# Introduction to PCA - I

In the previous segment, you saw that PCA is a low-rank decomposition algorithm that uses variance as a measure of information. In the subsequent segments, you will use a graphical and statistical interpretation of PCA and understand what exactly PCA does.

Let’s start the discussion by taking an interesting example. The table below contains the salary and age of a particular company’s employees.

![PCA Salary vs Age](https://i.ibb.co/kH3HRZj/PCA-Salary-vs-Age.png)

Here, we are taking a data set with two columns only. Note that we have deliberately taken a small data set to understand the concept of PCA with calculations of low values. In reality, you may be given a data set with thousands of columns and be required to use PCA to reduce the number of dimensions as per requirement.  
   
Now, suppose you want to build an ML model. Do you think the Age column is relevant enough to be included as one of the features?

You will be able to answer this question by calculating the variance of the columns. Let’s understand this in detail by watching the next video.

**VIDEO**

Let’s consider the following three tables:

![PCA Salary vs Age Multiple Tables](https://i.ibb.co/ZfgyHLN/PCA-Salary-vs-Age-Multiple-Tables.png)

In Table A, the age of the employees is not varying with the different data points; hence, it can be concluded that the Age column is not useful for building the machine learning model because it does not contain any information.

On the other hand, the age is slightly varying in Table B and significantly varying in Table C. Now, if you want to build an ML model using the columns of these tables, then only the Age column in Table C would be the most relevant because it has the maximum variance.

Thus, you can deduce the fact that if a particular column has more variance in it, then that variable is considered more important than the other columns in the data set. In simple terms, if a column has more variance, then that particular column contains more information.

Now, let’s consider Table C and calculate the variance of each column in it.

**Variance in age = 386.27  
Variance in salary = 750.57  
Covariance between age and salary = 447.22**

You will understand the concept of covariance in the subsequent segments. For now, let’s understand what covariance measures. Covariance represents the correlation between variables. The absolute value of the covariance will be high when one variable increases with an increase or a decrease in another variable, and if there is no relation between the variables, then the value of covariance will be low or near to zero.

Now let’s perform a short exercise and calculate the percentage of variance in each variable.

**Percentage of variance in age = 34%  
Percentage of variance in salary = 66%**

As you can see, both columns contain a significant amount of variance; hence, both columns are important for the analysis. Also, the columns are correlated with each other because the covariance between the Age and Salary columns is 447.22

Suppose you are able to create two new columns, say, PC1 and PC2, from the original set of columns, i.e., Age and Salary, such that the percentage of variance in PC1 is 99.8% and that of variance in PC2 is 0.2%. Also, the covariance between PC1 and PC2 is almost zero.

Now, can you simply drop PC2 since both PC1 and PC2 are uncorrelated with each other (covariance almost equals to zero) and almost 99% of the information, i.e., the variance is contained by PC1? 

In the next video, you will see the graphical interpretation of PC1 and PC2, which can be derived by rotating the axis in the direction of the maximum variance.

**VIDEO**

Let’s consider the rotation of the axis as discussed in the video above.

![PCA Rotation of Axis](https://i.ibb.co/HY7tSBZ/PCA-Rotation-of-Axis.png)

In the first graph, there is a significant variance along both the axes. Now, let’s change this and view the data from the perspective of blue and green axes.

What do you notice?

As you can see in the graphs above, the variance along the blue axis, i.e., PC1 is maximum and that along the green axis, i.e., PC2 is minimum. So, you have finally found the direction along which you can derive the maximum variance, or in other words, the maximum information.

Now, once you have found the direction of maximum variance, the next task is to project the original data points on these newly obtained axes. This is what PCA does, but how it manages to do this is something that you will learn in the upcoming segments.