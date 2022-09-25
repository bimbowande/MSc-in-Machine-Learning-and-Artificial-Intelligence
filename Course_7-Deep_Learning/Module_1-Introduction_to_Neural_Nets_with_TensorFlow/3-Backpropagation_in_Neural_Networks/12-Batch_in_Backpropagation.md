# Batch in Backpropagation

Until now, we have been working with a single data point for performing feedforward and backpropagation. However, in practice, performing feedforward and backpropagation for a large number of training data points will be extremely inefficient. 

  
In this segment, you will learn how to modify the feedforward and backpropagation algorithms such that you can work with a **batch of multiple data points** as shown below: 
$$\large{B=\begin{bmatrix}|&|&|&|&|\\x_i&x_{i+1}&.&.&x_{i+m-1}\\|&|&|&|&|\end{bmatrix}}$$

Let’s watch the next video to understand the pseudocode for training in batches.

**VIDEO**

To summarise, you learnt how the backpropagation algorithm can be written for a batch of multiple data points. Note that the loss L is computed over a batch. In a way, the batch acts as a proxy for the whole data set. Therefore, for a batch size of m, the average loss will be as follows:
$$\large{\dfrac{1}{m}\sum_{x\in\\B}L(N(x),~y)}$$
This is the average loss over the m data points of the batch. N(x) is the network output (the vector p). Let's denote a batch of input data points by the matrix B. The backpropagation algorithm for a batch is:

1. $H^0=x$
2. for $l$ in $\begin{bmatrix}1,&2,&\dots&\dots,&L\end{bmatrix}:$
    1.  $H^l=\sigma(W^l*H^{l−1}+b^l)$
3. $P=normalize(exp(W^o*H^L+b^o))$
4. $L=−\dfrac{1}{m}Y^T.log(P)$
5. $DZ^{L+1}=P−Y$
6. $DW^{L+1}=DZ^{L+1}.\left(H^L\right)^T$
7. for $l$ in $\begin{bmatrix}L,&L-1,&\dots&\dots,&1\end{bmatrix}:$
    1. $dH^l=\left(W^{l+1}\right)^T.dz^{l+1}$
    2. $DZ^l=dH^l⊗\sigma'(Z^l)$
    3. $DW^l=DZ^l⊗_T\left(H^{l−1}\right)^T$
    4. $Db^l=DZ^l$

**Note** that the loss is given by $L=−\dfrac{1}{m}Y^T.log(P)$ in the pseudocode above. Here, the '.' between $Y^T$ and $P$ represents the element-wise matrix multiplication and not the dot product. This change happens as you move from processing a single data point to a batch of data points. You will learn about it in detail while writing the code in NumPy.

Earlier $dz^l$ represented a vector while $DZ^l$ now represents the matrix consisting of the dzl vectors of all the data points in $B$ (each $dz^l$ being a column of $DZ^l$). Similarly, $dH^l$, $Y$, $P$ and $H^l$ are all matrices of the corresponding individual vectors stacked side by side.

There is something interesting to note here - $DW^l$ is a tensor while $Db^l$ is a matrix (think about why). This is something we don't want because, in the update step, when we write:
$$W^l_{new}=W^l{old}−\alpha.\dfrac{\delta\\L}{\delta\\W^l},~b^l_{new}=b^l_{old}-\alpha.\dfrac{\delta\\L}{\delta\\b^l}$$

The shapes of $\dfrac{\delta\\L}{\delta\\W^l}$(currently a tensor $DW^l$) and $W^l$ (a matrix) should be the same. Similarly, the shapes of $\dfrac{\delta\\L}{\delta\\b^l}$(currently a matrix $Db^l$) should be the same as that of $b^l$ (a vector). Let's see how the tensor $DW^l$ and the matrix $Db^l$ can be converted to a matrix and a vector respectively:

**VIDEO**

In the backpropagation of a single data point, you saw that $dz^l.\left(h^{l−1}\right)^T$ gave a matrix of dimensions of $dW^l$. Hence, when you take the matrix $dZ^l$ and $dH^{l-1}$ in place of $dz^l$ and $h^{l−1}$ respectively for batch backpropagation, you get multiple such dWl matrices stacked, creating the tensor $dW^l$.

We can see from the image below that the tensor product $DW^l=DZ^l⊗_T\left(H^{l−1}\right)^T$ is basically a **tensor**. This can be visualised in the following image:

![Tensor Visualization](https://i.ibb.co/KFR2DbP/Tensor-Visualization.jpg)

  
Each 'layer' along the 'batch size' dimension of this tensor contains the dWl matrix for each data point. Remember that the loss function we are minimizing is the average loss of data points in B, i.e. $\dfrac{1}{m}\sum_{x\in\\B}L(p,~y)$. Hence, we take the average of all the dWl matrices across the batch to get the final weight gradient matrix for the update step. In other words, we collapse the tensor along the batch dimension using the average. Now this is very easily facilitated if you do a simple dot product $DZ^l.(H^{l−1})^T$ and this is what we use in programming later in Numpy. You can easily figure this out by taking small $DZ^l$ and $H^{l−1}$ matrices and doing both tensor product as shown above and the simple dot product. 

Hence, you can write it as:

Average or individual matrices across batch dimension in $DZ^l⊗_T\left(H^{l−1}\right)^T=\dfrac{1}{m}DZ^l.(H^{l−1})^T$

#### Shape of Tensor

What will be the shape of the tensor $dW$ given that it $W=\begin{bmatrix}1&0&3&2\\5&7&0&9\\1&5&1&4\end{bmatrix}$.

- 3x4

- 4x3

Ans: A. *The shape of tensor $dW$ will be the same as the shape of $W$. Therefore, the answer will be 3x4.*

Qn: What will be the shape of the tensor $DW^l$ if $DZ^l$ is of the shape 4x5 and $H^{l−1}$ is of the shape 7x5.

- 4X5x7

- 5x4x7

Ans: A. *The tensor is given by the tensor product formula: $DW^l=DZ^l.\left(H^{l−1}\right)^T$. Use this formula to get an intuition about the dimensions. You get it as (number of neurons in current layer $l$, number of neurons in the previous layer $l-1$, batch size).*

Similarly, $Db^l$ is a matrix as shown below - each column corresponds to the vector $db^l$ for one data point in the batch:

![Batch Bias](https://i.ibb.co/Vtq4PVW/Batch-Bias.jpg)

This matrix consists of the gradient vectors $db^l$ of each data point in the batch stacked side by side. Since we minimize the average loss of the batch, we take the average of these 'bias gradient vectors' to finally create a single vector $\dfrac{\delta\\L}{\delta\\b}$.

This is where the backpropagation algorithm wraps up. By now, you must have gained the confidence to derive the backpropagation algorithm for any neural network.

You understood how you would utilize the whole dataset and update the parameters of the model: weights and biases. This is often referred to as **batch gradient descent** as you use the whole dataset as a batch to update the model parameters. In the next segment, you will learn about 2 other most common variations of the gradient descent algorithm.