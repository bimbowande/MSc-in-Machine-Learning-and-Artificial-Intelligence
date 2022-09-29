# Vanishing and Exploding Gradients

One of the major problems you face while you build deep neural networks is the problem of Vanishing and Exploding gradients. Let's see why the gradients vanish or explode in the upcoming video.

**VIDEO**

In the above video, you heard about vanishing and exploding gradients. Let us, deep-dive, into these two concepts and understand the reason behind them.

Let us first consider the case of **vanishing gradients**. You have computed gradients for weights and biases during backpropagation. These gradients usually consist of multiple terms multiplied by each other. Now consider, if all these terms are very small (less than 1), the product of these terms will end up being a very small value.

Recall, the formula for weight updates:
$$\Large{w_{new}=w_{old}−\alpha∗\dfrac{\delta\\L}{\delta\\w}}$$

Now, as you already know the commonly used value of learning rate, $\alpha=0.01$ and if the value of $\dfrac{\delta\\L}{\delta\\w}$ is very small, the product of these terms will also be very small and $w_{new}\approx~w_{old}$. Hence, it will either take a very long time for the function to reach convergence or it will fail to reach convergence.

Similarly, in the case of **exploding gradients**, if all the terms in the gradient are very large, the product of these terms will end up being a large value. Therefore the new weight will be much smaller than the old weight due to the 'minus' sign in the formula i.e., $w_{new}<w_{old}$, and you will not be able to reach the minima.

Some of the ways to mitigate the vanishing and exploding gradients problem are:

1.  Gating which you'll study in RNNs
2.  Residual Connections will be introduced in CNNs
3.  Batch normalization, you have already studied

In the next segment, you'll get to know about the different initialization strategies.