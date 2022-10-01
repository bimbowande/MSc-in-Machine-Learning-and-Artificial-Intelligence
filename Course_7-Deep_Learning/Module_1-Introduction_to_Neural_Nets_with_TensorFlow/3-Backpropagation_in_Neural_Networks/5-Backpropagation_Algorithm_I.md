# Backpropagation Algorithm - I

In the previous segment, you learnt how neural networks are trained. In the upcoming segments, you will learn about the **backpropagation algorithm** that is used for training in **neural networks.** 

  
By the end of this session, you should be able to build and train your own neural network in NumPy from scratch. However, before you proceed further to complex neural networks, you will solve some simple examples to develop a good understanding of this algorithm.

  
Let’s hear from Usha as she explains the concept of backpropagation in neural networks.

**VIDEO**

#### Activation Function

Qn: How will you define the linear activation function? 

- $y=x\text{ for all }x~\in~Real$

- $\begin{cases}y=x;~\text{for all}~x>0\\y=0;~otherwise\end{cases}$

Ans: A. *Linear activation means the output will be equal to the input for all values. Note that this is different from ReLU.*

In the video above, you learnt about the history of backpropagation. Backpropagation is one of the most important steps involved in the process of building and training neural network models. It was initially formulated by researchers in the early 1960s and was enhanced and familiarised as an important concept in neural networks in 1986.

**Backpropagation**, as the name suggests, refers to the **backwards propagation of errors** by **updating** the values of **model parameters** to **minimise the error** and in turn **optimising the model.**

Let’s now solve a very simple neural network problem to understand this concept. Consider a neural network with an input layer and an output layer with one neuron each as you saw in the video. The input and the actual output are given. For the sake of simplicity, you will take bias as zero and activation as linear activation for this example. 

The neural network and the corresponding values are given below.

![Sample Neural Network](https://i.ibb.co/YbsDYT3/Simple-Neural-Network.png)

Let’s start by calculating the value of the cumulative input as follows:
$$\Large{z=w*x+b=1.5w+0=1.5w}$$  
The output of the model: $y'=f(z)=1.5w$ (as it is the linear activation function)
$$\large{Loss=f(y',~y)}$$
$$\large{MSE~Loss=(y'−y)^2=(1.5w−2)^2}$$

So far, you have learnt how to calculate the output of the model and the MSE loss. Now, let’s backpropagate this error and update the weights of the model. \[Note that you are only updating the weight as you have taken bias as zero]. Let’s watch the next video on how to solve this problem.

**VIDEO**

According to the gradient descent algorithm,
$$\large{w_{new}=w_{old}−\alpha*\dfrac{\delta\\L}{\delta\\w}}$$

Using the chain rule,
 $$\large{\dfrac{\delta\\L}{\delta\\w}=\dfrac{\delta\\L}{\delta\\y'}*\dfrac{\delta\\y'}{\delta\\w}}$$
$$\large{\dfrac{\delta\\L}{\delta\\y'}=\dfrac{\delta(y'-y)^2}{\delta\\y'}=2(y'−y)}$$
$$\large{\dfrac{\delta\\y'}{\delta\\w}=\dfrac{\delta(1.5w)}{\delta\\w}=1.5}$$
$$\large{\therefore~\dfrac{\delta\\L}{\delta\\w}=2(y'−y)∗1.5=3(y'−y)=3(1.5w−2)=4.5w−6}$$

In neural networks, the weights are initialised to random values, and during backpropagation, these values are updated to the optimised values. Let’s take a random value of weight for this example and check how it is updated in the upcoming video.

**VIDEO**

As shown in the video above, if the initial weight, $w=0.3$ and $\alpha=0.1$, the predicted output of the model will be as follows:
$$\large{z=w*x+b=1.5w=1.5∗0.3=0.45}$$
$$\large{y'=f(z)=0.45}$$

The loss of this model will be as follows:

$$\large{MSE~loss=(y'−y)^2=(1.5w−2)^2=(0.45−2)^2=2.4025}$$

The updated weight can be calculated as follows:
$$\large{w_{new}=w_{old}−\alpha*\dfrac{\delta\\L}{\delta\\w}}$$
$$\large{w_{new}=w_{old}−\alpha*(4.5w-6)=0.3-0.1*(4.5*0.3-0.6)}$$
$$\large{w_{new}=0.3−0.1(−4.65)=0.765}$$

The predicted output of the model can be calculated as follows:
$$\large{y'=1.5w=1.5∗0.765=1.1475}$$

The new loss of this model can be calculated as follows:
$$\large{MSE~loss=(y'−y)^2=(1.5w−2)^2=(1.1475−2)^2=0.7267}$$

As you can see, the error for the initial value of weight is much higher than the one for the updated value. Similarly, you can continue updating weights and biases until you reach the point of convergence. Now, try to solve this problem with another iteration.

#### Updating Weights

Qn: Try to solve the problem for another iteration, and select the correct options from below.

- $w_{new}=1.02075,~y'=1.531125$

- $L=0.29$

- $L=0.22$

- $w_{new}=1.02075,~y'=1.66735$

Ans: A & C. *You can calculate wnew and y’ as follows: $w_{new}=0.765-0.1*(0.765*1.5-6)=1.02075$ and $y'=1.5w=1.5*1.02075=1.531125$. You can caclulate the loss of the model as follows: $L=(1.5w-2)^2=(1.5*1.02075 -2)^2=0.2198437656\approx0.22$*

By now, you have gained a basic understanding of the backpropagation algorithm. In the upcoming segments, you will be going through a few more solved examples and techniques to derive equations for this algorithm.