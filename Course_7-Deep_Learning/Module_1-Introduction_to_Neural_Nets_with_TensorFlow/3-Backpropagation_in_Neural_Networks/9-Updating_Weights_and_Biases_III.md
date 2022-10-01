# Updating Weights and Biases - III

So far, you have calculated three gradients, $dz^{[3]}$, $dw^{[3]}$ and $dh^{[2]}$. Now, the next step is to calculate $dz^{[2]}$. Let’s watch the next video to learn how to derive it.

**VIDEO**

Let’s quickly go through the steps covered in the video. You can write $dz^{[2]}$, using chain rule, as follows:
$$\large{dz^{[2]}=\dfrac{\delta\\L}{\delta\\z^{[2]}}=\dfrac{\delta\\L}{\delta\\h^{[2]}}.\dfrac{\delta\\h^{[2]}}{\delta\\z^{[2]}}}$$

You have already derived $\dfrac{\delta\\L}{\delta\\h^{[2]}}$, so you simply write it as $dh^{[2]}$. Now, let’s derive $\dfrac{\delta\\h^{[2]}}{\delta\\z^{[2]}}$. and for that lets look at the $h^{[2]}$ vector given below:
$$\large{h^{[2]}=\begin{bmatrix}h^{[2]}_{1}\\w^{[2]}_{2}\\w^{[2]}_{3}\end{bmatrix}=\begin{bmatrix}\dfrac{1}{1+e^{-z^2_1}}\\\dfrac{1}{1+e^{-z^2_2}}\\\dfrac{1}{1+e^{-z^2_3}}\end{bmatrix}=\begin{bmatrix}\sigma\left(z^{[2]}_1\right)\\\sigma\left(z^{[2]}_2\right)\\\sigma\left(z^{[2]}_3\right)\end{bmatrix}}$$

The $z^{[2]}$ vector looks like follows:
$$\large{z^{[2]}=\begin{bmatrix}z^{2}_1\\z^{2}_2\\z^{2}_3\end{bmatrix}}$$

Both $h^{[2]}$ and $z^{[2]}$ have $3x1$ dimension and the loss function can be written as follows:
$$\large{\dfrac{\delta\\L}{\delta\\z^{[2]}}=\begin{bmatrix}\dfrac{\delta\\L}{\delta\\z^{[2]}_1}\\\dfrac{\delta\\L}{\delta\\z^{[2]}_2}\\\dfrac{\delta\\L}{\delta\\z^{[2]}_3}\end{bmatrix}}$$
Let us learn how to compute each of the single gradient elements in the upcoming video.

**VIDEO**

