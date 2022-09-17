# Building a Decision Tree: Classification-II

In the previous segments, you learnt about Entropy and how it is calculated. You also learnt what information gain is. Now you will learn about **Information Gain** and its significance in building a decision tree. You will also implement your learnings and create a Decision Tree for the Coronavirus case-study.

You have already learnt that information gain is the measure of the change in entropy. It calculates the decrease in entropy after a split. In the upcoming video, Sajan will introduce you to the concept of Information Gain.

**VIDEO**

Information Gain is the main deciding parameter in order to figure out which feature to split at each node. Our main aim while splitting is to keep our tree as small as possible because it makes the tree easier to interpret and visualize. Another important factor to be kept in mind is purity. The end solution should have maximum purity as compared to other trees that can be created in place of it.

The metric that we use to measure the increase in purity is information gain. As the name suggests information gain calculates the measure of information we can get from a variable.  It is the difference between the entropy before and after split for a particular feature. The process of splitting is continued until the value of information gain is zero or very small.

#### Information Gain

Qn: When is the information gain maximum? (Select the most appropriate option.)

- When the decrease in entropy, from the parent set to the partitions obtained after splitting, is maximum.

- When the decrease in entropy, from the parent set to the partitions obtained after splitting, is minimum.

Ans: A. *The information gain is equal to the entropy change from the parent set to the partitions. So it is maximum when the entropy of the parent set minus the entropy of the partitions is maximum.*

Now that you have learnt what information gain is and its significance, you will be using it to create Decision Trees on your own, further in this segment. But in order to do so, you should first know a few assumptions that we should keep in mind while creating a tree. Following are the assumptions:

1.  When we begin creating the tree, the whole set of training data is considered at the root node for splitting.
2.  A recursive approach is followed while creating the tree.
3.  You will be using a statistical approach while finding the root node and internal nodes.

Steps to create a Decision Tree:

1.  Obtain a tabular representation of the given data.
2.  Calculate the entropy for all the features in the dataset for different splits.
3.  Calculate the information gain i.e., the change in entropy.
4.  The node with the highest information gain is selected as the root node.
5.  Divide the tree on the root node and repeat the above process to further split until leaf nodes are obtained.

Now let's use the same and create a Decision Tree for Coronavirus case-study. In the upcoming video, Sajan will be computing the information gain and showing you how to select the root node and form a Decision Tree from it.

**VIDEO**

In the video above, Sajan has used the Coronavirus case-study to show how a decision tree can be created. The table of observations for the same set of data is shown below:

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
| 14      | Cough             | More than 14 days    | With mask                        | No                 |

Let us stepwise analyse the process and create a Decision Tree to find out whether or not a person has coronavirus or not.

-   Calculate the entropy at source i.e, ‘Corona Test Result’
    - $P(Yes)= 9/14$, $P(No)=5/14$
    - $Entropy= -P(Yes)log_2P(Yes)-P(No)log_2P(No)$
    - $Entropy= -(9/14)log_2(9/14) - (5/14)log_2(5/14)=0.94$  
         
-   For feature= ‘Symptoms’ this can be done easily using the table below:

| Feature  | Test      | Yes | No | Total |
|----------|-----------|-----|----|-------|
| Symptoms | Fever     | 2   | 3  | 5     |
| Symptoms | Breathing | 4   | 0  | 4     |
| Symptoms | Cough     | 3   | 2  | 5     |

-   Now, calculate the entropy for each feature. Note that here, you are considering that the split is happening 3 ways, i.e 'Symptoms' splits into Fever, Breathing and Cough.
    -   Entropy for “Fever” = 0.97
    -   Entropy for “Breathing Problem” = 0
    -   Entropy for “Cough” = 0.97
    -   Total entropy of symptoms= 5/14 * 0.97 + 4/14 * 0 + 5/14 * 0.97 =0.69  
         
-   Similarly calculate for other features i.e, International Travel and Interaction with Infected people.  
     
-   Calculate the information gain i.e., the difference between entropy at source and entropy of feature.  
     
-   Calculate information gain for all the features i.e., Symptoms, International travel, interaction with an infected person. You get the following.
    -   IG for “Symptoms” = 0.25
    -   IG for “Interaction with infected person” = 0.048
    -   IG for “International Travel” = 0.152  
         
-   The information gain is maximum for “Symptoms” and hence it is chosen as the root node. At this point, the Decision Tree looks as shown in the image below:

