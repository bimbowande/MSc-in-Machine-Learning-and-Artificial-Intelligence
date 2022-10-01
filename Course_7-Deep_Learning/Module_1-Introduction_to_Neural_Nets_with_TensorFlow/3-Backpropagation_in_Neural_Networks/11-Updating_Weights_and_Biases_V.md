# Updating Weights and Biases - V

Let’s quickly summarise this derivation in the upcoming video.

**VIDEO**

In the above video, you saw summarised the derivation. Let us take a quick look at it in the image given below:

![Feedforward and Backpropogation](https://i.ibb.co/TqXFDxV/Feedforward-and-Backpropogation.jpg)

As you can see, the gradients are calculated in a backward direction, starting from dz[3]. This is why the process is known as **backpropagation**; you propagate the gradients in a backward direction starting from the output layer. The above diagram helps in calculating the gradients using the chain rule. Hence, you will calculate the gradients in the following sequence:

1. $dz^3=p−y$
2. $dW^3 = dz^3.\left(h^2\right)^T$
3. $dh^2=\left(W^3\right)^T.dz^3$
4. $dz^2=dh^2⊗.\sigma'(z^2)$
5. $dW^2=dz^2.\left(h^1\right)^T$
6. $dh^1=\left(W^2\right)^T.dz^2$
7. $dz^1=dh^1⊗.\sigma'(z^1)$
8. $dW^1=dz^1.\left(x\right)^T$

You have written these equations for the specific network that you have considered. Let's answer some questions to check if you can find a pattern in the above-mentioned formulas.

#### Gradients

For a particular layer number 5, what is the expression for dW5?

 - $dz^5.\left(h^5\right)^T$

 - $dz^5.\left(h^4\right)^T$

 - $dz^4.\left(h^5\right)^T$

 - $dz^4.\left(h^5\right)^T$

Ans:B. *It is $dz^l.\left(h^{l−1}\right)^T$ for a layer '$l$'.*

Qn: For a particular layer number 7, what is the formula of dh7?

- $\left(W^6\right)^T.dz^6$

- $\left(W^7\right)^T.dz^7$

- $\left(W^8\right)^T.dz^8$

- $\left(W^7\right)^T.dz^6$

Ans: C. *It is $\left(W^{l+1}\right)T.dz^{l+1}$ for a layer '$l$'.*

Qn: For a particular layer number 4, what is the formula of dz4?

- $dh^3⊗.\sigma'(z^3)$

- $dh^4⊗.\sigma'(z^4)$

- $dh^5⊗.\sigma'(z^5)$

Ans: B. *It is $dh^l⊗.\sigma'(z^l)$ for a particular layer '$l$'.*

Now that you have reached the end of this derivation, let’s write the pseudocode for the equations derived above. Let’s watch the next video to learn how to do this.

**VIDEO**

**Note** that we have considered softmax as the activation function of the output layer while writing the pseudocode. Do not worry, it will not change the formulae that we have derived for backpropagation.

As you can see in the above video, the loss function is mentioned as $L=y^T.log(p)$. Let us understand this representation of loss function:

Let us consider an output layer with 3 neurons. The actual output vector for this layer will be represented as $y=\begin{bmatrix}y_1\\y_2\\y_3\end{bmatrix}$ and the predicted output can be given by $p=\begin{bmatrix}p_1\\p_2\\p_3\end{bmatrix}$.

The C.E Loss is $(y_1log(p_1)+y_2log(p_2)+y_3log(p_3))$.

The log of predicted value can be represented as follows: $log(p)=\begin{bmatrix}log(p_1)\\log(p_2)\\log(p_3)\end{bmatrix}$

Thus, the cross-entropy loss can be written concisely as: 
$$\large{-y^T.log(p)=-\begin{bmatrix}y_1&y_2&y_3\end{bmatrix}.\begin{bmatrix}log(p_1)\\log(p_2)\\log(p_3)\end{bmatrix}=-(y_1log(p_1)+y_2log(p_2)+y_3log(p_3))}$$
 
where $y^T$ is the transpose of $y$.

Hope you got a good understanding of the representation cross-entropy loss by now.

So far, you saw the pseudocode for feedforward and the loss function. Let's watch the next video to learn about the pseudocode for backpropagation in neural networks.

**VIDEO**

The pseudocode of the algorithm that you learnt in the previous video can be written as follows:

1. $h^0=x$
2. for $l$ in $\begin{bmatrix}1,&2,&\dots&\dots,&L\end{bmatrix}:$
    1.  $h^l=\sigma(W^l*h^{l−1}+b^l)$
3. $P=normalize(exp(W^o*H^L+b^o))$
4. $L=−y^T.log(p)$
5. $dz^o=p−y$
6. $dW^o=dz^o.\left(h^2\right)^T$
7. for $l$ in $\begin{bmatrix}L,&L-1,&\dots&\dots,&1\end{bmatrix}:$
    1. $dh^l=\left(W^{l+1}\right)^T.dz^{l+1}$
    2. $dz^l=dh^l⊗.\sigma'(z^l)$
    3. $dW^l=dz^l.\left(h^{l−1}\right)^T$

In the video above, you went through one full trip through the network for a single data point. The entire journey consists of the following three steps:

1.  Feedforward
2.  Define the loss function
3.  Backpropagation

This is the consolidated algorithm for a single data point. But don't you think something is missing here? You have not updated any of the weights yet! You will complete the update step in a while after processing the above-mentioned steps for a **batch**. This is because processing a single update for one data point will be extremely slow.

Let's go through how to deal with batches in the upcoming segment.