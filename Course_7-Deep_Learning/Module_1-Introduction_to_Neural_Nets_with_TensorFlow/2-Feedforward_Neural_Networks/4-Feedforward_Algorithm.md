# Feedforward Algorithm

Now that you have learnt how information flows in the network, let’s write the pseudocode for a feedforward pass through the network for a single data point xi. This will help you implement your neural network in NumPy. 

Now, let’s consider a large neural network with ‘n’ inputs, ‘k’ outputs, ‘L’ hidden layers and the sigmoid activation function for all the hidden layers except the output layer. The output layer activation function will be the **softmax function**.

Previously, you have used the sigmoid activation function for your neural network, as it was a binary classification problem. Now, you will consider a multiclass classification problem, and the softmax function is the best choice for such a problem because the output is in terms of probabilities of occurrence of each class; this allows you to compare the results of all the classes with each other.

In the next video, we will write pseudocode which is applicable to any neural network.

**VIDEO**

#### Feedforward Algorithm

What is the value of in terms $h^{[l]}$ of $z^{[l]}$?

- $h^{[l]}=\dfrac{1}{1-e^{-z{[l]}}}$

- $h^{[l]}=\dfrac{1}{1+e^{-z{[l]}}}$ 

- $h^{[l]}=1-e^{-z{[l]}}$

- $h^{[l]}=1+e^{-z{[l]}}$

Ans: B. *$h^{[l]}$is the sigmoid activation applied to $z^{[l]}$ which is given by $\dfrac{1}{1+e^{-z{[l]}}}$.*

In the above video, you learnt the pseudocode of the feedforward algorithm. Let us write it once again:

1. $h^0=x_i$
2. for $l$ in $\begin{bmatrix}1,&2,&\dots&\dots,&L\end{bmatrix}:$
    1. $h^l=\sigma(W^l*h^{l−1}+b^l)$
3. $p = f(h^L)$

In the upcoming segments, you will build a neural network using the MNIST data set. This data set consists of grayscale images of handwritten digits (0–9), and your model needs to correctly classify the digit written in the image. Hence, your model should correctly predict the class or the digit. You can see that there are 10 digits and hence there’ll be 10 classes. So, the softmax output is used. It is in the form of probabilities. In the next video, you will learn how to handle these probabilities.

**VIDEO**

