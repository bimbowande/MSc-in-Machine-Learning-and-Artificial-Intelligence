# Perceptron as a Classifier

As you learnt in the previous segment, perceptrons can be used to solve binary classification problems on supervised data. Now that you understand the design of a perceptron, let's consider a simple binary classification task and understand how the perceptron can work as a classifier. Let’s watch the next video.

**VIDEO**

In the video provided above, you saw how a perceptron can be used for binary classification problems. Now, let’s reconsider the example of buying a new house to understand the working of a perceptron as a binary classifier.

Consider that you are thinking of whether or not to buy a house. Multiple factors go into consideration, such as those given below:

1. What is the size of the house in square feet?

2. How many rooms does the house have?

3. How many amenities are available in the neighbourhood?

As discussed earlier, each of these factors has a weight associated with it. This weight represents the importance of the corresponding feature for classification. Let’s take the following weight matrix for this example.
$$\large{\begin{bmatrix}Size\\Number\ of\ rooms\\Amenities\ in\ neighbourhood\end{bmatrix}=\begin{bmatrix}0.5\\0.3\\0.2\end{bmatrix}}$$
For each of the inputs, the rules for deciding 1 and 0 are as follows (Note that these are arbitrary mappings that have been decided to make the model simpler):

|                            |                                                        |                                                             |
| -------------------------- | ------------------------------------------------------ | ----------------------------------------------------------- |
| **Factor**                 | **1**                                                  | **0**                                                       |
| Size                       | > 1500 sq ft                                           | < = 1500 sq ft                                              |
| Number of rooms            | => 3 rooms                                             | < 3 rooms                                                   |
| Amenities in neighbourhood | Parking, healthcare facilities, grocery shops and more | No healthcare facilities or parking complex or nearby shops |

Assume that the bias value is -0.7. 

The area of the house is 1,659 square feet (sq ft), and it consists of two rooms. The neighbourhood has an excellent school, multiple grocery shops and restaurants. It also has the provision for a parking complex and a good hospital nearby.

Try solving the following questions:

#### Input

What is the input vector for the above-mentioned house?  
$$\large{\text{Input Vector}=\begin{bmatrix}Size\\Number\ of\ rooms\\Amenities\ in\ neighbourhood\end{bmatrix}}$$
- $\begin{bmatrix}1\\1\\1\end{bmatrix}$

- $\begin{bmatrix}1\\0\\1\end{bmatrix}$

- $\begin{bmatrix}0\\1\\1\end{bmatrix}$

- $\begin{bmatrix}1\\0\\0\end{bmatrix}$

Ans: B. *The size of the house is 1,659 sq ft (1659>1500); the number of rooms available in the house is two, (2<3) and all the required amenities are present in the neighbourhood. Therefore, the input vector will come out to be as follows: $\begin{bmatrix}1\\0\\1\end{bmatrix}$*

#### Cumulative Input

Qn: Compute the cumulative input for the input vector obtained in the previous question.

- 0.7 

- 0

- 1

- 1.4

Ans: B. *You can calculate the cumulative input as shown below.*  

$\text{Cumulative input}=w^T*x+b=w_1x_1+w_2x_2+w_3x_3+b$

$\text{Cumulative input}=0.5*1+0.3*0+0.2*1+(-0.7)=0.5+0.2-0.7=0$

#### Decision

Qn: Use the step function to find out whether or not you will be buying the house.

- Yes

- No

Ans: B. *The step function of the cumulative input, i.e., $f(0)=0$. Hence, you will not buy a house*

When Frank Rosenblatt proposed the model of a perceptron, it was designed to solve binary classification problems only. Given the input and output labels, one must be able to make the decision based on the weights of different inputs and the bias of the perceptron.  Let’s understand this using vector notation.

You are given the following inputs and their corresponding outputs: $(x_1, y_1),(x2, y2),\dots,(x_n, y_n)$. Let’s take the output function to be a sign function. According to the perceptron function: 
$$\large{y = sign (w^T*x  + b)}$$
Now, given the inputs and their corresponding outputs, you are required to predict the weight matrix and bias such that you can correctly predict the output label from the input label. How can you do this?

Take a look at the equation of the perceptron given above; it is a linear expression and can be represented as a line with equation $w^T*x+b=0$ such that all the points on one side of this line are positive values of $y$ and on the other are negative values of $y$ as shown below.

