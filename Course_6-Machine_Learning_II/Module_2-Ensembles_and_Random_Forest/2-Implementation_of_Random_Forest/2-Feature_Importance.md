# Feature Importance

Feature importance plays a crucial role in contributing towards effective prediction, decision-making and model performance. It eliminates the less critical variables from a large data set and helps with identifying the key features, which can, in turn, lead to better prediction results.

Random forests use multiple trees, reduce variance and allow further exploration of feature combinations. The forthcoming video will help you understand the notion of variable importance in random forests.

**VIDEO**

The importance of features in a random forest is calculated through **Gini importance** or **mean decrease impurity**, which represents the **total decrease in node impurity**. It is calculated by taking a weighted average of the above-mentioned metric across all the trees in the ensemble. This is replicated for all the features one by one as shown below. 

![Feature Importance Weighted Average 1](https://i.ibb.co/1GJZgGK/Feature-Importance-Weighted-Average-1.png)

The weights associated with a feature for every tree can be simply calculated as the **fraction of the rows** present in the node where it is to split the data set. The number of rows provides an approximation for the importance of the feature, as the node at a higher level would have a higher number of rows. The image below shows how the Information Gain is calculated.

![Feature Importance Weighted Average 2](https://i.ibb.co/P9RSmyX/Feature-Importance-Weighted-Average-2.jpg)

For each variable, the sum of the Information Gain (IG) across every tree of the forest is accumulated every time a variable is chosen to split a node. The value is then divided by the number of base trees in which the feature is involved in order to give the final average value.

So, the final value of information gain for a feature can be calculated as follows:

$$\dfrac{\sum(W_i∗(Information\ Gain_i))}{n}$$

Here:

$W_i$ is the value of weight associated with the ith tree. 

$Information\ Gain_i$ is the information gain after the split in the $i^{th}$ tree based on that feature. 

$n$ is the number of base models in which the feature is used for split.

You will get more clarity on the concept after you have attempted the assessments given below.

#### Feature Importance

Suppose you have a data set with 200 rows and 5 variables. Feature 5 is the target variable. You are building a random forest model with 4 trees and 50% of the observations as a bootstrapped sample for each tree. The model results in the following summary.

![Feature Importance Weighted Average 3](https://i.ibb.co/nC11pnL/Feature-Importance-Weighted-Average-3.jpg)

Qn: Using the concepts covered in this segment, calculate the importance score/final information gain value for feature 1.  (Round off to three decimal places)

- 0.043

- 0.074

- 0.225

- 0.280

Ans: A. *To calculate the importance score, you can refer to the formula provided above.*

-   *The weight for each tree can be calculated by dividing the number of observations in the node by 100. *
-   *Next, the weights must be multiplied with the IG value.*
-   *In the last step, you must take an average of all the values.*

$\text{Importance Score}=\dfrac{(\frac{20}{100}∗0.10)+(\frac{10}{100}∗0.12)+(\frac{60}{100}∗0.16)}{3}=0.04267$

Qn: Which of the following features is the most important in predicting the target variable?

- Feature 1

- Feature 2

- Feature 3

- Feature 4

Ans: C. *This variable is the most important feature, with a score of 0.28.*

Next, we will try to build a random forest model in Python and derive the feature importance for the same.