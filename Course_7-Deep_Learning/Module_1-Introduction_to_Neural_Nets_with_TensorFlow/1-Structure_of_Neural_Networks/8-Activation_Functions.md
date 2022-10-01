# Activation Functions

You saw that in perceptrons, the output function applied on the cumulative input is linear. Also, it was previously mentioned that in the case of ANNs, the activation functions are non-linear. In this segment, you will learn about these nonlinear activation functions. But before you understand the different activation functions for ANNs, let’s revise the concept of nonlinearity from Rohit in the upcoming video.

**VIDEO**

Take a look at the image provided below that shows the graphical representation of a linear and a non-linear function.

![Linear vs Non-Linear](https://i.ibb.co/yQgNvHG/Linear-vs-Non-Linear.png)

The activation functions introduce nonlinearity in the network, hence making it capable enough to solve very complex problems. Recall that in the case of perceptrons, you could not perform complex gate functions such as XOR using a single perceptron, but when you used multiple perceptrons, you were able to do so. This is because using multiple perceptrons allowed the model to account for the nonlinearity. However, activation functions in artificial neural networks allow them to handle any such complex tasks, making them a very powerful tool. 

Now that you have revised the difference between linear and non-linear functions, you will now understand how the output is calculated from a single neuron using an activation function. You will also come across various types and properties of common activation functions. Let’s start by understanding how to choose the correct activation function in the next video.

**VIDEO**

The main conditions that you need to keep in mind while choosing activation functions are as follows:

1.  Non-linearity
    
2.  Continuous
    
3.  Monotonically increasing
    

Now that you have a basic understanding of what activation functions are, let’s understand the common types of activation functions in the upcoming video.

**VIDEO**

The most popular activation functions used for neural networks are as follows:

-   Logistic/Sigmoid function:
    
    ![https://i.ibb.co/dBvM2sf/Sigmoid-Function.png](https://i.ibb.co/dBvM2sf/Sigmoid-Function.png)
    
-   Hyperbolic tangent function:  
    
    ![Hyperbolic Tangent Function](https://i.ibb.co/Prg33Nq/Hyperbolic-Tangent-Function.png)
    
-   Rectified linear unit (ReLU):  
     
    ![Rectified Linear](https://i.ibb.co/L9Z7k36/Rectified-Linear.png)
    
      
     
    
-   There is another activation function known as Leaky Relu, which is defined as follows:  

    $\begin{cases}Output=x;\ x≥0\\\\Output=\alpha*x;\ otherwise\end{cases}$
    

The output of a neuron is the activation function applied to the cumulative input to that neuron. Let’s understand how to compute the output of a neuron if you give the inputs, weights, bias and activation function. Let’s watch the next video.

**VIDEO**

Now that you have seen some solved examples of how to compute the output of a neuron, try answering the following questions yourself.

#### Cumulative Input

Qn: Consider a single neuron with the following weight vector and input vector.
$$\large{w=\begin{bmatrix}2\\-6\\3\end{bmatrix}}$$
$$\large{x=\begin{bmatrix}3\\2\\1\end{bmatrix}}$$
and bias b = -1

Calculate the cumulative input for this neuron.

- 4

- -4

- 1

- -1

Ans: B. *You can calculate the cumulative input as follows:*  
$\text{Cumulative input}=w^T*x+b=w_1x_1+w_2x_2+w_3x_3+b$

$\text{Cumulative input}=2*3+(-6)*2+3*1=6-12+3-1=-4$

#### ReLU

Qn: What is the output of this neuron if you use the ReLU activation function (up to three decimal places)?  
 
- -4

- 4

- 0

Ans: C. *Output $=y=x$ for $x>=0$ and 0 or all other values of $x$. $y=-4$, which is $<0$. Hence, output $=0$.*

#### Leaky ReLU

Qn: What is the output of the neuron if you use the Leaky ReLU activation function with α=0.2 (up to three decimal places)?  

- 0.8

- -0.8

- 4

Ans: B. *For y < 0, Leaky ReLU output $=\alpha\\x=-0.8$.*

#### Sigmoid Function

Qn: What is the output of the neuron if you use the sigmoid/logistic activation function (up to three decimal places)?

- 0.018

- 0.982

Ans: A. *$f(y)=\dfrac{1}{1+e^{−x}}$ and $y=-4$. Hence, output $=0.018$.*

So far, you have come across simple neural networks and computed the outputs for them, but this is not the case with real-world applications. The neural networks can be very complex and large. Therefore, you will need some assumptions to make them easier to understand. You will learn about these assumptions in the next segment.