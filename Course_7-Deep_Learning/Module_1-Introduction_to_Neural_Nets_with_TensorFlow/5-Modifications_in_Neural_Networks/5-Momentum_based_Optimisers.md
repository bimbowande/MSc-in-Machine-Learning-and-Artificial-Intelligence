# Momentum based Optimisers

So far, you have learnt about batch, stochastic and mini-batch gradient descent methods. Stochastic and mini-batch gradient descent algorithms are more widely used as compared to batch gradient descent as you have learnt in the previous sessions.

However, these algorithms also come with their fair share of limitations. Let us understand a few of them:

1.  It is difficult for the gradient descent variants(such as SGD) to navigate through very steep curves or **ravines**.
2.  As the number of updates in SGD is very large in number, it takes a long time to reach convergence.
3.  It is difficult to select the value for the learning rate α which returns the optimal results.

These limitations hinder the performance of these algorithms. In this segment, you'll cover some of the popular optimizers that will help in training the neural networks efficiently as compared to the gradient descent variants. Let's start with momentum-based gradient descent in the upcoming video.

**VIDEO**

In the above video, you learnt how it is difficult for SGD algorithms to traverse through ravines. Let understand it by looking at the image below:

![Stochastic Gradient Descent](https://i.ibb.co/mRvQmJ0/Stochastic-Gradient-Descent.png)

The SGD algorithm finds difficulty in navigating through steep curves as one data point is selected at once in order to update the parameter. Due to the randomness in the points, the **gradient is noisy** as compared to that of batch gradient descent. But using batch gradient at the cost of high requirement of time and memory is also not a feasible choice, Therefore, optimisers come into the picture.

The first optimiser you will be learning is a momentum-based optimiser. In order to learn about this technique, you require to learn about **exponential moving average.** It is commonly used in the financial domain to track the price of a particular commodity over time. It is given by the following formula:
$$\large{v_t=\beta\\v_{t−1}+(1−\beta)\theta_t}$$

where  t denotes the current time step, vt denotes the current exponential moving average, vt−1 denotes the previous exponential moving average, β is a hyperparameter and θt today's price.

Let us use this concept and jump into the implementation of momentum-based optimisers. So far you have used the following equation to update the parameters using gradient descent.
$$\large{W_{new}=W_{old}−\alpha∗dW\text{ and }b_{new}=b_{old}−\alpha∗db}$$  $$\large{\text{where, }~dW=\dfrac{\delta\\L}{\delta\\W}\text{ and }db=\dfrac{\delta\\L}{\delta\\b}}$$
In momentum-based methods you will update the parameters as follows:

1.  On iteration t:
    1. Compute $dW$, $db$ for the given mini-batch
    2. $v_{dW}=\beta∗v{dW}+(1−\beta)dW$
    3. $v_{db}=\beta∗v_{db}+(1−\beta)db$
    4. Update the parameters: $W_{new}=W_{old}−\alpha∗v_{dW}$ and $b_{new}=b_{old}−\alpha∗v_{db}$

where $\alpha$ and $\beta$ are hyperparameters. 

As you can see in the above formulas, rather than directly multiplying $dW$ and $db$ with the learning rate α, you first calculate the exponential moving average of the gradients and then use them to update the parameters. 

Now you might wonder how does this solve the issue of noisy gradients and traversing through ravines? Well, by incorporating the exponential moving average into the parameter update formula, you basically tune the noisy gradients and find their average before updating the parameters. This makes the traversal through ravines a lot easier as shown below:

![Gradient Descent with Momentum](https://i.ibb.co/NZ6Rz2W/Gradient-Descent-with-Momentum.png)

Even though the learning rate is big and you jump back and forth, it doesn't seem to affect when you apply momentum-based gradient descent. The reason behind this is that the unstable gradient direction which makes it jump back and forth keeps getting cancelled out and the other gradient though being small keep on accumulating and ultimately gets to the minimum. Hence, this helps in reaching the minimum faster.

In the next segment, you will learn about another interesting optimiser: **Adagrad.**