# Updating Weights and Biases - I

In this segment, you will learn how to backpropagate errors to update the model parameters: weights and biases in a neural network with multiple layers and multiple neurons in each layer. For this, we will reconsider the same neural network that we have been using so far, as given in below.

![Sample Nerual Network](https://i.ibb.co/FW353Gv/Sample-Nerual-Network.png)

This model consists of an input layer with 2 neurons, 2 hidden layers with 3 neurons each and an output layer with a single neuron. For this derivation, you will be considering the activation function to be sigmoid for all the layers. 

Note: Notice that the predicted output is p, and not y’, which you have been using so far. This is simply to avoid confusion in the derivation process. So, the actual output is y, and the predicted output is p for this derivation.

#### Backpropagation

Qn: Suppose you have m data points in the training data set. Arrange the following five computation steps as they appear in one iteration of the backpropagation algorithm:

1.  Feedforward the ith data point.
2.  Compute the gradient of the loss with respect to weights and biases.
3.  Update the weights and biases.
4.  Compute the loss of the ith data point.
5.  Aggregate (compute the average of) m losses.

- 1, 4, 2, 5, 3

- 1, 4, 5, 2, 3

- 1, 5, 4, 2, 3

- 1, 4, 5, 3, 2

Ans: B. *The data points are first fed forward, the loss of each data point is computed and aggregated (to compute the average loss), the gradient of loss is computed, and finally, weights and biases are updated once.*

Let’s quickly revise the notations and dimensions, before proceeding to the derivation.

**VIDEO**

The weights and biases for this derivation are mentioned below.
$$\large{W^{1}=\begin{bmatrix}w^{[1]}_{11}&w^{[1]}_{21}\\w^{[1]}_{12}&w^{[1]}_{22}\\w^{[1]}_{13}&w^{[1]}_{23}\end{bmatrix},~W^{2}=\begin{bmatrix}w^{[2]}_{11}&w^{[1]}_{21}&w^{[2]}_{13}\\w^{[2]}_{12}&w^{[2]}_{22}&w^{[2]}_{23}\\w^{[2]}_{13}&w^{[2]}_{23}&w^{[2]}_{33}\end{bmatrix},~\text{and}~b=\begin{bmatrix}b^{[1]}\\b^{[2]}\\b^{[3]}\end{bmatrix}}$$

You learnt about these matrices and vectors in the previous session. You will be deriving the equations for a generalised model. Therefore, the numeric values are replaced with w’s and b’s.

Note: W represents the batch of weights and w represents single points. Both these will be used throughout the derivation.

The feedforward equations for this example, as derived in the previous session, are as follows:
$$\large{z^{[l]}=W^{[l]}*h^{[l−1]}+b^{[l]}}$$
$$\large{h^{[l]}=\dfrac{1}{(1+e^{−z^{[l]}})}}$$

So far, you have learnt how to obtain regression outputs. In this derivation, you will solve a classification problem using binary cross-entropy loss where this model will classify whether or not the input feature belongs to a certain class.

The loss for a classification model-Cross-Entropy (CE) loss can be written as follows:  
$$\large{L=−(ylog(p)+(1−y)log(1−p))}$$

Before proceeding further, let’s quickly revise the CE loss by solving the following questions.

#### CE Loss

Qn: The cross-entropy is defined as $CE~loss=−(y_1log(p_1)+y_2log(p_2)+y_3log(p_3))$. Let’s assume the following values:  $y_1=1$. Hence, $y_2=y_3=0$. $p_1=0.8,~p_2=0.1$ and $p_3=0.1$. What will be the value of the CE loss (upto 1 decimal place)? Note that the log for e = 2.718.

- 0.2

- 0.3

Ans: A. *You can calculate the loss as follows:*

$CE~Loss=−(y_1log(p_1)+y_2log(p_2)+y_3log(p_3))$

$CE~Loss=−(1*log_e(0.8)+0*log_e(0.1)+0*log_e(0.1))=−log_e(0.8)=0.22314\approx0.2$

Qn: The cross-entropy is defined as $CE~loss=−(y_1log(p_1)+y_2log(p_2)+y_3log(p_3))$. Let’s assume the following values: $y_1=1$. Hence, $y_2=y_3=0$. $p_1=0.8,~p_2=0.1$ and $p_3=0.1$.  What will be the value of the CE loss (upto 1 decimal place)? Note that the log for $e=2.718$.

- 2.4

- 2.3

Ans: B. *You can calculate the loss as follows:*

$CE~Loss=−(y_1log(p_1)+y_2log(p_2)+y_3log(p_3))$

$CE~Loss=−(1*log_e(0.8)+0*log_e(0.1)+0*log_e(0.1))=−log_e(0.8)=2.30258\approx2.3$

You would have noticed in the above questions that when pi is close to yi, the CE loss is lesser as compared to when it is not, which goes in accordance with the intuition of loss.

Now that you are well-equipped with the knowledge of the loss function, let’s proceed further. The updated weight can be calculated as follows:
$$W_{new}=W_{old}−\alpha*\dfrac{\delta\\L}{\delta\\W}$$

Next, you need to start propagating backwards and update $W^{[3]}$. Using the chain rule, you can write $\dfrac{\delta\\L}{\delta\\W^{[3]}}$ as follows:
$$\large{\dfrac{\delta\\L}{\delta\\W^{[3]}}=\dfrac{\delta\\L}{\delta\\p}*\dfrac{\delta\\p}{\delta\\z^{[3]}}*\dfrac{\delta\\z^{[3]}}{\delta\\W^{[3]}}}$$

Let’s watch the next video to learn how to calculate $\dfrac{\delta\\L}{\delta\\W^{[3]}}$.

**VIDEO**

As you learnt in the video above, $\dfrac{\delta\\L}{\delta\\W^{[3]}}$ can be written as $\dfrac{\delta\\L}{\delta\\W^{[3]}}=dz^{[3]}*\dfrac{\delta\\z^{[3]}}{\delta\\W^{[3]}}$ where $dz^{[3]}=\dfrac{\delta\\L}{\delta\\p}*\dfrac{\delta\\p}{\delta\\z^{[3]}}=\dfrac{dL}{dz^{[3]}}$.

You calculate each individual component in the $\dfrac{dL}{dz^{[3]}}$equation and then find their product as follows:
$$\large{\dfrac{\delta\\L}{\delta\\p}=\dfrac{(−(ylog(p)+(1−y)log(1−p)))}{\delta\\p}=−\left(\dfrac{y}{p}+\dfrac{(1−y)}{(1−p)}\right)}$$$$\large{\dfrac{\delta\\L}{\delta\\p}=\dfrac{p-y}{p(1-p)}}$$
You can explore more on differentiation of log [here](https://www.math24.net/derivatives-logarithmic-functions).

Let’s watch the next video to understand how do we calculate $\dfrac{\delta\\p}{\delta\\z^{[3]}}$.

**VIDEO**

As you saw in the video,
$$\large{\dfrac{\delta\\p}{\delta\\z^{[3]}}=\dfrac{\delta\left(\dfrac{1}{1+e^{-z^{[3]}}}\right)}{\delta\\z^{[3]}}=−1∗−1∗e^{−z^{[3]}}∗(1+e^{−z^{[3]}})^{−1−1}=\dfrac{e^{−z^{[3]}}}{\left(1+e^{−z^{[3]}}\right)^2}}$$

can be written as $p(1−p)$. Take a look at how this is done:
$$\large{\dfrac{\delta\\p}{\delta\\z^{[3]}}=\dfrac{e^{−z^{[3]}}}{\left(1+e^{−z^{[3]}}\right)^2}~\text{and}~p=\dfrac{1}{(1+e^{−z^{[3]}})}}$$
$$\large{\dfrac{\delta\\p}{\delta\\z^{[3]}}=\dfrac{e^{−z^{[3]}}}{\left(1+e^{−z^{[3]}}\right)^2}=\dfrac{e^{−z^{[3]}}}{\left(1+e^{−z^{[3]}}\right)}*\dfrac{1}{(1+e^{−z^{[3]}})}}$$
$$\large{p(1−p)=\dfrac{1}{(1+e^{−z^{[3]}})}∗\left(1−\dfrac{1}{(1+e^{−z^{[3]}})}\right)}$$

$$\large{p(1−p)=\dfrac{1}{(1+e^{−z^{[3]}})}∗\dfrac{1+e^{−z^{[3]}}-1}{(1+e^{−z^{[3]}})}=\dfrac{e^{−z^{[3]}}}{\left(1+e^{−z^{[3]}}\right)}*\dfrac{1}{(1+e^{−z^{[3]}})}}$$

Therefore, you can write $\dfrac{e^{−z^{[3]}}}{\left(1+e^{−z^{[3]}}\right)^2}$ as $p(1−p)$.  
  
Finally, substituting the values into the formula $dz^{[3]}=\dfrac{\delta\\L}{\delta\\p}*\dfrac{\delta\\p}{\delta\\z^{[3]}}$, you will obtain the following result:
$$\large{dz^{[3]}=\dfrac{\delta\\L}{\delta\\z^{[3]}}=\dfrac{(p−y)p(1−p)}{p(1−p)}=p−y}$$

Now that you have computed $\dfrac{\delta\\L}{\delta\\z^{[3]}}$, the next step is to use this and compute $\dfrac{\delta\\L}{\delta\\W^{[3]}}$ using the formula discussed previously. Let us see how it is done in the next segment.