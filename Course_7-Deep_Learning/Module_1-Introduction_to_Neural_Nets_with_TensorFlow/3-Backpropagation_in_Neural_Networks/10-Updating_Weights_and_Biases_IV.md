# Updating Weights and Biases - IV

So far you have computed the gradients for layer 3 and  the gradients dh[2] and dz[2] for the second layer. Let us now compute dW[2] in the upcoming video.

**VIDEO**

Let’s quickly go through the steps covered in the video.
$$\large{dW^{[2]}=\begin{bmatrix}\dfrac{\delta\\L}{\delta\\W^{[2]}}\end{bmatrix}=\dfrac{\delta\\L}{\delta\\z^{[2]}}.\dfrac{\delta\\z^{[2]}}{\\delta\\W^{[2]}}=dz^{[2}].\dfrac{\delta\\z^{[2]}}{\\delta\\W^{[2]}}}$$

Let’s first take a look at the individual components, which are as follows:
$$\large{W^{[2]}=\begin{bmatrix}w^{[2]}_{11}&w^{[2]}_{21}&w^{[2]}_{31}\\w^{[2]}_{12}&w^{[2]}_{22}&w^{[2]}_{32}\\w^{[2]}_{13}&w^{[2]}_{23}&w^{[2]}_{33}\end{bmatrix},~z^{[2]}\begin{bmatrix}z^{[2]}_1\\z^{[2]}_2\\z^{[2]}_3\end{bmatrix}}$$

Where,

- $z^{[2]}=W^{[2]}.h^{[1]}+b^{[2]}$
    - $z^{[2]}_1=w^{[2]}_{11}.h^{[1]}_1+w^{[2]}_{21}.h^{[1]}_2+w^{[2]}_{31}.h^{[1]}_3+b^{[2]}_1$
    - $z^{[2]}_1=w^{[2]}_{12}.h^{[1]}_1+w^{[2]}_{22}.h^{[1]}_2+w^{[2]}_{32}.h^{[1]}_3+b^{[2]}_2$
    - $z^{[2]}_1=w^{[2]}_{13}.h^{[1]}_1+w^{[2]}_{23}.h^{[1]}_2+w^{[2]}_{33}.h^{[1]}_3+b^{[2]}_3$

Now in order to compute $\dfrac{\delta\\L}{\delta\\W^{[2]}}$, you will have to find the partial derivative of each of the three $z^{[2]}$ components with respect to all the nine $W^{[2]}$ components and it can be written in matrix form as follows:
$$\large{dW^{[2]}=\begin{bmatrix}\dfrac{\delta\\L}{\delta\\w^{[2]}_{11}}&\dfrac{\delta\\L}{\delta\\w^{[2]}_{21}}&\dfrac{\delta\\L}{\delta\\w^{[2]}_{31}}\\\dfrac{\delta\\L}{\delta\\w^{[2]}_{12}}&\dfrac{\delta\\L}{\delta\\w^{[2]}_{22}}&\dfrac{\delta\\L}{\delta\\w^{[2]}_{32}}\\\dfrac{\delta\\L}{\delta\\w^{[2]}_{13}}&\dfrac{\delta\\L}{\delta\\w^{[2]}_{23}}&\dfrac{\delta\\L}{\delta\\w^{[2]}_{33}}\end{bmatrix}=\begin{bmatrix}dz^{2}_1.\dfrac{\delta\\L}{\delta\\w^{[2]}_{11}}&dz^{2}_1.\dfrac{\delta\\L}{\delta\\w^{[2]}_{21}}&dz^{2}_1.\dfrac{\delta\\L}{\delta\\w^{[2]}_{31}}\\dz^{2}_2.\dfrac{\delta\\L}{\delta\\w^{[2]}_{12}}&dz^{2}_2.\dfrac{\delta\\L}{\delta\\w^{[2]}_{22}}&dz^{2}_2.\dfrac{\delta\\L}{\delta\\w^{[2]}_{32}}\\dz^{2}_3.\dfrac{\delta\\L}{\delta\\w^{[2]}_{13}}&dz^{2}_3.\dfrac{\delta\\L}{\delta\\w^{[2]}_{23}}&dz^{2}_3.\dfrac{\delta\\L}{\delta\\w^{[2]}_{33}}\end{bmatrix}}$$