![Perceptron Classifier 1](https://i.ibb.co/MD91pwR/Perceptron-Classifier-1.png)

This line $w^T*x+b=0$ is known as a separator. This separator is valid only if $w^T*x+b<0$ when $y=-1$ and $w^T*x+b>0$ when $y=1$. Therefore, you can say that $y(w^T*x+b)>0$ should stand true for all data points. If $w^T*x+b<0$, then the separator is not valid as shown below:

![Perceptron Classifier 2](https://i.ibb.co/qNDFD2t/Perceptron-Classifier-2.png)

Now, let's solve some questions to concretise these concepts. Suppose you have the following data points with their corresponding ground truth values as shown in the table below.

|                |                 |
| -------------- | --------------- |
| Data Points, x | Ground Truth, y |
| (0,3)          | 1               |
| (5,9)          | 1               |
| (-1,-2)        | -1              |

 Answer the following questions: 

#### Valid Separator

Qn: Which of the following combinations of (w,b) is a valid separator? (Note: More than one option may be correct.)

- $w=\begin{bmatrix}-1\\1\end{bmatrix}$, $b=−2$

- $w=\begin{bmatrix}-1\\1\end{bmatrix}$, $b=−5$

- $w=\begin{bmatrix}-1\\1\end{bmatrix}$, $b=−1$

- $w=\begin{bmatrix}-1\\1\end{bmatrix}$, $b=1$

Ans: A, C & D. $y(w^T*x+b)>0$ for all data points.


So far, you have been talking about how perceptrons perform binary classification for linearly separable data. But, can they perform classification for data that is non-linearly separable? 

Well, a single perceptron is not capable of performing nonlinear classification. However, multiple perceptrons can achieve this while working together. Let us see how this is done in the upcoming video:

**VIDEO**

It is not possible for the decision boundary/separator to always be linear. There might be certain cases where you will come across complex datasets where you will not be able to split the data points into two planes. Take a look at the image given below.

![Perceptron Classifier 3](https://i.ibb.co/dtwRQG3/Perceptron-Classifier-3.png)

If your data points are distributed in this manner, it will not be possible for you to classify your model using a single separator. But, you can obtain the desired result by using multiple separators to classify your data as shown in the image given below.

![Perceptron Classifier 4](https://i.ibb.co/wyWs3P8/Perceptron-Classifier-4.jpg)

As you can see, this can be done using four different perceptrons, and then computing the resulting output from the individual output of each perceptron as shown in the image below:

![Perceptron Classifier 5](https://i.ibb.co/09vK1ZP/Perceptron-Classifier-5.jpg)

If sum of outputs $=P1+P2+P3+P4>4$, then $Y=1$. 

Else, $Y=-1$

Where, $\large{P_i=W_i∗X_i+b}$

This is how a perceptron can act as an AND gate. Let’s take another example and understand how perceptrons can be used as an OR gate. Take a look at the distribution of data points and separators as shown in the image given below.

![Perceptron Classifier 6](https://i.ibb.co/zZjjcrG/Perceptron-Classifier-6.jpg)

Now, for this example, if the data points lie in a polygon (non-linear separator), the output of the perceptron Pi will be 1; else, it will be -1, i.e., P1 = 1 if data points lie in the separator; else, it will be -1. If neither of these data points lies in any of the separators, the overall sum of outputs of each perceptron will be P1+P2+P3+P4 = - 4 and, in such a case, the overall output will be -1. Hence, you can conclude that:

If the sum of outputs $=P1+P2+P3+P4>-4$, then $Y=1$ 

Else, $Y=-1$

Take a look at the image provided below to understand how a perceptron works as an OR gate.

![https://i.ibb.co/JtSJgN4/Perceptron-Classifier-7.jpg](https://i.ibb.co/JtSJgN4/Perceptron-Classifier-7.jpg)

You can see how a network of perceptrons can act as a universal function approximator. You have seen how a single layer of perceptron in combination with an AND gate leads to an enclosure in a polygon, and multiple such AND outputs using an OR gate lead to an enclosure in multiple polygons. In the most extreme case, this can be extended to finding a polygon for each data point.

Now, let’s try to solve some questions.

#### Separators

Qn: What is the minimum number of perceptrons required to correctly classify the points for the image given below?

![https://i.ibb.co/4YYhP28/Perceptron-Classifier-Qn.png](https://i.ibb.co/4YYhP28/Perceptron-Classifier-Qn.png)

- 1

- 2

- 3

- 4

Ans: B. *You need only two perceptrons as shown in the image given below.*

![Perceptron Classifier Ans](https://i.ibb.co/HCfXCG7/Perceptron-Classifier-Ans.png)

#### AND/OR

Qn: Which gate will you use for the two perceptrons as shown in the image given below?

![Perceptron Classifier Ans](https://i.ibb.co/HCfXCG7/Perceptron-Classifier-Ans.png)

- AND

- OR

Ans: A. *You can use an AND gate for the two perceptrons as shown in the image given above.*

So far, you have learnt about perceptrons, their structure and how they can be used as classifiers. However, as you saw above, a single perceptron on its own is not capable of performing non-linear operations. To do so, you need multiple perceptrons working together to correctly classify the data. To overcome this limitation, many advances were made in the domain of artificial intelligence and deep learning to obtain a powerful tool that can be used to perform a large variety of tasks. Let’s quickly understand how deep learning has evolved over a period of time in the upcoming video.

**VIDEO**

Now, let’s quickly revisit the history of neural networks:

1. The study and research on neural networks started around 75 years ago when Warren McCulloch and Walter Pitts introduced the first neuron to the world. This neuron took inputs in the form of 0 and 1 and the threshold value. This neuron was capable of performing AND, OR, NOT, NAND and NOR gate operations. However, the simplistic nature of inputs did not account for the weights of each input; therefore, this became one of the limitations of the model. In addition to this, it was also not able to perform complex operations such as XOR and XNOR.  
    
2. In 1957, Rosenblatt introduced perceptrons. This perceptron was an advancement to the McCulloch-Pitts neuron and accounted for the weights of each input as well. However, as you learnt earlier, a single perceptron was still unable to solve non-linear classification problems.  
    
3. After a few years, ADALINE (Adaptive Linear Elements) was introduced to the industry; this was one of the first neural networks that were capable of solving real-world problems. However, the expectations from neural networks became unrealistic at that point, which led to dissatisfaction.   
    
4. In 1969, people saw how multiple perceptrons could be used to solve complex problems such as the XOR gate. But, due to high expectations and limited computation resources, it took around 15 years for multilayer perceptron backpropagation to come into the picture, and after another two decades of research, you finally have artificial neural networks.

After all these years of research and development, you now have a very powerful tool, i.e., artificial neural networks, which can solve a wide range of complex problems. In the upcoming segment, you will learn about the fundamental building blocks of ANNs.