![Coronavirus Case-Study Symptoms](https://i.ibb.co/qJDD691/Coronavirus-Case-Study-Symptoms-2.png)

-   Now that we have established that “Symptoms” forms the root node of our tree, we will find out how to split the trees further by looking at their entropy. 
    -   Entropy for “Fever” = 0.97
    -   Entropy for “Breathing Problem” = 0
    -   Entropy for “Cough” = 0.97  
         
-   The entropy for “Breathing Problem” is zero as all the outcomes in case of this feature lead to a positive case of coronavirus according to the given set of data, therefore it is not further split whereas “Fever” and “Cough” will be further split depending on the information gain. So now the tree structure after selecting the root node looks somewhat like the image shown below:

![Coronavirus Case-Study Symptoms 3](https://i.ibb.co/BnxxWVw/Coronavirus-Case-Study-Symptoms-3.png)

-   Now for Cough, we'll get the data points as shown in the following table:

|       |                   |              |     |
|-------|-------------------|--------------|-----|
| Cough | More than 14 days | Without mask | Yes |
| Cough | Less than 14 days | Without mask | Yes |
| Cough | Less than 14 days | With mask    | No  |
| Cough | Less than 14 days | Without mask | Yes |
| Cough | More than 14 days | With mask    | No  |

-   Information Gain(Cough, International Travel) can be calculated as follows:
    -   P(less than 14 days)= 3/5, P(more than 14 days)= 2/5
    -   Entropy(less than 14 days)=−23log223−13log213=0.9182
    -   Entropy(more than 14 days)=−12log212−12log212=1
    -   Entropy(Cough, International Travel)=35∗0.9182+25∗1=0.95
    -   Information Gain(Cough, International Travel) =0.97−0.95=0.02  
         
-   Information Gain(Cough, Interaction with an infected person) can be calculated as follows:
    -   P(without mask)= 3/5, P(with mask)= 2/5
    -   Entropy(without mask)=0
    -   Entropy(with mask)=0
    -   Entropy(Cough, Interaction with an infected person)=35∗0+25∗0=0
    -   Information Gain(Cough, Interaction with an infected person)= 0.97−0=0.97  
         
-   Information Gain(Cough, Interaction with an infected person)>Information Gain(Cough, International Travel). Therefore, split is done on Interaction with an infected person.  
     

Similarly, you can calculate the information gain for “International Travel” and “Interaction with an infected person” for “Fever” and split on them until you obtain the final tree. Try completing the above tree based on the steps you have learnt so far and try to answer the following questions.

#### Coronavirus case-study

Qn: How many leaf-nodes does the coronavirus case-study tree have?

- 4

- 5

- 3

- 6

Ans: B. *There are 5 leaf nodes in the Decision Tree for this case-study.*

Qn: In which of the following cases is the patient affected with the virus?

- The person has breathing problems but has not travelled internationally in the past 14 days and has not interacted with an affected person.

- The person has a cough and has interacted with an infected person without a mask.

- The person has a fever and has travelled internationally in the past 14 days.

- The person has a cough and travelled internationally and also interacted with an infected person but with a mask.

Ans: A, B & C.

- *All the people showing breathing problems are infected with this virus according to the data available with us.*
- *As you can see in the final Decision Tree, people with cough and a history of interaction with an infected person with a mask are themselves exposed to the virus.*
- *People with fever and international travel within the last 14 days of having a fever also have this virus.*

The final tree is shown in the image below:

![Coronavirus Case-Study Symptoms](https://i.ibb.co/yXzPN0g/Coronavirus-Case-Study-Symptoms-4.png)

Note that this is different from the tree that you saw at the start of the session. This is the optimal tree that you get when you follow the ID3 algorithm. Note that we have not split the tree further as we get 2/3 data points in each leaf node. This is considered as a **stopping criterion** so that you don't keep building the tree until you have 1 data point in each leaf. You'll learn more about this in the upcoming segments.

In the above tree, if you have observed closely, we have split the tree 3 ways at the root note 'symptoms'. You could have asked 'Why not do a binary split?'. Let's see what we get when we assume binary split. Calculate the Information Gain and answer the question below:

#### Information Gain

Qn: In order to perform the binary split, you are grouping "Fever" and "Cough". From the table given below, calculate the revised information gain for "Symptoms".

| Feature  | Test          | Yes | No |
|----------|---------------|-----|----|
| Symptoms | Fever + Cough | 5   | 5  |
| Symptoms | Breathing     | 4   | 0  |

- 0.25

- 0.23

- 0.24

- 0.22

Ans: B. 

$P(Fever+Cough)=10/14$

$P(Breathing\ Problem)=4/14$

$Entropy(Fever+Cough)=−(5/10)log_2(5/10)−(5/10)log_2(5/10)=1$

$Entropy(Breathing\ Problem)=−(4/4)log_2(4/4)−0=0$

$Overall\ Entropy=(10/14)∗1+(4/14)∗0=0.71$

$Entropy(At\ source)=0.94$

$Information\ Gain=0.94-0.71=0.23$

The Information Gain for "Symptoms" for a ternary split was 0.25 and that for binary split is 0.23. You can observe that the Information Gain value decreases for a binary split. Hence, we have considered the ternary split. You can try out different combinations for binary split and verify this, i.e Breathing + Cough & Fever and Breathing + Fever & Cough. One interesting thing to note here is that there are decision tree algorithms like **CART** that restrict the split to **binary** to reduce the complexity and make it more interpretable. You'll learn about it shortly.

So far we have learnt about Classification Decision Trees using the ID3 algorithm. If you have observed closely, we have considered all the features that are used for splitting as categorical and even the target variable is categorical. This is one of the limitations of the ID3 algorithm that it build to handle only categorical variables for classification tasks only.  However, there are several other algorithms for decision trees that overcome this limitation. In this course, we will be dealing with one other algorithm. Let us summarise the ID3 algorithm in the next video.

**VIDEO**

The two main algorithms covered as part of this course are:

1.  ID3
2.  CART

We have already learnt in detail about the ID3 algorithm that deals with categorical variables. CART deals with both categorical and continuous variables at the same time and can be used for both classification and regression tasks.

#### Choice of algorithm

Suppose you were asked by the HR of your company to form a team of employees with interest and calibre in sports for an upcoming match between various offices in your city. For the process of selection requires you to examine the following features about each employee: “Age”, “Gender”, “Height”, “Past sports record”, “Health-issues”, etc. Which of the following Decision Tree algorithms will you employ to make the process of decision making easier for yourself?

- ID3

- CART

Ans: B. *The features under consideration are both categorical and continuous, therefore in order to deal with them using CART is the suitable option.*

#### Decision Trees

Qn: Consider the following tree:

![Decision Tree Qn](https://i.ibb.co/rkmbnJZ/Decision-Tree-Qn.png)

Which is the most informative feature, as identified by the tree?

- Age

- Thal

- pain.typ

- Flourosc

Ans: B. *The most informative features are towards the top of a tree.*

You will be learning about CART in detail in the upcoming segments. In the next segment, you'll see how to build a regression decision tree.