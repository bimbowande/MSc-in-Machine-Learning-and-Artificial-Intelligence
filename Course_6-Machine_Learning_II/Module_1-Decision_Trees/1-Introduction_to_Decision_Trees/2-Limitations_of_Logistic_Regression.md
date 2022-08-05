# Limitations of Logistic Regression

Suppose you want to analyze whether a credit card transaction is fraudulent or not and in order to do so you decide to use a dataset consisting of previous credit card transactions. Such a dataset will have a huge amount of data and contain multiple independent variables with missing values within them. The data can be continuous, categorical or both. Moreover, the data may or may not be linearly separable. Hence, linear regression is out of option. Logistic Regression can be used but what if the sigmoid separator is also not able to differentiate the classes properly?

There are various situations where using Logistic regression is not feasible. Let us hear what Sajan has to explain about the same:

**VIDEO**

#### Decision Boundary

Qn: You have seen that the sigmoid function is used to fit the points in case of the logistic regression model. Sigmoid is a non-linear curve then why is the decision boundary linear?

Ans: You have sigmoid as $p=\dfrac{1}{1+e^{−z}}=\dfrac{1}{1+e−^{(w_1x_1+w_2x_2+c)}}>0.5$ for a vanilla logistic regression. Hence, for $z$, the decision boundary can be thought of as sigmoid but in terms of the original features, $x_1$, $x_2$, the decision boundary comes out to be linear. This is a result of a modification of the above function as $w_1x_1+w_2x_2+c>0$ which is a linear separator. You can read more about this from [here](https://homes.cs.washington.edu/~marcotcr/blog/linear-classifiers/).

From the video, we can conclude that using Logistic Regression works well only for linearly separable data. But to do so, it requires the following tasks to be done for it to function properly:

-   Preprocessing the data before it is used.
-   Normalization
-   Scale the features to the same level.

This makes the process very tedious and complicated when huge sized data is involved. Therefore, it is not always the most suitable method. Besides the factors mentioned above, Logistic Regression does not work well in the following cases:

-   Multi-class data
-   A large number of missing entries of data.

**Note:** Another fact to be kept in mind is that logistic regression can only work for binary (two-variable) classification problems. In such cases it is considered as a generalised linear model for a binary classification problem as the log of sigmoid function leads to a [linear boundary/partition](https://homes.cs.washington.edu/~marcotcr/blog/linear-classifiers/). The images shown in the video refer to this particular case of logistic regression.

Therefore, there is a requirement for another Machine Learning model which can overcome these limitations. This is where Decision Trees come into the picture. You will learn in detail about Decision Trees in this module. But before we dive deep into the concepts of Decision Trees, let us take a look at the upcoming video which highlights how Decision Trees can overcome some issues faced by Logistic Regression:

**VIDEO**

From the video above, we can summarize the following points:

1.  While Logistic Regression technique helps interpret the dependency of the dependent and the independent variables, you may not be able to visualise it. Decision Trees outcomes are interactive and comparatively easier to understand and visualize.
2.  Unlike Logistic Regression, Decision Trees do not require very large-sized training data.
3.  To implement multiclass classification, the approach followed by Logistic Regression is ‘one v/s all’ which basically involves building multiple models,  one for each class. But in the case of  Decision Trees, multiclass classification can be done in a single tree, which is a better approach.

With this understanding, try to answer the following questions:

#### Choice of model

Qn: Which of the following Machine Learning models will you use while working with a dataset with missing values within it? (Choose the best option)

- Logistic Regression

- Decision Trees

Ans: B. *Decision Trees are not very sensitive to missing values, hence the amount of pre-processing required will be less in comparison to Logistic Regression. We shall learn more about this later.*

Qn: Which of the following statements is/are true?

- Decision Trees can divide the classes using only linear boundaries.

- Logistic Regression is more interpretable as compared to Decision Trees.

- Decision Trees can divide the space into two or more parts using linear or non-linear boundaries as per requirement.

Ans: C. *Decision Trees divide space into different parts such that most of the points from the same class lie together. While doing so it may use non-linear boundaries as well.*

Now that you are aware of the requirement for a Decision Tree, let us learn about it in detail in the upcoming segments.