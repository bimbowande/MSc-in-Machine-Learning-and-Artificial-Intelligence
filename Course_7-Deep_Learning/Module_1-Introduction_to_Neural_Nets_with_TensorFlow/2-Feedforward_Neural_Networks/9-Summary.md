# Summary

Let’s summarise your learnings from this session in the next video.

**VIDEO**

In this session, you learnt the following:

1.  You began this session by revisiting the notations of neural networks. Next, you learnt about the dimensions of weights and biases. These dimensions are given below:
    1.  The dimensions of weight matrices can be given by $\begin{bmatrix}n^{[l]},~n^{[l−1]}\end{bmatrix}$. 
    2.  The bias vector dimensions can be given by $\begin{bmatrix}n^{[l]},~1\end{bmatrix}$. But in the practical implementation, you take only one value of bias for all the neurons in a particular layer. Hence, the dimension becomes $\begin{bmatrix}1,~1\end{bmatrix}$.  
         
2.  Next, you also solved an example and computed the feedforward/predicted output of the network using the following equations:
    1.  Cumulative Input, $\large{z^{[l]}=w^{[l]}*h{[l−1]}+b^{[l]}}$
    2.  The output of hidden layer(sigmoid), $\large{h^{[l]}=\dfrac{1}{(1+e^{−z^{[l]}})}}$  
         
3.  Finally, you understood the pseudocode for the feedforward algorithm by considering a neural network with ‘n’ inputs, ‘k’ outputs, ‘L’ hidden layers and the sigmoid activation function for all the hidden layers except the output layer. The output layer activation function will be the softmax function. The pseudocode is given below:
	1. $h^0=x_i$
	2. for $l$ in $\begin{bmatrix}1,&2,&\dots&\dots,&L\end{bmatrix}:$
	    1. $h^l=\sigma(W^l*h^{l−1}+b^l)$
	3. $p_i=e^{W^o*h^L}$
	4. $p_i=normalize(p_i)$
         
4.  Lastly, you learnt how to implement this algorithm using a vectorised approach and wrote pseudocode for the same. The pseudocode is given below:
	1. $H^0=B$
	2. for $l$ in $\begin{bmatrix}1,&2,&\dots&\dots,&L\end{bmatrix}:$
	    1. $H^l=\sigma(W^l*H^{l−1}+b^l)$
	3. $P=normalize(exp(W^o*H^L+b^o))$
         
5.  You also covered the feedforward implementation in NumPy using the MNIST data set where you performed the following steps:
    1.  Data extraction, exploration and preparation
    2.  Writing activation functions and initializing parameters
    3.  Single-layer forward and ‘L’ layers forward methods

In the next segment, you will attempt the graded questions to test your learning. All the best!