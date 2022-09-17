# Building a Decision Tree: Classification-I

Classification class of model building involves two main steps i.e., learning step and prediction step. In the learning step, the model is trained based on already existing data also called the training data. In the prediction step, the model is used to predict the result for a set of data also known as test data. Decision Trees are the most widely used technique for classification algorithms as these are easily understood and interpreted.

In the case of Classification Decision Trees that are built using the **ID3 algorithm**, the splitting criteria is Entropy. ID3 one of the earliest decision tree algorithms was invented by Ross Quinlan stands for Iterative Dichotomiser 3 and is named such because the algorithm iteratively dichotomizes(divides) features into two or more groups at each step.

**Entropy** is the measure of randomness of a variable. Therefore, more entropy means more randomness which leads to less purity. Entropy quantifies the degree of disorder in the data and its value varies from 0 to 1.

In simple language, a pure dataset means all the data belongs to the same class and the entropy is zero whereas an impure one means data is divided over different classes and the entropy is greater than zero but less than one. Let us learn what entropy is and how it varies in the next video:

**VIDEO**

From the above video, we can conclude that: 
  
>**‘More entropy, less purity’**  
 >or   
>**‘Less entropy, more purity’**

Now that you have obtained the basic idea of entropy, let’s develop a more intuitive understanding using an earlier example in the following video:

**VIDEO**

In the video above, you saw how entropy works using an example of whether or not a person will play hockey. Now try to interpret for the image below, which of the following has more entropy and why? Given that the diagonal line is the line of separation.

![Line of Seperation](https://i.ibb.co/bJwHSby/Line-of-Seperation.png)

The entropy for image 1 is less than that for image 2 as the split in image 1 divides the variables into more homogeneous groups as compared to the ones in image 2. All the above conclusions are made based on the theoretical understanding of entropy, however, this is not possible when it comes to huge datasets. In that case, you will need a formula for computing entropy. Let us see how entropy is calculated using the formula in the next video:

**VIDEO**

The entropy of a variable in a given class can be calculated using the following formula:
$$\large{Entropy=\sum^c_{i=1}−}p_ilog_2p_i$$
Where pi is the probability of the feature/attribute under consideration.

Entropy follows the sum of product (SOP) methodology. As you can see in the formula above, firstly the product of the probability of feature and the logarithmic value of the probability is calculated and then their summation is done for all the features. 

Take the image below and try to understand the outcomes of the formula with the help of graphical representation:

![Entropy vs Probability](https://i.ibb.co/rkdkxGv/Entropy-vs-Probability.png)

Some important facts about Entropy can be derived from the formula/ image above:

1.  If all the variables belong to the same class, the probability is one or zero, entropy is zero and purity is maximum.
2.  If the variables are equally divided over two classes (in case of binary classification), the probability is 0.5 for both the classes, the entropy is 1 and purity is minimum.

Try the following questions based on your learning about Entropy:

#### Entropy

Qn: Consider a set of variables as shown in the image below such that there are 8 data points from one class represented in Red colour and 8 from another class represented in Green colour:

![Entropy Qn](https://i.ibb.co/R0888S7/Entropy-Qn.png)

Calculate the total entropy for the above figure.

- 1

- 0

- 0.5

- Cannot be determined.

Ans: A. *Calculate the entropy as follows:*

$P(red) = P(blue) = 8/16 = 1/2$   

$Entropy_{original}=−P(blue)log_2P(blue)−P(green)log_2P(green)$

$Entropy=−1/2log2(1/2)−1/2log2(1/2)=1$

Qn: Consider a set of variables as shown in the image below such that there are 8 data points from one class represented in Red colour and 8 from another class represented in Green colour:

![Entropy Qn 2](https://i.ibb.co/GHds4Vy/Entropy-Qn-2.png)

The data is split into two parts using a linear boundary. Calculate the total entropy for the above figure after splitting. Hint: Calculate the weighted value of entropy of both the left and right split.

- 0.30 

- 0.28 

- 0.50

- 0.25

Ans: B.  *Calculate the entropy as follows:*

$Entropy_{leftsplit}=0\ (\text{all variables from same class})$  
$Entropy_{rightsplit}=−P(green,\ rightsplit)log_2P(green,\ rightsplit)−P(red,\ rightsplit)log_2P(red,\ rightsplit)$  
$Entropy_{rightsplit}=−(8/9)log_2(8/9)−(1/9)log_2(1/9)=0.15+0.35=0.50$

$Entropy_{aftersplit}=7/16*0+9/16*0.50=0.281$

Qn: Consider a set of variables as shown in the image below such that there are 8 data points from one class represented in Red colour and 8 from another class represented in Green colour:

![Entropy Qn3](https://i.ibb.co/jRBwrBR/Entropy-Qn3.png)

Information Gain is the change in entropy after splitting. In simple words, it is the difference in entropy before and after splitting. Calculate the information for this problem statement.

- 0.75

- 0.5

- 1

- 0.72

Ans: D. *You can calculate the information gain as follows:*  

$Entropy_{original}=1$  

$Entropy_{aftersplit}=7/16*0+9/16*0.50=0.28$  

$Information\ Gain=Entropy_{original}−Entropy_{aftersplit}=1−0.28=0.72$

Now that you are well versed with the entropy and introduced to the concept of information gain, in the next segment you will learn about information gain in more detail and how to create a Decision Tree for the Coronavirus case-study.

So far you have learnt about entropy. However, there are several other impurity measures which you can read about in the links provided in the additional reading segment.

## Additional readings:

1.  For the more curious folks, explore [what happens when we use a base other than 2 for log in entropy?](https://stats.stackexchange.com/questions/87182/what-is-the-role-of-the-logarithm-in-shannons-entropy)