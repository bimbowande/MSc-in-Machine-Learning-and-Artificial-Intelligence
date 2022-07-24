# Building a Decision Tree: Regression

In this segment, you shall understand how to build a regression tree using categorical as well as the continuous variables. This acts as the foundation for the regression trees in the CART  algorithm which shall be covered in the next segment.

Let's say you are planning on buying a shirt, there will be various factors that you will keep in mind before making the purchase. Such as the price of a shirt, your savings or the discount offered, etc. These are continuous variables and to deal with them you cannot use entropy to calculate the information gain. For such continuous variables, Regression Decision Trees are used. But before moving forward to Regression Decision Trees, let us learn how to deal with continuous variables from Sajan in the upcoming video.

**VIDEO**

In order to deal with continuous values, you can sort them and then find the midpoints and calculate information gain for those midpoints. Once we find the value with the highest information gain, that particular value is selected as the root node. So far you have learnt how to deal with continuous variables. Now you will learn how to use them and implement a Regression Decision Tree.

But you might be wondering why not simply use linear regression to solve such a problem? There are cases where you cannot directly apply linear regression to solve a regression problem because its applications are limited by the assumptions. Linear regression will fit only one model to the entire data set; whereas you may want to divide the data set into multiple subsets and apply linear regression to each set separately. Let us take an example to understand this better.

Suppose you want to predict the weight of the person given the age and height. If you try to plot the age on x-axis and height on the y-axis in the form of a linear model, you will get something similar to the one shown in the image below:

