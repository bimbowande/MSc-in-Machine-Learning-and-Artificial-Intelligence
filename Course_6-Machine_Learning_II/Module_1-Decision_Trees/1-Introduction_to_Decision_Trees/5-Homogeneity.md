# Homogeneity

Now that you are aware of the basic idea of a Decision Tree, let's move on to forming a Decision Tree for the given problem statement. The first and very beginning of the process is selecting a Root Node. In order to form a Decision Tree, one must know how to select the node which will lead to the best possible solution. In the next video, Sajan will explain the same to you in much detail.

**VIDEO**

There are two main points to be kept in mind while forming a Decision Tree. 

1.  The simplicity of tree
2.  Homogeneity/Purity

In the next video, Sajan will enlighten you to the concept of homogeneity/purity:

**VIDEO**

For classification tasks, a data set is completely homogeneous if it contains only a single class label which is very difficult to achieve in a real-world dataset. So try to do the best you can, i.e. try to split the nodes such that the resulting nodes are as homogenous as possible. Take a look at the image below for getting a better understanding of the concept of homogeneity.

![Homegeneity Measure](https://i.ibb.co/bmJCbNW/Homegeneity-Measure.png)

While creating a Decision Tree you go step-by-step, picking an attribute and splitting the data such that the homogeneity increases after every split. You stop splitting when the resulting leaves are sufficiently homogenous. 

What is sufficiently homogenous? Well, you define the amount of homogeneity which, when achieved, the tree should stop splitting further. A split that gives you a homogenous subset is much more desirable than the one that results in a 50-50 distribution (in the case of two labels). All the data points belong to one label in a completely homogeneous set.

#### True/False

Qn: An attribute can be present only in one test/node of a decision tree.

- True

- False

Ans:B. *If you test on “International Travel”, then you can have “less than 14 days” as the first test, “more than 14 days” as the second test.*

#### Homogeneity

Qn: The ultimate aim of decision tree splitting is to \_\_\_\_\_.

- Decrease homogeneity

- Increase homogeneity

Ans: B. *More homogeneity will mean that most of the data points in the set belong to the same class label. Hence, classifying all the data points of that set, to get them to belong to that class, will result in lesser errors.*

Qn: What is the homogeneity of the following data set?

![Homogeneity Question](https://i.ibb.co/qRM2LhG/Homogeneity-Question.png)

- Completely non-homogeneous

- Completely homogeneous

Ans: B. *All the data points belong to only one class label, and so this data set is completely homogeneous.*

#### Splitting

Qn: Out of so many attributes, how does a decision tree select one for splitting? Select the best option.

- It picks an attribute at random.

- It calculates the improvement in homogeneity associated with each attribute and picks the one that results in the maximum increase in homogeneity.

- It calculates the improvement in homogeneity associated with each attribute and picks the one that results in the minimum increase in homogeneity.

- It calculates the improvement in homogeneity associated with each attribute and picks the one that results in no change in homogeneity.

Ans: B. *Out of all the attributes, the attribute that results in the maximum increase in homogeneity is chosen for splitting.*

#### Homogeneity

You already know that one of the most important conditions for splitting is to achieve an improvement in purity/homogeneity. Calculate the impurity of data based on the formula given below:   
$$Formula:−P(blue)log_2P(blue)−P(yellow)log_2P(yellow)$$

Calculate the impurity for this image:

![Homogeneity Question](https://i.ibb.co/LZT7Tn2/Homogeneity-Question-2.png)

- 0.8012

- 0.8812

- 0.8112

- 0.8182

Ans: C. *Use the formula given above:* $P(yellow)=6/8=3/4$ ; $P(blue)=2/8=1/4$ 
$Impurity=−P(blue)log_2P(blue)−P(yellow)log_2P(yellow)=−(3/4)log_2(3/4)−(1/4)log_2(1/4)=0.8112$

The value of impurity that you have calculated is known as **entropy**. You will be learning in detail about it in the upcoming segment. Now that you are introduced to the basic criteria that are to be kept in mind while splitting, in the next segment you will learn about Classification Decision Trees and how to select the root node and form a tree with categorical variables.