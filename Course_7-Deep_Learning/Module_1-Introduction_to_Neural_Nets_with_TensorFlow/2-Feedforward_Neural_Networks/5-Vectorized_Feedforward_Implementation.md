# Vectorized Feedforward Implementation

Training data includes multiple data points, and you need to perform feedforward computation for all of them. For a very large data set, doing one point at a time using a loop might be very time-consuming. Therefore, a vectorized approach to perform feedforward for multiple points at once is needed.

**VIDEO**

**Vectorized implementation** means performing the computation (here, feedforward) for multiple data points using matrices. This will be much quicker than working with one data point at a time. A way to achieve this would be to write a 'for loop' iterating through all the data points. 

Let’s reconsider the neural network with ‘n’ inputs, ‘k’ outputs, ‘L’ hidden layers and the sigmoid activation function for all the hidden layers except the output layer. The output layer activation function will be the softmax function. Let’s try writing the feedforward pseudocode for a set of m data points using a 'for loop'.

1. for $i$ in $\begin{bmatrix}1,&2,&\dots&\dots,&m\end{bmatrix}:$
    1. $h^0=x_i$
    2. for $l$ in $\begin{bmatrix}1,&2,&\dots&\dots,&L\end{bmatrix}:$
        1. $h^l=\sigma(W^l*h^{l−1}+b^l)$
    3.  $p_i = f(h^L)$

You will notice that you require two nested 'for loops'. This will become computationally quite expensive if you have a large data set (which is often the case with neural networks). As a data scientist, you would have guessed that there must be a more efficient way of doing it. 

In the next video, you will learn how to perform feedforward for an entire batch of data points in one go by means of vectorized computation techniques using matrices.

**VIDEO**

In the above video, you saw how to use matrices to implement the vectorised feedforward algorithm. Let us understand it in more depth by considering a batch B to show a vectorized implementation that consists of m data points stacked side by side, which is represented as follows.
$$\large{B=\begin{bmatrix}|&|&|&|&|\\x_i&x_{i+1}&.&.&x_{i+m-1}\\|&|&|&|&|\end{bmatrix}}$$
All data points $x_i,~x_{i+1}$ etc. are d-dimensional vectors, i.e. every input vector has d numerical features. Each data point is a **column vector** in the matrix B.

#### B Dimension

Qn: What is the dimension of each of the input vectors present in the batch B?

- (d, 1)

- (1,d)

Ans: A. *It is a vector with d numerical features arranged in rows. Hence, (d,1).*

Qn: We have represented data points in the batch B by the starting and ending indices $i$ and $i+m−1$ respectively. According to this indexing scheme, how many input data points are present in the training set?

- m-1

- m

Ans: B. *We have $(i+m-1)-(i)+1=m$ data points.*

Qn: For the batch given above, what will be the dimensions of B?

- (m, d)

- (d, m)

Ans: B. *We have d rows and m columns. Therefore, the dimensions of the batch are (d,m).*

Thus, the feedforward algorithm for a batch B is as follows:

1. $H^0=B$
2. for $l$ in $\begin{bmatrix}1,&2,&\dots&\dots,&L\end{bmatrix}:$
    1. $H^l=\sigma(W^l*H^{l−1}+b^l)$
3. $P=normalize(exp(W^o*H^L+b^o))$

Notice that this is very similar to the algorithm for a single data point with some notational changes. Specifically, we have used the uppercase notations and $P$ instead of $h^l$ and $p$ respectively to denote an entire batch of data points. In other words, $H^l$  and $P$  are matrices whose ith column represents the $h^l$ and p vectors respectively of the $i^{th}$ data point. The number of columns in these 'batch matrices' is equal to the number of data points in the batch $m$. 
$$\large{H^l=\begin{bmatrix}|&|&|&|&|\\h^l_i&h^l_{i+1}&.&.&h^l_{i+m-1}\\|&|&|&|&|\end{bmatrix}\text{ and }P=\begin{bmatrix}|&|&|&|&|\\p_i&p_{i+1}&.&.&p_{i+m-1}\\|&|&|&|&|\end{bmatrix}}$$

Now, try answering a few questions that will help you understand the concept better.

   
You are given a simple network, and you pass a batch B consisting of 50 data points through this network. Each data point is represented by five features as shown below:

![Vectorized Feedforward Qn](https://i.ibb.co/Wx2jc4w/Vectorized-Feedforward-Qn.jpg)

You pass a batch B consisting of 50 data points through this network. Each data point is represented by five features.

#### $P$ Dimension

Qn: What is the dimension of the network output matrix $P$?

- (5,50)

- (4,50)

- (7,50)

- (16,50)

Ans: B. *There are 4 neurons in the output layer. Hence, for every input data point, there will be an output vector of shape (4,1). Since there are 50 such data points, the shape of the matrix $P$ is (4,50).*

#### $H^1$ Dimension

Qn:What is the dimension of the output matrix out of the first hidden layer, that is H1?

- (7, 50)

- (5, 50)

- (12, 50)

- (4, 50)

Ans: A. *There are 7 neurons in the hidden layer 1. Hence, for every input data point, there will be an output vector of shape (7, 1). Since there are 50 such data points, the shape of the matrix $H^1$ is (7, 50).*

#### $B$ Dimension

Qn: What is the dimension of the input batch $B$?

- (7, 50)

- (5, 50)

- (4, 50)

- (16, 50)

Ans: B. *There are 50 input data points and there are 5 neurons for each input data point. Hence, dimension = (5, 50)*

#### Computation in Neural Networks

Qn: Why can neural network computations be parallelized?

- Computation for each layer can be done independently of the others.

- Products of matrices and vectors can be easily parallelized.

- Neurons in one layer are not connected to each other.

Ans: B. *Neural network computations essentially boil down to matrix-vector products. Hence, the products of matrices and vectors can be easily parallelized.*

Now that you have learnt about the vectorized approach to feedforward neural networks, in the next segment, let’s try using this knowledge and building our own feedforward neural network in NumPy.  
 
## Additional Links:

1.  You can learn more about the parallelization of products of matrices and vectors [here.](http://www.hpcc.unn.ru/mskurs/ENG/DOC/pp07.pdf)
2.  Read more on parallel methods for matrix multiplication [here.](http://www.lac.inpe.br/~stephan/CAP-372/matrixmult_microsoft.pdf)