The next step is to compute each of these gradients and substitute it to the matrix you saw above. Let us see how to compute these partial derivatives:

**VIDEO**

As you saw in the video above, let us compute the value of $\dfrac{\delta\\z^{[2]}_1}{\delta\\w^{[2]}_{11}}$ below:
$$\large{\dfrac{\delta\\z^{[2]}_1}{\delta\\w^{[2]}_{11}}==\dfrac{\left(w^{[2]}_{11}.h^{[1]}_1+w^{[2]}_{21}.h^{[1]}_2+w^{[2]}_{31}.h^{[1]}_3+b^{[2]}_1\right)}{\delta\\w^{[2]}_{11}}=h^{[1]}_1}$$

Similarly, you can compute values for each element and substitute them in the matrix. On substituting the values, you will get the following:
$$\large{dW^{[2]}=\begin{bmatrix}dz^{[2]}_1.h^{[1]}_1&dz^{[2]}_1.h^{[1]}_2&dz^{[2]}_1.h^{[1]}_3\\dz^{[2]}_2.h^{[1]}_1&dz^{[2]}_2.h^{[1]}_2&dz^{[2]}_2.h^{[1]}_3\\dz^{[2]}_3.h^{[1]}_1&dz^{[2]}_3.h^{[1]}_2&dz^{[2]}_3.h^{[1]}_3\end{bmatrix}}$$

This can be written as follows: $dW^{[2]}=dz^{[2]}*\left(h^{[1]}\right)^T$

The bias $db^{[2]}$, as computed earlier, will be equal to $dz^{[2]}$.

#### Intermediary Variables

You have already computed the gradients with respect to $W^{[2]}$, i.e., $\dfrac{\delta\\L}{\delta\\W^{[2]}}$.

Now, to update the weights of the previous layer, $W^1$, you need to compute $dW^{[1]}=\dfrac{\delta\\L}{\delta\\W^{[1]}}$ For this, you will follow the same strategy: compute the gradient with respect to intermediary variables and use the chain rule of differentiation. Which of the following intermediary variables do you think will be involved in reaching $\dfrac{\delta\\L}{\delta\\W^{[1]}}$?

Select all the correct options (Note: $dx=\dfrac{\delta\\L}{\delta\\x}$) (More than one option may be correct.)

- $dh^2$

- $dh^1$

- $dz^2$

- $dz^1$

Ans: B & D. *$W^{[2]}$ is directly related to $h^{[1]}$, $h^{[1]}$ is directly related to $z^{[1]}$, and $z^{[1]}$ is directly related to $W^{[1]}$. Therefore, you will require dh1 to compute $\dfrac{\delta\\L}{\delta\\W^{[1]}}$.*

Similarly, for layer 1, you can write the equations as follows:

1. $dh^{[1]}=dz^{[2]}.\left(W^{[2]}\right)^T$
2. $dz^{[1]}=dh^{[1]}⊗\sigma'(z^{[1]})$
3. $dW^{[1]}=dz^{[1]}.\left(x\right)^T$

Having derived $dW^{[3]}$, $dW^{[2]}$ and $dW^{[1]}$, all we need to do is update the weights using the formula:
$$W^i=W^i-\alpha.\dfrac{\delta\\L}{\delta\\W^i}$$
where $i$ is the layer number  = 1, 2, 3

You have now completed the derivation of gradients for all the layers in the given neural network which involved performing complex matrix operations. But do we really need to do all this when modern libraries such as Tensorflow etc. provide convenient APIs? The answer is that it is important to conceptually understand how the backpropagation algorithm works, although in practice you will be using libraries such as Keras, Tensorflow etc. to train neural networks. 

Let's summarize the steps done so far in the next segment.