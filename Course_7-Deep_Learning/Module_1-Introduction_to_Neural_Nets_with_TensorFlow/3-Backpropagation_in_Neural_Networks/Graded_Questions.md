# Graded Questions

Try to solve the following graded questions. All the best!

#### Learning in Neural Networks

Qn: A neural network learns by adjusting the weights and biases such that the loss is minimised. The ‘learning’ in a neural network happens during \_\_\_\_\_.

- feedforward

- backpropagation

- cost function evaluation

- None of the above

Ans: B. *The ‘learning’ in a Neural network is essentially adjustment of weights and biases. That happens during backpropagation. The network doesn’t change (learn) during feedforward.*

#### Gradient of Loss Function

Qn: The gradient of the loss with respect to the weights for a particular layer used in the update step would be a ____.

- vector

- tensor

- matrix

- scalar

Ans: C. *Check the dimension of W. The update step should have the same dimensions of all its arguments. Hence, this would be a matrix because W is a matrix.*

#### Gradient Calculation

Qn: Mark the correct statement about the gradient calculation of loss L with respect to the weights W of different layers in a neural network, from below.

- The gradient of $L$ wrt layer $l$ is calculated using the gradient wrt layer $l−1$

- The gradient of $L$ wrt layer $l−1$ is calculated using the gradient wrt layer $l$

- The gradient of $L$ wrt layer $l+1$ is calculated using the gradient wrt layer $l−1$

Ans: B. *The gradients are calculated using backpropagation, i.e. the gradient of $L$ wrt layer $l-1$ is calculated using the gradient wrt layer $l$.*

#### Weights and Biases

Qn: In a single forward-backwards pass through the network \_\_\_\_\_.

- The weights and biases of one layer gets updated

- The weights and biases of all the layers layer get updated

- Only the weights of one layer gets updated

- Only the biases of one layer gets updated

Ans: B. * In each iteration, we calculate the loss and update the weights and biases of each layer to minimise the loss.*

**Comprehension - Regression Using Neural Networks**The neural network given below is designed for a regression task. There is only one neuron in the output layer. The output of

the network is denoted by the scalar variable $r$. The loss function is defined as $L=\dfrac{1}{2}(y−r)^2$, where $y$ is the true value (a numeric scalar) of the input data point $x$.

The activation function of the last layer is the pass-through function, i.e., it allows the input to pass through the last layer without any changes. Hence, $r=z^3$. The network is illustrated in the diagram given below.

![Graded Questions](https://cdn.upgrad.com/UpGrad/temp/65c712f0-8dde-4dd5-8b66-4914bac535cf/Regression.png)

We pass a single datapoint and get the above shown quantitites. Now, we have to do backpropagation. **Please note** that there is a bias of the layer 3:  $b^3$. Answer the following questions based on this information:

Since the activation function is the pass-through function, we know that $r=z^3$. Hence it follows that $\dfrac{\delta\\L}{\delta\\r}=\dfrac{\delta\\L}{\delta\\z^3}=dz^3$. Now, we want to calculate $dh^2$. **Please note** that there is a bias of the layer 3:  $b^3$.

Based on this scenario, answer the following questions.

#### Backpropagation

Let's start the backpropagation with the last layer, i.e., the output layer containing one neuron. What will be the expression for $\dfrac{\delta\\L}{\delta\\r}$?

- $r−y$

- $y−r$

Ans: A. *Compute the partial derivative of the loss function $L$ with respect to $r$ as follows: $\dfrac{\delta\\L}{\delta\\r}=\dfrac{\delta\left(1/2(y-r)^2\right)}{\delta\\r}=0.5*2*(-1(y-r))=r-y$*

Similarly, by calculating $dh^2_2$, you can show that $dh^2=\begin{bmatrix}dh^2_1\\dh^2_2\end{bmatrix}=\left(W^3\right)^T.dz^3$ which is what we have derived in the session earlier. 

#### Weight Matrix

Qn: What is the dimension of $W^3$?

- (2,2)

- (1,2)

- (2,1)

Ans: B. *The shape of $W^l$ = (number of neurons in layer $l$, number of neurons in layer $l-1$). Therefore, the dimensions will be (1, 2).*

Qn: We can write $W^3=\begin{bmatrix}w^3_{11}&w^3_{12}\end{bmatrix}$. The output of the 2nd layer $h^2=\begin{bmatrix}h^2_1\\h^2_2\end{bmatrix}$. What is $z^3$?

- $w^3_{11}h^2_1+w^3_{12}h^2_2+b^3$

- $w^3_{11}h^2_1+w^3_{12}h^2_2$

Ans: A. *You can compute the value of z3 as follows: $z^3=\begin{bmatrix}w^3_{11}&w^3_{12}\end{bmatrix}.\begin{bmatrix}h^2_1\\h^2_2\end{bmatrix}+b3=w^3_{11}h^2_1+w^3_{12}h^2_2+b^3$*

#### Computing dh

Qn: Which of the following is the correct expression for $\dfrac{dL}{dh^2_1}$? (Consider $z^3$ to be the intermediate variable.) 

- $\dfrac{\delta\\L}{\delta\\z^3}.\dfrac{\delta\\z^3}{dh^2_1}$

- $\dfrac{\delta\\L}{\delta\\z^3}.\dfrac{\delta\\z^3}{dh^2_1}+\dfrac{\delta\\L}{\delta\\z^3}.\dfrac{\delta\\z^3}{dh^2_2}$

- $\dfrac{\delta\\L}{\delta\\z^3}.\dfrac{\delta\\z^3}{dh^2_2}$

Ans: A. *$\dfrac{dL}{dh^2_1}$ can be calculated as follows:*
1. $L$ is a function of $z^3$.
2. $z^3$ is a function of $h^2_1$.
3. On applying the chain rule, you will get the following: $\dfrac{\delta\\L}{\delta\\z^3}.\dfrac{\delta\\z^3}{dh^2_1}$.

Qn: What is the value of $\dfrac{dL}{dh^2_1}$ or $dh^2_1$? Use the expression generated in the previous question. More than one options may be correct.

- $dz^3.w^3_{11}$

- $dz^3.w^3_{12}$

- $(r-y).w^3_{11}$

- $dz^3.w^3_{11}+dz^3.w^3_{12}$

Ans: A & C. *In $\dfrac{\delta\\L}{\delta\\z^3}.\dfrac{\delta\\z^3}{dh^2_2}$, $\dfrac{\delta\\L}{\delta\\z^3}=dz^3=(r−y)$ and  $\dfrac{dz^3}{dh^2_1}=w^3_{11}$*

#### Calculating dW

Qn: The expression for $\dfrac{\delta\\L}{\delta\\w^3_{11}}$ is (more than one options may be correct): Hint: Use $z^3$ as the intermediate variable.

- $dz^3h^2_1$

- $dz^2h^2_1$

- $dz^3h^2_2$

- $(r−y)h^2_1$

Ans: A and D. *Compute $\dfrac{\delta\\L}{\delta\\w^3_{11}}$ as shown below: $\dfrac{\delta\\L}{\delta\\w^3_{11}}=\dfrac{\delta\\L}{\delta\\z^3}.\dfrac{\delta\\z^3}{\delta\\w^3_{11}}=dz^3h^2_1=(r-y)h^2_1$*

In the next session, you will learn about **TensorFlow** which will make the process of building and training the deep learning models much simpler.