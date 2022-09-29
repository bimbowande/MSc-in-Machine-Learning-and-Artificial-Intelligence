# Loss Function

In this session, you will learn what you mean by optimization from the fundamentals of gradient descent and then move on to the ways in which you can improve your training using different optimization techniques.

You have already been introduced to what optimization means and how at the end of the day, most of the algorithms boil down to an optimization problem. Almost all the algorithms that you have learnt until now with the exceptions of Random Forest essentially boil down to an optimization problem.

An optimisation problem involves defining an objective function that needs to be minimised to get the best results. Even the neural network training problem is an optimization problem where you learn the best set of weights and biases to minimise the loss function. It is an unconstrained optimization problem as you have no constraints on the values of weights and biases. 

In the next video, you'll explore if you are right in defining the loss function the way you have until now.

**VIDEO**

#### Loss Function

Qn: You are given the MNIST dataset with the following hand-drawn image:

![MNIST Three](https://i.ibb.co/Hg6VTXV/MNIST-Three.png)

What will be the loss if the actual label is 8?

- Loss = 1

- Loss = 0

Ans: A. *In classification problems, the loss function is defined as follows:

$Loss =\begin{cases}0~\text{if}~y~(\text{actual label})=y'~(\text{predicted label})\\\\1~\text{otherwise}\end{cases}$

As you can see, the loss is in terms of 0 or 1 which is not a differentiable term. Therefore, a surrogate function is required that gives the desired output and is also differentiable.*

The loss function you have been using to train the neural network is given by the following formula:
$$\large{−\sum^C_{i=1}(y~log(y'_i))}$$

where $y'_i$ is the predicted output and $y_i$ is the actual output of the model.

This is the **empirical loss** which is different from the **theoretical loss**. Let us understand the difference between the two losses as given below:

1.  The theoretical loss is the actual loss that occurs if you consider all the data points that you can possibly have.
2.  The empirical loss on the other hand loss that occurs if you consider the data points in the training dataset.

But you are not entirely wrong in using the empirical loss function as there have been studies that show empirical loss is similar to theoretical loss given the number of data points 'n' is large.

Now, let's look at another issue related to the loss function that you have been using until now. This problem arises specifically involving classification in discrete classes if you used the simple class wise comparison loss that can be given by the following formula:
$$\sum^n_{i=1}(y'_i\ne\\y_i)$$
Using this formula would not help us in understanding how the output of the neural network change with delta change in the input. Also, since you know that neural networks train using backpropagation, you need a **differential loss function** and the function given above is not differentiable.

Hence, you use a **surrogate loss function** like the cross-entropy loss for a classification scenario defined as $\sum^C_{i=1}(ylog(y'_i))$. Though y′is are not discrete values, you use them to find the discrete predicted class. In other words, you have defined a surrogate function that helps us satisfy both conditions:

1.  The outcomes are discrete values
2.  The loss function is differentiable

Let's look at some of the other interesting observations related to the cross-entropy loss function in the next segment.