As you saw in the video above, learnt about the feedforward algorithm with a softmax output layer. You already know that softmax output $p=f(h^L)$.
$$\large{f(h^L)=f'(z_o)=softmax(z_o)}$$
$$\large{\therefore~f(h^L) = softmax (W^o*h^L+b^o)}$$
where, 

$z_o$ is the input

$W^o$ is the weight matrix

$h^L$ is the output of the last hidden layer 

$b^o$ is the bias for the final output layer

For simplicity, let's drop the bias, $b^o$. 

For a particular datapoint $\large{i,~pi=softmax(W^o*h^L_i)=\begin{bmatrix}p_{i1}\\p_{i2}\\\vdots\\p_{ik}\end{bmatrix}}$

  
The weight and output of the final layer look like shown below:
$$\large{W^o=\begin{bmatrix}-&w_1&-\\-&w_2&-\\-&w_3&-\end{bmatrix},~h^L=\begin{bmatrix}h^{L}_{i1}\\h^{L}_{i2}\\\vdots\\h^{L}_{ij}\end{bmatrix}}$$
Where w1,w2 ... wk are row vectors of the output weight matrix Wo and k is the number of neurons in the output layer.

Note that the length of w1= length of hLi = n, where n is the number of neurons in the last hidden layer. 

Therefore,
$$\large{p_i=softmax\left(\begin{bmatrix}-&w_1&-\\-&w_2&-\\-&w_3&-\end{bmatrix}*\begin{bmatrix}h^{L}_{i1}\\h^{L}_{i2}\\\vdots\\h^{L}_{ij}\end{bmatrix}\right)=\begin{bmatrix}p_{i1}\\p_{i2}\\\vdots\\p_{ik}\end{bmatrix}=softmax\left(\begin{bmatrix}w_1h^{L}_{i1}\\w_2h^{L}_{i2}\\\vdots\\w_kh^{L}_{ij}\end{bmatrix}\right)}$$
The last step required to calculate the output of the softmax function having all these weights and outputs is **normalization.** Here, you need to compute the probability values, which can be calculated using different methods but in the case of the softmax function, you will be using the exponential function to normalize the output and compute probabilities.
$$\large{p_i=softmax\left(\begin{bmatrix}w_1h^{L}_{i1}\\w_2h^{L}_{i2}\\\vdots\\w_kh^{L}_{ij}\end{bmatrix}\right)=\begin{bmatrix}\dfrac{e^{W_1h^L_{i1}}}{e^{W_1h^L_{i1}}+e^{W_2h^L_{i2}}+\dots+e^{W_kh^L_{ij}}}\\\dfrac{e^{W_2h^L_{i2}}}{e^{W_1h^L_{i1}}+e^{W_2h^L_{i2}}+\dots+e^{W_kh^L_{ij}}}\\\vdots\\\dfrac{e^{W_kh^L_{ij}}}{e^{W_1h^L_{i1}}+e^{W_2h^L_{i2}}+\dots+e^{W_kh^L_{ij}}}\end{bmatrix}=\begin{bmatrix}p_{i1}\\p_{i2}\\\vdots\\p_{ik}\end{bmatrix}}$$

You can rewrite this as:

$$\large{p_{ij}=\dfrac{e^{w_j*h^L}}{\sum^k_{t=1}e^{w_t*h^L}}\text{ for  }j=\begin{bmatrix}1,&2,&\dots,&k\end{bmatrix}\text{ \& }k=\text{ number of classes}}$$

You saw how the output of the last layer is computed. Now you can write, the complete feedforward algorithm as shown below:

1. $h^0=x_i$
2. for $l$ in $\begin{bmatrix}1,&2,&\dots&\dots,&L\end{bmatrix}:$
    1. $h^l=\sigma(W^l*h^{l−1}+b^l)$
3. $p_i=e^{W^o*h^L}$
4. $p_i=normalize(p_i)$

Note that Wo (the weights of the output layer) can also be written as $W^{L+1}$.

Let's now try to understand how decision making happens in the softmax layer using the same example network we had used in the previous segment:

![Softmax](https://i.ibb.co/6Y8QpSf/Softmax.png)

We have the last weight matrix $W^3$ as $W^o$. The output layer classifies the input into one of the three labels: 1, 2 or 3. The first neuron outputs the probability for label 1, the second neuron outputs the probability for label 2 and hence the third neuron outputs the probability for label 3.

Now answer the following questions:

#### Dimension $W^o$

Qn: What is the dimension of $W^o$?

- (2,3)

- (3,2)

Ans: B. *Dimension  = (number of neurons in layer l, number of neurons in layer l-1) for a weight matrix $W^l$*

#### Weight matrix calculation

Qn: Consider $W^o=\begin{bmatrix}3&4\\1&9\\6&2\end{bmatrix}$ and  $h^2=\begin{bmatrix}1\\2\end{bmatrix}$ and bias is 0. What will be $W^o*h^2$?

- $\begin{bmatrix}11\\19\\10\end{bmatrix}$

- $\begin{bmatrix}19\\11\\10\end{bmatrix}$

Ans: A. *It is a simple matrix multiplication.*

#### Softmax Claculation

Qn: Consider $W^o=\begin{bmatrix}3&4\\1&9\\6&2\end{bmatrix}$ and  $h^2=\begin{bmatrix}1\\2\end{bmatrix}$ with the bias = 0. What will be the softmax output vector $p$, i.e. the output of the 3rd layer? In other words, what is $normalized(p)$ (up to 5 decimal places)?

- $\begin{bmatrix}0.00034\\0.99954\\0.00012\end{bmatrix}$

- $\begin{bmatrix}0.00012\\0.99954\\0.00034\end{bmatrix}$

Ans: A. *The probability order should be 3<1<2 for the class labels.*

#### Predicted label

Qn: What is the predicted label?

- 1

- 2

- 3

Ans: *As the highest probability is for the neuron representing label 2, it is the predicted label.*

So far, you have been implementing the feedforward algorithm for one single data point at a time (i.e., a single image in the case of the MNIST data set). However, the training data may have millions of data points. For example, the MNIST data set itself has approximately 60,000 images in the training set.

Now, you will learn how to perform feedforward for an entire batch of data points in one attempt for which you will use vectorized computation techniques that will be covered in the next segment.

## Additional Reading:

-   You can go through [this book](http://neuralnetworksanddeeplearning.com/chap1.html) to understand more about recognizing handwritten digits