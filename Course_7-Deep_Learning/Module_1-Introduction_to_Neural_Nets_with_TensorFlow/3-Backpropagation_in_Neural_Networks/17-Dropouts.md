# Dropouts

In the previous segment, you learnt about two basic regularization techniques, the L1 norm and the L2 norm. In this segment, you will learn about another popularly used regularization technique specifically for neural networks called **dropouts**. Let’s watch the video to learn more about this technique.

**VIDEO**

To summarise, the dropout operation is performed by multiplying the weight matrix $W^l$ with an $\alpha$ **mask vector** as shown below.
$$\large{W^l.\alpha}$$
For example, let's consider the following weight matrix of the first layer.
$$\large{W^1=\begin{bmatrix}w^1_{11}&w^1_{12}&w^1_{13}\\w^1_{21}&w^1_{22}&w^1_{23}\\w^1_{31}&w^1_{32}&w^1_{33}\\w^1_{41}&w^1_{42}&w^1_{43}\end{bmatrix}}$$
  
Then, the shape of the vector $\alpha$ will be (3,1). Now if the value of $q$ (the probability of 0) is 0.66, the α vector will have two 1s and one 0. Hence, the α vector can be any of the following three:
$$\large{\begin{bmatrix}0\\0\\1\end{bmatrix}~\text{or}~\begin{bmatrix}0\\1\\0\end{bmatrix}~\text{or}~\begin{bmatrix}1\\0\\0\end{bmatrix}}$$
  
One of these vectors is then chosen randomly **in** **each mini-batch.** Let's say that, in some mini-batch, the mask $\alpha=\begin{bmatrix}1\\0\\0\end{bmatrix}$ is chosen. Hence, the new (regularised) weight matrix will be:
$$\large{\begin{bmatrix}w^1_{11}&w^1_{12}&w^1_{13}\\w^1_{21}&w^1_{22}&w^1_{23}\\w^1_{31}&w^1_{32}&w^1_{33}\\w^1_{41}&w^1_{42}&w^1_{43}\end{bmatrix}.\begin{bmatrix}0\\0\\1\end{bmatrix}=\begin{bmatrix}0&0&w^1_{13}\\0&0&w^1_{23}\\0&0&w^1_{33}\\0&0&w^1_{43}\end{bmatrix}}$$

You can see that all the elements in the first and second column become zero.

Some important points to note regarding dropouts are:

-   Dropouts can be applied only to some layers of the network (in fact, this is a common practice; you choose some layer arbitrarily to apply dropouts to).
-   The mask α is generated independently for each layer during feedforward, and the same mask is used in backpropagation.
-   The mask changes with each minibatch/iteration, are randomly generated in each iteration (sampled from a Bernoulli with some $p(0)=q$).

Dropouts help in **symmetry breaking**. There is every possibility of the creation of communities within neurons, which restricts them from learning independently. Hence, by setting some random set of the weights to zero in every iteration, this community/symmetry can be broken. 
  
Note: A different mini-batch is processed in every iteration in an epoch, and dropouts are applied to each mini-batch.
  
Try to solve the following question to reinforce your understanding of the concept of dropouts.

#### Alpha Vector Dimension

Suppose you want to add dropout to the weight matrix $W^3$ with dimension (4, 7). What will be the dimension of the mask vector α?

- 4

- 7

Ans: B. *As can be observed from the example stated in the text, α has a dimension = (number of neurons in layer '$l-1$', 1).*

#### Dropouts

Qn: Suppose you want to add dropout to the weight matrix $W^3$ with dimension (4, 7). The value of '$q'$, which is the probability of 0, is 0.25. How many elements in $W^3$ will be set to 0?

- 7

- 21

Ans: A. *There are 28 weight elements. The probability of 0 is 0.25. Hence, 25% of the weight elements will be set to 0, which is 7.*

Notice that after applying the mask α, one of the columns of the weight matrix is set to zero. If the jth column is set to zero, it is equivalent to the contribution of the jth neuron in the previous layer to zero. In other words, you cut off one neuron from the previous layer. 
  
There are other ways to create the mask. One of them is to create a matrix that has 'q' percentage of the elements set to 0 and the rest set to 1. You can then multiply this matrix with the weight matrix element-wise to get the final weight matrix. Hence, for a weight matrix $\begin{bmatrix}w^1_{11}&w^1_{12}&w^1_{13}\\w^1_{21}&w^1_{22}&w^1_{23}\\w^1_{31}&w^1_{32}&w^1_{33}\\w^1_{41}&w^1_{42}&w^1_{43}\end{bmatrix}$, the mask matrix for 'q'  = 0.66 can be $\begin{bmatrix}0&1&0\\0&0&1\\1&0&0\\0&0&1\end{bmatrix}$.

Multiplying the above matrices element-wise, we get . $\begin{bmatrix}0&w^1_{12}&0\\0&0&w^1_{23}\\w^1_{31}&0&0\\0&0&w^1_{43}\end{bmatrix}$.

Well again, you need not worry about how to implement dropouts since you just need to write one simple line of code to add dropout in Keras:

```python
# dropping out 20% neurons in a layer in Keras 
model.add(Dropout(0.2)
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)Please note that '0.2' here is the **probability of zeros**. This is also one of the hyperparameters. Also, note that you **do not apply** dropout to the output layer.

So far, you have learnt about two types of regularization strategies for neural networks. Next, you will be learning about another technique knows as **batch normalization.**
