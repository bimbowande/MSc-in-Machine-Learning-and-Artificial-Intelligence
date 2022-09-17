# CART

Let us consider the example of buying a shirt again. Earlier, we only considered factors like savings, cost of the shirt, etc. All these variables are continuous which may not be the case in real life. While buying shirt factors like its colour or occasion to wear it may also affect your decision and these are categorical variables. So far you have learnt about both classification and regression Decision Trees separately but you might find a dataset containing both types of variables/ features requiring both of them to function together. This can be achieved using CART. 

CART stands for Classification and Regression Decision Trees. They are very similar to the human decision-making process and hence easy to understand. However, the most attractive feature of this algorithm remains the flexibility of input variables i.e., both categorical and continuous. Let us learn about CART from Sajan in the upcoming video:

**VIDEO**

You have already studied the method of measuring purity in the case of both Regression and Classification Tree. While using a CART, the measure used to calculate Information Gain for categorical target variable is the Gini Index. Let us now learn how splitting and selection of root nodes is done in this Decision Tree Algorithm. Sajan will be explaining it to you in the next video:

**VIDEO**

The criteria for splitting in the case of CART is the Gini index. Gini index measures the number of times a random variable is incorrectly identified. It is calculated as follows:
$$\large{Gini=1−\sum^n_{i=1}(p_i)^2}$$
where pi stands for the probability of the classes within variable under consideration.

#### Gini Index

Qn: Considering all the data points in a data set have the same label, what will be the Gini index?

- Gini Index = 1

- Gini Index = 0

- You need exact data to calculate the Gini index.

Ans: B. *The probability of exactly one class will be 1, and the probability of all the other classes will be 0. So, the Gini index, which is given by $1−\sum^k_{i=1}p^2_i$, will be 0.*

Qn: When is the Gini index of a data set high?

- When the homogeneity is minimum.

- When the homogeneity is maximum.

- The Gini index does not depend on the homogeneity.

Ans: A. *When the data set is non-homogeneous, the Gini index, which is a measure of misclassification of the data points will be maximum. The Gini index is minimum when all the points in the data set belong to one class label. It is given by $1−\sum^k_{i=1}p^2_i$*

Qn: When is the information gain maximum? (Select the most appropriate option.)

- When the decrease in entropy, from the parent set to the partitions obtained after splitting, is maximum.

- When the decrease in entropy, from the parent set to the partitions obtained after splitting, is minimum.

Ans: A. *The information gain is equal to the entropy change from the parent set to the partitions. So it is maximum when the entropy of the parent set minus the entropy of the partitions is maximum.*

Qn: How is entropy related to the Gini index?

- The higher the entropy, the higher is the Gini index.

- The lower the entropy, the higher is the Gini index.

- Entropy and the Gini index are not related.

Ans: A. *A high value of entropy and Gini index implies that the data is non-homogeneous and further splitting is required to make it as homogeneous as possible.*

Qn: In a given data set, 50% of the data points belong to label 1, and the other 50% belongs to label 2. Calculate the Gini index.

 - The Gini index $=1−\left[(\frac{1}{2})^2+(\frac{1}{2})^2\right]$

 - The Gini index $=\left[0.5*(\frac{1}{2})^2+0.5*(\frac{1}{2})^2\right]$

Ans: A. $p_1 = 0.5$, and $p_2= 0.5$. So the Gini index, which is given by $1−\sum^k_{i=1}p^2_i$, will be $1−\left[(\frac{1}{2})^2+(\frac{1}{2})^2\right]$

Let us take a look at the next video where Sajan shows how to deal with coronavirus dataset using the Gini index:

**VIDEO**

Just as you calculated entropy in case of classification problem, calculate the Gini index for all the features. The Gini Index values are as follows:

-   Symptoms = 0.342
-   International Travel = 0.367
-   Interaction with an infected person = 0.4285

“Symptoms” has the minimum Gini-Index and is hence selected as the root node. You can follow the same steps to obtain the entire tree. The result looks the same as it did while we solved the case study in the previous segments. But this is _incorrect_ as the split needs to be **binary** as the algorithm is CART. Hence, to do the binary split, as seen in the case of ID3 algorithm, where you calculated the Information Gain for 'Breathing Problem' vs 'Cough + Fever', you can do a similar exercise with Gini and confirm that the node will be split as 'Breathing Problem' and 'Cough + Fever'.

#### CART

Qn: Given that you are working with CART algorithm and want to split the node "Symptoms". So you decide to split it on the basis of "Breathing Problem" and "Fever+Cough". Calculate the total weight Gini Index value. (Choose the option nearest to your answer)