Let’s compute $\dfrac{\delta\\L}{\delta\\z^{[2]}}$ by computing $\dfrac{\delta\\L}{\delta\\z^{[2]}_1}$, $\dfrac{\delta\\L}{\delta\\z^{[2]}_2}$ and $\dfrac{\delta\\L}{\delta\\z^{[2]}_3}$ as follows:
$$\large{\dfrac{\delta\\L}{\delta\\z^{[2]}}=dh^{[2]}_1.\dfrac{\delta\\h^{[2]}_1}{\delta\\z^{[2]}_1}+dh^{[2]}_2.\dfrac{\delta\\h^{[2]}_2}{\delta\\z^{[2]}_2}+dh^{[2]}_3.\dfrac{\delta\\h^{[2]}_3}{\delta\\z^{[2]}_3}}$$
$$\large{\dfrac{\delta\\L}{\delta\\z^{[2]}}=dh^{[2]}_1.\sigma'\left(z^{[2]}_1\right)+0+0}$$
$$\large{\therefore~\dfrac{\delta\\L}{\delta\\z^{[2]}}=dh^{[2]}_1.\sigma'\left(z^{[2]}_1\right)}$$

$$Similarly,~\large{\dfrac{\delta\\L}{\delta\\z^{[2]}_2}=dh^{[2]}_2.\sigma'\left(z^{[2]}_2\right)~\text{and}~\dfrac{\delta\\L}{\delta\\z^{[2]}_3}=dh^{[2]}_3.\sigma'\left(z^{[2]}_3\right)}$$

Therefore, we can write it as follows:
$$\large{dz^{[2]}=dh^{[2]}⊗\sigma'\left(z^{[2]}\right)}$$

where,  
$\sigma'\left(z^{[2]}\right)$ represents the derivative of $\sigma\left(z^{[2]}\right)$, which is $\sigma'\left(z^{[2]}\right)=\sigma\left(z^{[2]}\right)\left(1−\sigma\left(z^{[2]}\right)\right)$,and ⊗ represents the element-wise multiplication of the vectors.

## Comprehension: Gradients with the Sigmoid Activation Function

For a particular layer, you have $z^{[2]}=\begin{bmatrix}2\\1\\3\\-1\end{bmatrix}$. The activation function is the sigmoid function. Now, try to answer the following questions.

#### Output of the Layer

Given the value of $z^{[2]}$, what is $h^{[2]}$ (upto 3 decimal places)?

- $\begin{bmatrix}0.781\\0.531\\0.753\\0.469\end{bmatrix}$

- $\begin{bmatrix}0.881\\0.731\\0.953\\0.269\end{bmatrix}$

Ans: B. *On applying the sigmoid activation to the z vector, you will obtain the following result.*
$$h^{[2]}=\sigma\left(z^{[2]}\right)$$$$h^{[2]}=\begin{bmatrix}h^{[2]}_{1}\\w^{[2]}_{2}\\w^{[2]}_{3}\\w^{[2]}_{4}\end{bmatrix}=\begin{bmatrix}\dfrac{1}{1+e^{-z^2_1}}\\\dfrac{1}{1+e^{-z^2_2}}\\\dfrac{1}{1+e^{-z^2_3}}\\\dfrac{1}{1+e^{-z^2_4}}\end{bmatrix}=\begin{bmatrix}\sigma\left(z^{[2]}_1\right)\\\sigma\left(z^{[2]}_2\right)\\\sigma\left(z^{[2]}_3\right)\\\sigma\left(z^{[2]}_4\right)\end{bmatrix}$$$$\large{h^{[2]}=\begin{bmatrix}h^{[2]}_{1}\\w^{[2]}_{2}\\w^{[2]}_{3}\\w^{[2]}_{4}\end{bmatrix}=\begin{bmatrix}\dfrac{1}{1+e^{-2}}\\\dfrac{1}{1+e^{1}}\\\dfrac{1}{1+e^{-3}}\\\dfrac{1}{1+e^{-(-1)}}\end{bmatrix}=\begin{bmatrix}0.880797\\0.731058\\0.952574\\0.268941\end{bmatrix}\approx\begin{bmatrix}0.881\\0.731\\0.953\\0.269\end{bmatrix}}$$
#### Differentiation of Sigmoid Function

Qn: As you already know, $\sigma'\left(z^{[2]}\right)=\sigma\left(z^{[2]}\right)\left(1−\sigma\left(z^{[2]}\right)\right)$. What will be the value of $\sigma'\left(z^{[2]}\right)$  (upto 3 decimal places)?

- $\begin{bmatrix}0.105\\0.197\\0.045\\0.197\end{bmatrix}$

- $\begin{bmatrix}0.145\\0.127\\0.035\\0.127\end{bmatrix}$

Ans: A. *Substitute the values obtained in the previous question to the formula provided as follows: $\sigma'\left(z^{[2]}\right)=\sigma\left(z^{[2]}\right)\left(1−\sigma\left(z^{[2]}\right)\right)$*
$$\sigma'\left(z^{[2]}\right)=\begin{bmatrix}0.881\\0.731\\0.953\\0.269\end{bmatrix}\left(1-\begin{bmatrix}0.881\\0.731\\0.953\\0.269\end{bmatrix}\right)=\begin{bmatrix}0.881\\0.731\\0.953\\0.269\end{bmatrix}.\begin{bmatrix}0.119\\0.269\\0.047\\0.731\end{bmatrix}=\begin{bmatrix}0.105\\0.197\\0.045\\0.197\end{bmatrix}$$

#### Derivative of Loss Based on the Cumulative Input

Qn: You know that $dz^{[2]}=dh^{[2]}⊕\sigma'\left(z^{[2]}\right)$. Also, you have calculated $\sigma'\left(z^{[2]}\right)=\begin{bmatrix}0.105\\0.197\\0.045\\0.197\end{bmatrix}$. Considering $dh^{[2]}=\begin{bmatrix}1\\-1\\2\\-1\end{bmatrix}$, what will be the value of $dz^{[2]}$?

- $\begin{bmatrix}0.105\\−0.197\\0.090\\−0.197\end{bmatrix}$

- $\begin{bmatrix}0.105\\0.197\\0.090\\0.197\end{bmatrix}$

Ans: A. *By performing the element-wise multiplication of the vectors $\sigma'(x)$ and $dh^{[2]}$, you get:* $$dz^{[2]}=dh^{[2]}⊗\sigma'\left(z^{[2]}\right)=\begin{bmatrix}1\\-1\\2\\-1\end{bmatrix}⊗\begin{bmatrix}0.105\\0.197\\0.045\\0.197\end{bmatrix}=\begin{bmatrix}0.105\\−0.197\\0.090\\−0.197\end{bmatrix}$$
Let us move to the next segment and learn how to compute $dW^{[2]}$ using $dz^{[2]}$.
