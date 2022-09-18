# Perceptron

In this segment, you will study a simple device called the perceptron, which was the first step towards creating the large neural networks as you see today. Let's take a quick example to understand how a perceptron works.

Consider that you want to make a decision whether to buy a house or not. Multiple factors go into consideration to take the decision, such as:

1.  What is the size of the house in square feet?
    
2.  How many rooms does it have?
    
3.  What are the amenities available in the neighbourhood?
    

Let’s consider this example and try to understand the perceptrons and their working in the upcoming video:

**VIDEO**

A perceptron acts like a tool that enables you to make a decision based on multiple factors. Each decision factor holds a different ‘weight’ - for example, Rohit may consider the amenities around the house to be more important than the other two factors. Perceptrons work similarly: they take the different factors as input signals, attach a weight based on their importance, and perform basic operations to make a decision.

In other terms, the perceptron takes a weighted sum of multiple inputs (along with a bias) as the cumulative input and applies an output function on the cumulative input and returns the output. 
$$\Large{Cumulative\ Input=w_1x_1+w_2x_2+w_3x_3+b}$$
Where, xi’s represent the inputs, wi’s represent the weights associated with inputs and b is the bias.

Shortly, you will be talking about everything in terms of vectors and matrices. So, let's start using these terms from now. Let’s say ‘w’ and ‘x’ are vectors representing the weights and inputs as follows (note that, by default, a vector is assumed to be a column vector).
$$\Large{x=\begin{bmatrix}x_1\\x_2\\\vdots\\x_k\end{bmatrix},\ w=\begin{bmatrix}w_1\\w_2\\\vdots\\w_k\end{bmatrix}}$$
A neat and concise way to represent the weighted sum of w and x is using the dot product of wT and x. Let us understand this concept of taking the dot product of transpose of weight vectors and the input vectors.

The transpose of $w$ is $w^T=\begin{bmatrix}w_1&w_2&\dots&w_k\end{bmatrix}$ - a row vector of size 1 x k. Taking the dot product of wT with $x$:
$$\Large{w^T*x=\begin{bmatrix}w_1&w_2&\dots&w_k\end{bmatrix}*\begin{bmatrix}x_1\\x_2\\\vdots\\x_k\end{bmatrix}}$$
After adding bias to $w^T*x$, you will get the following equation:
$$\Large{Cumulative\ Input=w^T*x+b=w_1x_1+w_2x_2+w_3x_3+b}$$
Now, to obtain the output, an output function is applied to the cumulative input. There are two most commonly used output functions, which are as follows:

1.  **Step function:** This function is applied on the cumulative input, i.e., it returns 1 if the input is positive; else, it returns 0. In other words, the perceptron ‘fires’ (returns 1) if the cumulative input is positive and ‘stays dormant’ (returns 0) if the input is negative.
    

Y = 1 if x > 0

Y = 0 if x <= 0

![](https://images.upgrad.com/da4fe4b1-2952-4560-92d2-d7b3f8dcc94b-5.png)

  
 

2.  **Sign function:** This function is applied on the cumulative input, i.e., it returns 1 if the input is positive; else, it returns -1. In other words, the perceptron ‘fires’ (returns 1) if the cumulative input is positive and ‘stays dormant’ (returns -1) if the input is negative.
    

Y = 1 if x > 0

Y = -1 if x <= 0

![](https://images.upgrad.com/db40e2b4-b0d4-45d7-ae73-d17988b7f155-6.png)

Now, try computing the outputs for the following questions.

#### Cumulative Input

You have the following vectors. 
$${w=\begin{bmatrix}3\\1\\5\\7\\4\end{bmatrix},\text{ and }x=\begin{bmatrix}1\\1\\0\\1\\0\end{bmatrix}}$$

Qn: The bias value is -2. Calculate the cumulative input to the perceptron.

- 18

- 11

- 9

- 16

Ans: C. *Calculate the cumulative input using the formula given below.*  
$\text{Cumulative input}=w^T*x+b=w_1x_1+w_2x_2+w_3x_3+b$

$\text{Cumulative input}=3*1+1*1+5*0+7*1+4*0+(-2)=3+1+7-2=9$

Qn: The bias value is -2. Consider that the step function is used as the output function. Following the discussion above, what is the output of the perceptron? 

- 0

- 1

Ans: B. 

Qn: The bias value is -13. Following the discussion above, what is the output of the perceptron? Consider the sign function as defined above in the discussion.

- 0

- 1

- -1

Ans: C. *You can calculate the output as follows:*

$\text{Cumulative input}=w^T*x+b=w_1x_1+w_2x_2+w_3x_3+b$

$\text{Cumulative input}=3*1+1*1+5*0+7*1+4*0+(-2)=3+1+7-13=-2$

As you can see above, the output of a perceptron in the case of a step function is either 1 or 0 and that in the case of a sign function is either 1 or -1. In both cases, the output is classified into two different classes. Perceptron hence forms a powerful classification algorithm for supervised learning. In the next segment, you will understand how perceptrons can be used for classification.