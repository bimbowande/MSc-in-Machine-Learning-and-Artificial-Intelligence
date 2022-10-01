# Training a Neural Network

In the previous session, you learnt how information passes through neural networks. In this segment, you will learn how neural networks are trained. Let’s hear from Usha as she elaborates on this:

**VIDEO**

You have trained various machine learning models in the previous modules. As you already know, to train a linear regression model, you need to tune the slope and intercept to achieve a decision boundary for which the error is minimum. Similarly, to train a logistic regression model, you need to compute the optimal values for $\beta$’s. To conclude, you can say that the aim of **training a model** is to **optimise** the **model parameters** in order to **minimise the error**. 

This error is a function of the predicted and actual outputs of the model. It is given by the following equation:
$$\Large{Error~or~Loss=f(Predicted~output,~Actual~output)}$$
In the case of neural networks, the training task involves computing the optimal weights and biases by minimising some cost function. Let’s try to understand with the help of an example in the upcoming video:

**VIDEO**

#### Parameters

Qn: According to you understanding, what should be the training parameters in the case of deep learning model?

- Weights

- Number of layers

- Bias

- Number of neurons in a layers

Ans: A & C. *The parameters of neural network training are weights and biases.*

You will be using the same neural network that you saw in the previous session. This model consists of an input layer with two neurons, two hidden layers with three neurons each and an output layer with a single neuron, as shown below.

![Sample Nerual Network](https://i.ibb.co/FW353Gv/Sample-Nerual-Network.png)

You have already computed the predicted output of the model to be 0.94993. If the actual output of the model is 1, then you can compute the error in the regression model by using the following mean squared error formula:
$$\large{MSE=\dfrac{1}{n}\sum^n_{i=1}(y'−y)^2}$$

Where,  
n is the number of data points in the output,  
y is the actual output, and  
y’ is the predicted output.

For this example, you know that $n=1$, $y'=0.94993$ and $y=1$. Therefore, after adding the values, you will get the following:
$$\large{MSE=(0.94993−1)^2=0.00251}$$

So far, you have computed loss by using a frequently used loss function in the case of regression problems. There are some other loss functions that can be used while computing the loss in the model. Let’s quickly revise them in the upcoming video.

**VIDEO**

Some commonly used loss functions are as follows:  
**Classification problems**

1.  Binary cross-entropy loss: $−ylog(y')−(1−y)log(1−y')$
2.  Multi-class cross-entropy Loss: $−\sum^n_{i=1}ylog(y')$

    Note: The log used in these formulas is a natural $log(ln)$.

An **interesting point to note** here is that binary cross-entropy loss is derived from the formula of multiclass cross-entropy loss. How can this be done?

  
In the case of binary cross-entropy loss, the output will be either 1 (belongs to a certain class) or 0 (does not belong to a certain class). In this case, the value of n will be 2. Therefore, you will get the following: $−\sum^2_{i=1}ylog(y')=−y_1log(y'_1)−y_2log(y'_2)$.

For instance, suppose you have to predict whether a given image in the MNIST data set is the digit ‘3’ or not. If ‘3’ is the digit in the image, the actual output will be 1 which is y1 (belongs to the class), or else 0 which is y2 (does not belong to the class). Hence, you can see that $y_1=1−y_2$.

Similarly, if the predicted output of the model y′1 (is the digit 3) is 0.8, then (is not the digit 3) will automatically be 0.2. This is because the sigmoid predicts the probability of the image belonging to the class, i.e, y′1. Therefore, by the probability theory, y′1+y′2=1, where y′2 is the probability of not belonging to the class.

Hence, you can write, $y'_1=1−y'_2$.

Therefore, you can rewrite the loss function as $−y_1log(y'_1)−y_2log(y'_2)$ as $−ylog(y')−(1−y)log(1−y')$.

Now that you have an understanding of the commonly used classification losses, let us also take a look at regression losses as given below:

  
**Regression problems**

1.  Mean squared error (MSE): $\dfrac{1}{n}\sum^n_{i=1}(y'−y)^2$
2.  Mean Absolute error (MAE): $\dfrac{1}{n}\sum^n_{i=1}|y'−y|$

MSE is a more commonly used error/ loss when it comes to regression problems. This is because the **square term** in the formula of MSE identifies the existence of the outliers in the model by giving more weightage to higher error terms. Additionally, MSE is differentiable at all points as compared to MAE and this will come in handy during backpropagation.

Try to solve the following questions.

#### Cross-Entropy Loss

Qn: For the neural network shown in the image below, compute the cross-entropy loss.

![](https://images.upgrad.com/0885e74f-178a-4b7d-b982-d1a2f4b555cb-pasted%20image%200%20(3).png)

Given:  
Predicted output: y’ = 0.94993  
Actual output: y = 1

- -0.051

- 0.513

- -0.513

- 0.051

Ans: D. *Compute the cross-entropy loss for the given neural network as follows:*  
$$\large{Loss=−y*log(y')−(1−y)*log(1−y')}$$$$\large{=-1*log(0.94993)-0*log(1-0.94993)}$$$$\large{=-log(0.94993)= 0.051}$$
An important point to note is that if the volume of data is large (which is often the case), the loss calculation can get pretty messy. For example, if you have a million data points, they will have to be fed into the network (in batch), the output will be calculated using feedforward and the loss Li (for the ith data point) will be calculated. The total loss is the sum of the losses of all the individual data points and is also referred to as the cost function.

  
Hence, $\large{Total~loss=L_1+L_2+L_3+....................+L_{1000000}}$.

The total loss L is a function of weights, w and biases, b. Once the total loss is computed, the weights and biases are updated (in the direction of decreasing loss). In other words, L is minimised with respect to the w's and b's. This can also be written in the form of an algorithm as follows:

1.  Output, $y'_i=h^{l+1}(w,~b,~x_i)$, here $h^{l+1}$ is the output of the final output layer.
2.  Loss = $L(h^{l+1}(w,~b,~x_i),~y_i)=L(y'_i,~y_i)$
3.  Total cost = −Σni=1L(y′i,yi)
4.  Training problem: Minimise the overall cost/loss of the model = $min(w,b)\left[−|sum^n_{i=1}L(y'_i,y_i)\right]$

Note that you minimise the average of the total loss and not the total loss. Minimising the average loss implies that the total loss is getting minimised.

This process of minimisation can be done using any optimisation routine, the most commonly used is gradient descent. We will discuss this in the next few segments.