| Sl. No. | Symptoms          | International Travel | Interaction with infected person | Corona Test Result |
|---------|-------------------|----------------------|----------------------------------|--------------------|
| 1       | Fever             | More than 14 days    | Without mask                     | No                 |
| 2       | Fever             | More than 14 days    | With mask                        | No                 |
| 3       | Breathing Problem | More than 14 days    | Without mask                     | Yes                |
| 4       | Cough             | More than 14 days    | Without mask                     | Yes                |
| 5       | Cough             | Less than 14 days    | Without mask                     | Yes                |
| 6       | Cough             | Less than 14 days    | With mask                        | No                 |
| 7       | Breathing Problem | Less than 14 days    | With mask                        | Yes                |
| 8       | Fever             | More than 14 days    | Without mask                     | No                 |
| 9       | Fever             | Less than 14 days    | Without mask                     | Yes                |
| 10      | Cough             | Less than 14 days    | Without mask                     | Yes                |
| 11      | Fever             | Less than 14 days    | With mask                        | Yes                |
| 12      | Breathing Problem | More than 14 days    | With mask                        | Yes                |
| 13      | Breathing Problem | Less than 14 days    | Without mask                     | Yes                |
| 14      | Cough             | More than 14 days    | With mask                        | No                 |![](https://images.upgrad.com/f99deda8-0961-4101-b033-d4e26a6eaed1-table.png)

- 0.43

- 0.36

- 0.50

- 0.27

Ans: B. *You can calculate the Gini Index as follows:*

$Gini(Breathing Problem)=1−\left(\frac{4}{4}\right)^2−\left(\frac{0}{4}\right)^2=0$

$Gini(Fever+Cough)=1−\left(\frac{5}{10}\right)^2−\left(\frac{5}{10}\right)^2=0.5$

$Total\ weighted\ Gini\ Index=\frac{4}{14}∗0+\frac{10}{14}∗0.5=0.36$

CART is an algorithm for building decision trees based on the Gini index as a splitting criterion. It is a binary tree that can be built by splitting nodes into two child nodes repeatedly. Refer to the following steps to build a Decision Tree using CART algorithm:

1.  Calculate the Gini impurity before any split on the whole dataset.
2.  Consider any one of the available attributes.
3.  Calculate the Gini impurity after splitting on this attribute for each of the levels of the attribute.
4.  Combine the Gini impurities of all the levels to get the Gini impurity of the overall attribute.
5.  Repeat steps 2-5 with another attribute till you have exhausted all of them.
6.  Compare the Gini impurity across all attributes and select the one which has the minimum Gini.

While dealing with CART, Gini index is the splitting criteria for classification tree or categorical variables but in case of continuous variables, the splitting criteria are MSE(mean squared error). It can be calculated as follows:
$$\large{MSE=\dfrac{1}{N}\sum^N_{i=1}(\hat{Y}_i−Y_i)^2}$$
Where N is the number of nodes  
$(\hat{Y}_i−Y_i)^2$ is the square of the difference between actual and predicted value.

MSE nothing different from variance which is nothing but the square of standard deviation. You have seen this already in the previous segment. You will be calculating it using regression trees in the next session.

So far you have learnt about CART and how to implement it. However, while dealing with the CART algorithm, the only possible implementation is through binary trees. But you might need a non-binary tree in order to implement your dataset. Take a look at the upcoming video to understand it better: 

**VIDEO**

Now that you are well aware of both the algorithms: ID3 and CART, let us summarise the main key learnings for them:

1.  A categorical tree is one that has class labels as leaf nodes whereas a continuous tree has numerical values as leaf nodes.
2.  CART can only deal with binary trees whereas ID3 can deal with trees having split more than two(non-binary trees) as well.
3.  ID3 uses Entropy/ Information Gain to measure the impurity whereas CART uses Gini Index for categorical target variables.
4.  Both Entropy and Gini-Index measure the impurity of the variable or the number of times a variable is incorrectly classified. Therefore, our aim while building the tree is to achieve a reduction in these values.
5.  CART uses MSE/ Variance for continuous variables.
6.  Standard Deviation is nothing but the square root of MSE value or Variance of a variable.  

## Additional Links:

-   [C4.5 Algorithm](https://cis.temple.edu/~giorgio/cis587/readings/id3-c45.html)
-   [CHAID algorithm for decision trees](https://www.listendata.com/2015/03/difference-between-chaid-and-cart.html) (Chi-squared criteria for splitting and multiway decision trees)