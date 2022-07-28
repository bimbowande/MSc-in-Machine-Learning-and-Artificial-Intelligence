# Time Dependency

By now, you have worked on multiple case studies using the random forest model. One of the key things that you would have observed is that the performance of a random forest model increases with the increase in the number of trees. However, this has a limitation. As you increase the number of trees, the construction and evaluation of multiple trees result in a higher computation time. 

This limitation can restrict you from building a solution that requires quick analysis, as in the case of predicting stock prices. For such cases, you must know how the computation time varies with different hyperparameters. In the next video, you will learn about this.

**VIDEO**

Consider a data set with m features and n observations. Each of the n observations is represented as the vector $X_j={x_{j1},x_j2,xj3,...,xjm}$ having the output Yj.

Building an ensemble involves the following steps:

1. Taking a random sample of observations, say j= 40% of the total observations

2. Building S trees by finding all the splits from a subsetted feature space at all nodes within each tree

Hence, the four crucial factors that affect the model building time are as follows:

-   Number of points in the training set: n∗j , where $j = 40\%$ of data set for the training set
-   Number of splitting features (by default) = $\sqrt{m}$ 
-   Number of trees = $S$
-   Number of levels in each tree (default, considering a binary tree) = $log(n∗j)$

All these factors are positively correlated with the model building time. If you combine all of them, you will obtain the following result:

$$Time \propto S∗(\sqrt{m}∗(n∗j)∗log(n∗j))$$

When you are building a solution based on random forests, you must keep all the hyperparameters in mind. As a practice, you should always check whether your model satisfies the requirements from both time and resource perspectives.

#### Time Required to Build a Forest

Qn: Select the correct option. If there are S trees in a forest, M features (income, age, etc.) and n observations (in the original training data), the time taken to build the forest depends upon:

- Only $S$ and $M$

- Only $S$ and $n$

- Only $M$ and $n$

- $S$, $M$ and $n$

Ans:D. *The time required will depend on S. While building each of the S trees, time is spent in creating the levels of trees and finding splits among f features. The levels of trees are given by log(n). Finding the right split depends upon both n observations and f features, as homogeneity will be measured for all f features and n observations.*

#### Time Spent on Splitting

Qn: Select the correct option. Consider building a single individual tree in an ensemble by taking $j = 40\%$ observations randomly from the training set. There are M features and n observations in the original training data. The time spent at each split in this tree is proportional to:

- $\sqrt{M}*n*j$

- $\sqrt{M}*n$

- $n*j$

- $M*n*j$

Ans: A. *Each split is made by comparing the homogeneity across $j=40\%$ of the n observations. Thus, it has to depend on j and n (more the observations, more the time required to compare homogeneity). The time required to find a split also depends upon the number of features being considered, which is $\sqrt{M}$.*

Now, you have a good understanding of the random forest model. In the next session, you will learn how to create a Random Forest model on Spark and how this can be optimised in the distributed environment.