![Regression Decision Tree 1](https://i.ibb.co/z7PPmc6/Regression-Decision-Tree-1.png)

For infants (age<3) and people above 25 years (age>25), the growth will not be very rapid and hence the slope is not very steep. However, 3 to 25 years (3<age<25) can be considered as the growing age of the person and hence the steep slope will signify the rapid increase in the weight of an individual. However, a slow down in growth rate is seen after the age of 25 (age>25) and the decrease grows rapidly during old age. Therefore, there is no single linear model which will be able to predict this completely. Hence, you can divide this into different buckets and use a Decision Tree model as shown in the image below:

![Regression Decision Tree 2](https://i.ibb.co/VMFXPy6/Regression-Decision-Tree-2.png)

In regression problems, a decision tree splits the data into multiple subsets. In this case, the leaf node consists of continuous values as opposed to the categorical labels in case of classification problems. The leaves in a classification tree have the values as the label of the majority class while for a regression tree, it would be average of the target values of all the data points present in that particular leaf.

While working with a categorical target variable, you have used entropy in order to calculate the information gain of a feature. But this does not work for a continuous target variable. In the case of a continuous target variable, you can use standard deviation; the reduction in standard deviation becomes the measure of purity.

#### Regression Decision Trees

Qn: Select all that is correct about decision tree classification and regression models.

- Leaves in classification contain labels.

- Leaves in regression contain labels.

- Leaves in regression contain the average of target values of the data points in the leaf as the prediction for that leaf.

- Leaves in regression contain models.

Ans: A & C. *In classification, the target variable is discrete. Hence, each data point in a leaf has an associated class label. Each leaf in regression contains an average value as the prediction.*

#### Decision trees

Qn: Say you have a data set with lots of categorical variables and some numerical variables. The target variable is continuous, so it’s a regression problem. After some exploratory data analysis, you figure out that it will be best to perform decision tree regression instead of linear regression. Which of the following statements will be correct? 

- It is hard to represent all the data via a single model; so you don’t want to use the linear regression model.

- Decision trees require less data preparation.

- Decision trees require normality assumptions.

Ans: A & B. *Decision tree regression is performed because the entire data set cannot be represented by a single linear regression model. In decision trees, you do not have to treat missing values, outliers and multicollinearity before proceeding with model building.*

Let us learn how to work with Decision Trees for Regression in the next video. Regression trees are the trees where the target variable is continuous.

**VIDEO**

The process of selection of the root node and the further splitting remains similar to that in the case of categorical decision trees. The only difference is the measure considered to calculate the homogeneity of the system i.e., standard deviation instead of entropy. The feature with maximum reduction in standard deviation before and after splitting is selected as the root node. Take a look at the coronavirus case-study observation table below which now has a continuous target variable. Note that here, all the features are categorical.

![Regression Decision Tree Example Table](https://i.ibb.co/m5njXSc/Regression-Decision-Tree-Example-Table.png)

Let us now see with the help of the coronavirus case-study example how calculations are done and a solution arrives in the next video.

**VIDEO**

Following is the formula used to calculate standard deviation:

$$S_n=\sqrt{\dfrac{1}{N}\sum^N_{i=1}(x_i−\bar{x})^2}$$

where:  
$N$ is the number of data points,   
$x_i$ is ith data,   
$\bar{x}$ is average (mean) of all data.

As we did in the previous segment for the case of the classification task, here, we calculated the reduction in standard deviation for all the features. The reduction in standard deviation is maximum for symptoms and hence it is selected as the root node. A similar process can be repeated recursively until the entire tree is obtained.

This was an example where we had just the continuous target variable and the features were categorical. Let us now consider the case where feature variables in the dataset are also continuous. How will you select a root node? How will splitting happen? All these questions are addressed in the next video.

**VIDEO**

While selecting the splitting value in case of continuous variables, the factor measured is the reduction in variance. The formula is as follows: 

$$\dfrac{\sum{(X−\bar{X})}}{2n}$$

As you can see, the variance is simply the square of standard deviation and hence it wouldn’t matter if you use standard deviation. The key thing you need to focus on is how to figure out the splitting value for continuous variables. While working with continuous feature variables, as seen at the start of the segment, sort them in ascending order and then find the midpoint for all the data points. Calculate the reduction in variance before and after the split for each of the midpoints. The one with maximum reduction in variance is selected as the root node. There are other methods to find this split for continuous feature variables which you'll learn in the next session.

Use the above Coronavirus dataset to create a Decision Tree as shown in the steps below and answer the following questions:

-   Calculate the Standard Deviation of percentage infection.
    -   Calculate the mean/average of the values.
    -   Apply the standard deviation formula and compute the result.

#### Regression Decision Trees

Qn: What is the standard deviation of the percentage of infection at source?

- 9.32

- 8.45

- 9.89

- 8.79

Ans: A. *You can find the standard deviation as follows:*  
*The average of % of infection = (25+30+46+45+52+23+43+35+38+46+48+52+44+30)/14 = 39.78*  
$Standard\ Deviation = \dfrac{((25−39.78)^2+(30−39.78)^2+...+(44−39.78)^2+(30−39.78)^2)^{1/2}}{14}=9.32$

-   Calculate the Standard Deviation for Symptoms, International Travel and Interaction with an infected person.
    -   For each feature calculate the mean and standard deviation as done in the above step.
    -   Calculate the reduction in standard deviation: the difference between the standard deviation at source and standard deviation of the split nodes according to the feature under consideration.
    -   Select the feature that has the maximum value of the reduction in standard deviation as the root node.

#### Regression Decision Trees

Calculate the reduction in Standard Deviation for all the features and select the correct option.

-  Reduction in SD (Symptoms) = 1.05  
Reduction in SD (International travel) = 0.27  
	Reduction in SD (Interaction with infected person) = 0.30

-  Reduction in SD (Symptoms) = 1.05  
Reduction in SD (International travel) = 0.27  
	Reduction in SD (Interaction with infected person) = 0.29

-  Reduction in SD (Symptoms) = 1.66  
Reduction in SD (International travel) = 0.27  
	Reduction in SD (Interaction with infected person) = 0.29

-  Reduction in SD (Symptoms) = 1.66  
Reduction in SD (International travel) = 0.27  
Reduction in SD (Interaction with infected person) = 0.31

Ans: C. *You can calculate the reduction in standard deviation for interaction with infected person as follows:*  
*Standard Deviation(% infection) = 9.32*  
*Standard Deviation(without mask) = 7.37*  
*Standard Deviation(with mask) = 10.59*  
*Standard Deviation (Interaction with infected patients) = 6/14*7.37 + 8/14*10.59 = 9.03  
Difference = 9.32- 9.03 = 0.29*  
*Similarly, you can calculate for other features as well.*

-   As the maximum value of the reduction in standard deviation is for “symptoms”, it is selected as the root node and we now have the following tree:  
     
![Regression Decision Tree Example](https://i.ibb.co/M52rfHJ/Regression-Decision-Tree-Example.png)

-   Now, calculate the reduction in standard deviation for “International travel” and “Interaction with infected patients” keeping “Symptoms” as the root node.  Here, let's build the tree for the Fever branch.

#### Regression Decision Trees

Qn: Select the correct option.

- Reduction in SD (Fever, International Travel) = 3.33  
Reduction in SD (Fever, Interaction with infected person) = 0.85  
International Travel is selected for the split as the reduction value is more than that for interaction with infected patients.

- Reduction in SD (Fever, International Travel) = 0.87  
Reduction in SD (Fever, Interaction with infected person) = 0.54  
International Travel is selected for the split as the reduction value is more than that for Interaction with infected patients.

- Reduction in SD (Fever, International Travel) = 0.87  
Reduction in SD (Fever, Interaction with infected person) = 2.45  
Interaction with infected patients. is selected for the split as the reduction value is more than that for International Travel.

- Reduction in SD (Fever, International Travel) = 0.67  
Reduction in SD (Fever, Interaction with infected person) = 0.85  
Interaction with infected patients. is selected for the split as the reduction value is more than that for International Travel.

Ans: A. *Average(Fever)=(25+30+35+38+48)/5=35.2*  
*Standard Deviation(Fever)=7.78*  
*Standard Deviation(Fever,International travel)= 3/5*4.08 + 2/5*5=4.45  *
*Reduction = 7.78 - 4.45 = 3.33*

*Standard Deviation(Fever,Interaction with infected patients)= 3/5*5.56 + 2/5*9 = 6.93*  
*Reduction = 7.78 - 6.93 = 0.85*  
*3.33 > 0.85, Therefore,International travel is selected.*

-   If the number of leaf nodes is large, calculating average for each becomes a tedious task. Therefore, maxBins function comes into play. You will learn about it in the next session.
-   Repeat the same steps for other features until you reach the leaf nodes.
-   Once, you have reached the point where you cannot further split the tree, calculate the average of values at the leaf node. 

The final tree that you will obtain is shown in the image below:

![Regression Decision Tree Covid Case Study](https://i.ibb.co/87yfNgK/Regression-Decision-Tree-Covid-Case-Study.png)

Note that, here also, you could have binary split at the root node, Symptoms, which is the case when you implement using CART algorithm. Though this would give lesser information gain as shown in the classification task in the previous segment.

#### Regression Tree

Qn: The above diagram has an incomplete leaf node shown by a "?". Complete it by selecting the correct option.

- 25

- 30

- 27

- 45

Ans: B. *The leaf nodes represent the average of values present.*

In the tree above, you can continue splitting further. However, it is not done as the information gain becomes very less and hence not much information can be extracted by splitting further.

"min_samples_split" is a hyperparameter which denotes the minimum number of samples required to split an internal node. You will be studying in detail what hyperparameters are and the significance of "min_samples_split" in the next session.

In this segment, you have seen how to build regression trees using both continuous and categorical features. The splitting criterion that you use here for regression trees is the standard deviation or the variance for both categorical and continuous features. The key thing in case of continuous features is how to find the split point. With this, you are all set to learn about the CART algorithm in the next segment.

## Additional Reading:

1.  To learn more about Decision Trees, you can refer to the [Decision Trees scikit-learn documentation](http://ogrisel.github.io/scikit-learn.org/sklearn-tutorial/modules/tree.html).