# Advantages and Disadvantages of Decision Trees

Before you dive deeper into this session, let’s learn where Decision Trees are used in the industry. Let’s watch the following video where Sajan will explain how professionals use Decision Trees in day-to-day operations in the industry.

**VIDEO**

You have seen that Decision Trees are actively used in the following industries:

-   Healthcare 
-   Finance
-   E-Commerce industry

You will be covering a case-studies on Healthcare and Finance domains in the upcoming segments. and you have already considered the E-commerce example of buying a shirt in the previous session. Several use cases in the healthcare and financial sectors involve decision-making which verifies the understanding of the professionals in these sectors, as you cannot leave the decision-making of a person’s life or their creditworthiness to receive a loan to a black-box model. In such cases, Decision Trees significantly help in understanding why a particular data point has a certain outcome and then making informed decisions.

Now, let’s look at the following criteria to decide whether to use Decision Trees or Logistic Regression for a given dataset and problem statement.

-   Use Decision Trees
    -   If you need a model for both classification and regression tasks
    -   If the task is a multiclass classification task
    -   If the data is not linearly separable, Decision Trees should be preferred over Linear/ Logistic Regression
    -   If there are outliers; Linear and Logistic Regression are very sensitive to Outliers while decision trees create bins of values upon the split criteria and hence outliers do not adversely affect these bin creation. Hence, outlier treatment is not required.
    -   If the dataset has a lot of missing values; Missing values are considered as a separate class by Decision Trees in case of a categorical variable. In case of continuous variables, you can either impute it with some logic or a common value in which case, these data points behave similarly if that variable is used for the split at a particular node. Hence, minimal processing is required.
-   Use Logistic Regression
    -   If the task is a binary classification task
    -   After removing outliers and treating missing values in the dataset

#### Outliers

Qn: You have understood that outliers in the feature variables do not pose a problem in case of Decision Trees, whether it is a regression tree or a classification tree. Do you think outliers in the target continuous variable is a problem?

Ans: *Yes, it will be an issue because the measure used for splitting in a regression tree is MSE or Variance or Standard Deviation, which are sensitive to outliers. This will create an issue in any machine learning regression problem.*

Decision trees are intuitive and promising algorithms for dealing with categorical attributes. They are also capable of dealing with continuous variables, which makes them of great use. You are already aware of such advantages of Decision Trees. In the next video, Sajan will discuss the advantages of Decision Trees in detail:

**VIDEO**

Let’s summarise the advantages of Decision Trees.

1.  Predictions made by a decision tree are easily interpretable.
2.  Decision trees work well for both categorical and continuous variables.
3.  They can handle linearly separable and non-separable data.
4.  A decision tree does not assume anything specific about the nature of the attributes in a data set. It can seamlessly handle all kinds of data — numeric, categorical, strings, Boolean, and so on.
5.  It does not require normalisation since it has to only compare the values for splitting within an attribute. Therefore, very little or no pre-processing of data is required.
6.  Decision trees often give us an idea of the relative importance of the explanatory attributes that are used for prediction. Intuitively, the closer the variable used for split is to the root node, the higher is the importance.
7.  The set of rules are very easily explainable as they are similar to the approach humans generally follow while making decisions.
8.  A complex model can be simplified by its tree-like visualizations & even a naive person can understand the logic.

You have come across so many advantages of Decision Trees, so should decision trees be used for every case? Not really.  Let’s look at the next video to understand the problems associated with decision trees:

**VIDEO**

Let us now summarize the disadvantages of Decision Trees:

-   Decision trees tend to overfit the data. If allowed to grow with no check on its complexity, a tree will keep splitting till it has correctly classified (or rather, mugged up) all the data points in the training set. You will be learning about overfitting and how to deal with it in the upcoming segments.
-   Decision trees tend to be very unstable, which is an implication of overfitting. A few changes in the data can change a tree considerably.
-   The mathematical calculation of entropy, IG for all features takes a lot of time & memory as you need to perform the split for every feature at every splitting point.
-   The decision trees algorithms learnt till now are greedy. The process is greedy because you have to optimise at every split, and not overall. This means that the information gain overall in the tree, i.e., the difference between the entropy at a source and the leaf nodes may not be the maximum if you follow the greedy approach, i.e., find the best split at each node. This can be dealt with using Random Forest, which you will be learning in the next module.

#### Advantages of Decision Trees

Qn: Which of the following are the advantages of Decision Trees? (More than one option can be correct)

- Decision Trees are easy to understand.

- Decision Trees tend to overfit.

- Decision Trees can deal with linearly non-separable data.

- Decision Trees require pre-processing of data.

Ans: A & C. *The predictions made by a decision tree are easily interpretable. One of the major advantages of Decision Trees over linear models is that it can deal with linearly non-separable data.*

#### Disadvantages of Decision Trees

Qn: Suppose you get an accuracy of 40% on the test data and 98% on the training data. Select all of the following options that apply. (Note: More than one option may be correct.)

- The model has a low variance and a high bias.

- The model has a high variance and a low bias.

- The model is overfitting. 

- The model is underfitting.

Ans: B & C. *The model has memorised the data, giving you an accuracy of 98% on the training data and leading to high variance. As it can now represent the training set very well, it has a low bias. The test accuracy is extremely low (40%). The model is unable to work well on unseen/test data. It has memorised the training set. Hence, it is overfitting.*

You will now learn about overfitting in detail, and also learn how to handle it in the upcoming segments.