# Updating Weights and Biases - II

So far you have computed $dz^{[3]}$ in the previous segment. Let us start with computing the next gradient component i.e., $\dfrac{\delta\\L}{\delta\\W^{[3]}}$. Take a look at the upcoming video.

**VIDEO**

As you know, $\dfrac{\delta\\L}{\delta\\W}=dz^{[3]}\dfrac{\delta\\z^{[3]}}{\delta\\W^{[3]}}$ and you have computed $dz^{[3]}$. Now, the next step is to compute $\dfrac{\delta\\z^{[3]}}{\delta\\W^{[3]}}$. Let’s first take a look at the individual components.
$$\large{z^{[3]}=W^{[3]}*h^{[2]}+b^{[3]}}$$

where,
$$\large{W^{3}=\begin{bmatrix}w^{[3]}_{11}&w^{[3]}_{21}&w^{[3]}_{31}\end{bmatrix}~\text{and}~h^{[2]}=\begin{bmatrix}h^{[2]}_{1}\\w^{[2]}_{2}\\w^{[2]}_{3}\end{bmatrix}}$$ 
$$\large{\therefore~z^{[3]}=w^{[3]}_{11}*h^{[2]}_{1}+w^{[3]}_{21}*h^{[2]}_{2}+w^{[3]}_{31}*h^{[2]}_{3}+b^{[3]}}$$

You can break $\dfrac{\delta\\L}{\delta\\W}$ into a vector of individual components as follows:
$$\large{\dfrac{\delta\\L}{\delta\\W^{[3]}}=\begin{bmatrix}\dfrac{\delta\\L}{\delta\\w^{[3]}_{11}}&\dfrac{\delta\\L}{\delta\\w^{[3]}_{21}}&\dfrac{\delta\\L}{\delta\\w^{[3]}_{31}}\end{bmatrix}}$$
Now, you can compute each of these elements individually and substitute them into the row vector shown above.  Let us understand it in the next video.

**VIDEO**

On computing the partial derivative of loss with respect to weight elements of layer 3, you will obtain the following: 

1. $\dfrac{\delta\\L}{\delta\\w^{[3]}_{11}}=dz^{[3]}.\dfrac{\delta\left(w^{[3]}_{11}.h^{[2]}_{1}+w^{[3]}_{21}.h^{[2]}_{2}+w^{[3]}_{31}.h^{[2]}_{3}+b^{[3]}\right)}{\delta\\w^{[3]}_{11}}=dz^{[3]}.h^{[2]}_{1}$
     
2. $\dfrac{\delta\\L}{\delta\\w^{[3]}_{21}}=dz^{[3]}.\dfrac{\delta\left(w^{[3]}_{11}.h^{[2]}_{1}+w^{[3]}_{21}.h^{[2]}_{2}+w^{[3]}_{31}.h^{[2]}_{3}+b^{[3]}\right)}{\delta\\w^{[3]}_{21}}=dz^{[3]}.h^{[2]}_{2}$
     
3. $\dfrac{\delta\\L}{\delta\\w^{[3]}_{31}}=dz^{[3]}.\dfrac{\delta\left(w^{[3]}_{11}.h^{[2]}_{1}+w^{[3]}_{21}.h^{[2]}_{2}+w^{[3]}_{31}.h^{[2]}_{3}+b^{[3]}\right)}{\delta\\w^{[3]}_{31}}=dz^{[3]}.h^{[2]}_{3}$

This can be written as follows: $dW^{[3]}=\dfrac{\delta\\L}{\delta\\W^{[3]}}=\begin{bmatrix}dx^{[3]}\end{bmatrix}.\begin{bmatrix}h^{[2]}_1&h^{[2]}_2&h^{[2]}_3\end{bmatrix}$

On solving this, you will get $dW^{[3]}=\dfrac{\delta\\L}{\delta\\W^{[3]}}=\begin{bmatrix}dx^{[3]}\end{bmatrix}.\left(h^{[2]}\right)^T$

Now, using $\dfrac{\delta\\L}{\delta\\W^{[3]}}$, you can update the $W^{[3]}$ weight matrix using the gradient descent equation given below:
$$\large{W^{[3]}_{new}=W^{[3]}_{old}−\alpha.\dfrac{\delta\\L}{\delta\\W^{[3]}}}$$

Similar to the process you followed in the case of $W^{[3]}$, you can also compute the bias $b^{[3]}$ as follows:
$$\large{\therefore~z^{[3]}=w^{[3]}_{11}*h^{[2]}_{1}+w^{[3]}_{21}*h^{[2]}_{2}+w^{[3]}_{31}*h^{[2]}_{3}+b^{[3]}}$$
$$\large{\dfrac{\delta\\L}{\delta\\b}=\dfrac{\delta\\L}{\delta\\p}.\dfrac{\delta\\p}{\delta\\z^{[3]}}.\dfrac{\delta\\z^{[3]}}{\delta\\b^{[3]}}}$$

