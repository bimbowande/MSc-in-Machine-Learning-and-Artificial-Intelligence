# Decision Trees - Introduction

In the process of decision analysis, Decision Trees can be used to represent the decision making visually. As the name suggests, a Decision Tree is a flow-chart like structure which helps in making predictions. A Decision Tree is a predictive model that resembles an upside-down tree. It is a supervised learning method i.e., it has a fixed target variable but unlike Logistic Regression, it is not parametric. A parametric algorithm is one in which data can be divided over a certain set of parameters. Parameters restrict the flexibility of the model as the models can only be built around the parameters. Therefore we can conclude that Decision Trees are more flexible as compared to Logistic Regression.

A Decision Tree is very similar to how you make decisions in real life: you ask a series of questions to arrive at a decision. A decision tree splits the data into multiple sets. Then, each of these sets is further split into subsets to arrive at a decision.

**VIDEO**

Decision Trees can be considered a set of if-then-else statements. In other words, the process of making decisions is followed by asking questions with two or more possible outcomes. The outcome is decided based on which condition is satisfied. Let us assume that you are in a dilemma of whether or not to go out to buy a cake of soap. How will you arrive at a decision? Let us study this simple Decision Tree example as shown in the image below:

![Soap example](https://i.ibb.co/r6f6vrh/Soap-example.png)

You will ask yourself a set of questions: Do you need more soap? Or Do you have soap at home? Based on your need for soap you can decide whether or not you want to buy more but will you be able to buy soap on that day depending on various other factors such as the weather outside, amount of time you have in order to go to a shop or availability of the product at the shop, etc?

Therefore you will ask the second set of questions, in the given image, weather conditions are taken into consideration. If it is raining outside, going out at that given point of time is not the best possible solution. Otherwise, given the need for soap and clear weather, you can go out and buy yourself soap. This is the basic concept followed by Decision Trees while arriving at a conclusion.

Now that you're aware of how a decision tree works, let us explore an example of how decision trees may be used by industry professionals.

A Program Manager (PM) has to make a decsision about whether his team should proactively start working on a project.

![Program Manager Decision Tree](https://i.ibb.co/s1w56vF/Program-Manager-Decision-Tree.jpg)

Program Manager Decision Tree

The PM asks a set of questions:

-   Is the project essential for the company's growth?
    -   If it is, he directs his team to start work.
    -   If it is not, he asks a set of further questions.
-   Does the project involve taking significant risks?
    -   If it does, he directs his team to not start work.
    -   If it doesn't, he asks another question.
-   Does the project help in team building?
    -   If it does, he directs his team to start work.
    -   If it doesn't, he directs his team to not start work.

#### Decision Trees

Qn: Which of the following is correct for Decision Tree?

- It is a flowchart that represents the algorithm.

- The leaf nodes of the Decision Tree represent target class-labels.

- It is a tree structure that makes the process of decision making easier.

- All of the above

Ans: D.

As you are already aware of the two different kinds of variables: Categorical and Continuous and that one of the major advantages of a Decision Tree is that it can deal with both categorical and continuous variables. Another advantage that decision trees or trees, in general, is that they can be used for both classification and regression tasks. Let us learn from Sajan about the two types of Decision Trees in the upcoming video:

**VIDEO**

You have seen that the following are the two types of Decision Trees:  
 

**Classification Decision Trees** 

1.  Classification Decision Trees deal with categorical target variables.
2.  The target variable takes a discrete set of values.
3.  In such tree structures, class labels are represented by leaves and branches represent conjunctions of features that lead to those class labels. 
4.  The predicted outcome is a discrete value.
5.  E.g If a mail is a spam or not? or Given the weather conditions will you be able to go out or not?

**Regression Decision Trees**

1.  Regression Decision Trees have continuous output variables.
2.  The predicted outcome can be considered a real number.
3.  E.g. How long will a patient stay in the hospital? Or The cost of a product on an e-commerce website.

#### Classification Decision Trees

Qn: Consider the following tree:

![Classification Decision Tree - Question](https://i.ibb.co/Y0wBR69/Classification-Decision-Tree-Question.png)

a, b, c, d, e, f, g, h, i, j are the attributes. A test on attribute ‘a’ can yield 3 possible values: 1, 2 and 3. Similarly, tests on other attributes can yield 2 values: 1 and 2. You have 2 class labels: 0 and 1. Predict the class labels for the following cases:

Case1: a=2, c=2, h=2

Case2: a=1, b=2, f=1

Case3: a=3, d=1, i=2

- 0, 0, 1

- 1, 0, 0

- 1, 1, 0

Ans: A. *For case1, from ‘a’ go to ‘c’ and then to ‘h’, following the lines corresponding to ‘a=2’ and ‘c=2’. The class label associated with case1 will be at the end of the line, with ‘h=2’. This will be similar for other cases as well.*

#### Predict Classes

Netflix is looking to recommend premium membership to some of its existing members. For this, they have constructed the decision tree given below:

![Netflix Recommendation Decision Tree](https://i.ibb.co/BrR5t7j/Netflix-Recommendation-Decision-Tree.png)

Predict the class labels for the following cases:

**Case1**: The old membership period is > 1 year, gender is male, and no. of violations is < 2.

**Case2**: The old membership period is < 1 year, avg. hours spent per day < 2, and most-watched content-type is movies.

**Case3**: The old membership period is > 1 year and gender is female

- Case 1: Recommend Premium  
   Case 2: Recommend Premium  
   Case 3: Don't Recommend Premium

- Case 1: Recommend Premium  
   Case 2: Don't Recommend Premium  
   Case 3: Recommend Premium

- Case 1: Don't Recommend Premium  
   Case 2: Recommend Premium  
   Case 3: Recommend Premium

Ans: B. *Test on each of the attributes and proceed down the tree to the appropriate leaf node. For this, you will get Recommend, Don't Recommend, and Recommend respectively.*

You will be studying both classification and regression trees in detail in the upcoming segments.