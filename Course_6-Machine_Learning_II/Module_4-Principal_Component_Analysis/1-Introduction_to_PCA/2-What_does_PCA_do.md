# What does PCA do?

The first thing to know before learning a new concept is to understand why and how that knowledge is useful. so, let's watch the next video to understand the motivation for studying PCA.

**VIDEO**

Note: At 3:12, Rahim tells 100C2 is 450, while it should be 4950 instead.

As explained by Rahim in the video above, having many features poses problems in the following situations:

-   **The predictive model set-up:** When there are many correlated features in a data set, it leads to the problem of multicollinearity. There are certain methods through which you can reduce the dimensionality and remove the correlation among the features, but it may lead to some information loss. In contrast, PCA reduces the dimensionality by keeping the maximum information of the data set intact.
-   **Data visualisation:** It is not possible to visualise more than two variables simultaneously using a 2-D plot. Therefore, finding relationships between the observations in a data set that has several variables through visualisation is quite difficult.

Let’s hear from Rahim as he explains the workings of PCA.

**VIDEO**

In the next segment, you will learn about low-rank approximation. You will understand why it is not possible to explicitly find the relation between the variables and learn how variance and covariance are used for this purpose.

#### Application of PCA

Qn: What do you do when you have correlated variables in the case of linear/ logistic regression?

- Drop all the correlated columns

- Keep the correlated columns as they are

- Consider the variance inflation factor (VIF) values and p-values of the features and eliminate the columns accordingly

Ans: C.

So, you do not need to eliminate the features by considering the p-values or VIF values in the case of PCA because it automatically finds the best set of features. This is one of the advantages of PCA.

In the next segment, you will learn about low-rank approximation.