As you have already computed, $\dfrac{\delta\\L}{\delta\\p}.\dfrac{\delta\\p}{\delta\\z^{[3]}}$ can be written as $dz^{[3]}$. Substituting it into the above equation, you will get the following:
 $$\large{\dfrac{\delta\\L}{\delta\\b^{[3]}}=dz^{[3]}.\dfrac{\delta\\z^{[3]}}{\delta\\b^{[3]}}}$$
Now, 
$$\large{\dfrac{\delta\\L}{\delta\\b^{[3]}}=dz^{[3]}.\dfrac{\delta\\z^{[3]}}{\delta\\b^{[3]}}=dz^{[3]}.\dfrac{\delta\left(w^{[3]}_{11}.h^{[2]}_{1}+w^{[3]}_{21}.h^{[2]}_{2}+w^{[3]}_{31}.h^{[2]}_{3}+b^{[3]}\right)}{\delta\\b^{[3]}_{11}}=dz^{[3]}}$$

Therefore,  $db^{[3]}=dz^{[3]}$

Now that you have derived the gradient of weight and bias for the second hidden layer. Let’s now propagate backwards and compute $\dfrac{\delta\\L}{\delta\\w^{[2]}}$. Let’s watch the next video to learn how to solve this in a step-by-step manner.

**VIDEO**

The next step is to derive $\dfrac{\delta\\L}{\delta\\h^{[2]}}$, which can be done as follows:
$$\large{dh^{[2]}=\dfrac{\delta\\L}{\delta\\h^{[2]}}=\dfrac{\delta\\L}{\delta\\z^{[3]}}.\dfrac{\delta\\z^{[3]}}{\delta\\h^{[2]}}}$$

You have already derived $\dfrac{\delta\\L}{\delta\\z^{[3]}}$, so you simply write it as $dz^{[3]}$. Now let’s derive $\dfrac{\delta\\z^{[3]}}{\delta\\h^{[2]}}$. Keep in mind the dimensions of the vectors and break them down into individual components as follows: 
$$\large{h^{[2]}=\begin{bmatrix}h^{[2]}_{1}\\w^{[2]}_{2}\\w^{[2]}_{3}\end{bmatrix}~\text{and}~z^{[3]}=w^{[3]}_{11}.h^{[2]}_{1}+w^{[3]}_{21}.h^{[2]}_{2}+w^{[3]}_{31}.h^{[2]}_{3}+b^{[3]}}$$

You will compute the individual partial derivatives of $z^{[3]}$ with respect to $h^{[2]}_1$, $h^{[2]}_2$ and $h^{[2]}_3$. Once these values are computed substitute them and derive $\dfrac{\delta\\L}{\delta\\h^{[2]}}$ as follows:
$$\dfrac{\delta\\L}{\delta\\h^{[2]}}=\begin{bmatrix}dz^{[3]}.\dfrac{\delta\left(w^{[3]}_{11}.h^{[2]}_{1}+w^{[3]}_{21}.h^{[2]}_{2}+w^{[3]}_{31}.h^{[2]}_{3}+b^{[3]}\right)}{\delta\\h^{[2]}_{1}}\\dz^{[3]}.\dfrac{\delta\left(w^{[3]}_{11}*h^{[2]}_{1}+w^{[3]}_{21}.h^{[2]}_{2}+w^{[3]}_{31}.h^{[2]}_{3}+b^{[3]}\right)}{\delta\\h^{[2]}_{2}}\\dz^{[3]}.\dfrac{\delta\left(w^{[3]}_{11}*h^{[2]}_{1}+w^{[3]}_{21}.h^{[2]}_{2}+w^{[3]}_{31}.h^{[2]}_{3}+b^{[3]}\right)}{\delta\\h^{[2]}_{3}}\end{bmatrix}$$

On further simplification of the above vector you get, $\large{dh^{[2]}=\dfrac{\delta\\L}{\delta\\h^{[2]}}=dz^{[3]}.\left(w^{[3]}\right)^T}$

Try solving the following question:

#### Backpropagation Notations

Qn: Select all the correct statements about the intermediate variable $z$ from below. (Note: More than one option may be correct.)

- $z^l$ denotes the cumulative input coming into layer $l$.

- $z^l$ denotes the cumulative output from layer $l$.

- $h^l=\sigma(z^l)$

- $z^l=W^l*h^{l−1}+b^l$

- $z^l=W^l*h^l+b^l$

Ans: A, C & D. *$z^l$ denotes the cumulative input going into layer $l$. The output of layer $l$ is simply the activation function applied to $z^l$. $z^l$ is computed by multiplying the output of layer $l−1$ with the weights and by adding the bias.*

So far, you have calculated three gradients, $dz^{[3]}$, $dw^{[2]}$ and $dh^{[2]}$. Now, the next step is to calculate $dz^{[2]}$. Let us move to the next segment and learn how to do so.