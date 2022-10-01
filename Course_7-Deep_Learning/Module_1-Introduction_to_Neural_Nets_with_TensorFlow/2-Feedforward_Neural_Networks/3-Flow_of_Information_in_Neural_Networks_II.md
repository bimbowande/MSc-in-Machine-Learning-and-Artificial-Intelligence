# Flow of Information in Neural Networks - II

Let us now take a look at the values of the input, weight matrices and bias vector required to compute the output of the model:

$$\large{x=\begin{bmatrix}1\\1\end{bmatrix},\ w^{[1]}=\begin{bmatrix}1&0\\3&2\\1&2\end{bmatrix},\ w^{[2]}=\begin{bmatrix}1&0&1\\0&1&3\\1&2&1\end{bmatrix},\ w^{[3]}=\begin{bmatrix}1&0&1\end{bmatrix},\ b=\begin{bmatrix}2\\1\\1\end{bmatrix}}$$

Now let us take a look at the upcoming video to understand how to perform calculations to compute the output of the model.

**VIDEO**
 
In the above video, you compute the output of the model, let us go through the steps once again for better understanding. Now, we will revise how to compute the output of this neural network; the steps involved in this are given below:

1. $z^{[1]}_1=w^{[1]}_{11}*h^{[0]}_1+w^{[1]}_{21}*h^{[0]}_2+b^{[1]}_1=1*1+0*1+2=3$, where $h[0]$ is the input vector x  
     
2. $z^{[1]}_2=w^{[1]}_{12}*h^{[0]}_1+w^{[1]}_{22}*h^{[0]}_2+b^{[1]}_2=3*1+2*1+2=7$  
     
3. $z^{[1]}_3=w^{[1]}_{13}*h^{[0]}_1+w^{[1]}_{23}*h^{[0]}_2+b^{[1]}_3=1*1+2*1+2=5$  
     
4. Therefore, $z^{[1]}=\begin{bmatrix}3\\5\\7\end{bmatrix}$
    
Here, notice that in the above equations you have considered bias values $b^{[1]}_1$, $b^{[1]}_2$ and $b^{[1]}_3$. All these values represent the biases for the neurons in layer 1. You can use different values for these terms, essentially each neuron can have its own bias. But, for practical purposes, during implementation, you consider that all neurons in a layer have the same bias as this reduces the number of learnable parameters. Hence, proceeding with understanding, from $b=\begin{bmatrix}2\\1\\1\end{bmatrix}$, you see that $b^{[1]}=2$. 

Therefore,  $b^{[1]}_1=b^{[1]}_2=b^{[1]}_3=2$, as shown in the computation above.

Now you might wonder that by just specifying only a single element in $b^{[1]}$, how does it get applied to all the neurons? In numpy and tensorflow this is possible because of broadcasting, which you'll learn in the future sessions.

Let us now compute the output of first hidden layer $h^{[1]}$ using the cumulative input vector $z^{[1]}$ as shown below:

1. $\large{h^{[1]}_1=sigmoid(z^{[1]}_1)=\dfrac{1}{(1+e^{−z^{[1]}_1})}=\dfrac{1}{(1+e^{−3})}=0.95257}$
     
2. $\large{h^{[1]}_2=sigmoid(z^{[1]}_2)=\dfrac{1}{(1+e^{−z^{[1]}_2})}=\dfrac{1}{(1+e^{−7})}=0.99909}$  
     
3. $\large{h^{[1]}_3=sigmoid(z^{[1]}_3)=\dfrac{1}{(1+e^{−z^{[1]}_3})}=\dfrac{1}{(1+e^{−5})}=0.99331}$  
     
4. Therefore, $\large{h^{[1]}=\begin{bmatrix}0.95257\\0.99909\\0.99331\end{bmatrix}}$
    

Similarly, you can compute the values of z and h for the second hidden layer and the output layer. Try solving this and answering the following questions.

#### Cumulative Input

Qn: Calculate the cumulative input vector $z^{[2]}$ for the example you have been studying so far.

Given: $w^{[2]}=\begin{bmatrix}1&0&1\\0&1&3\\1&2&1\end{bmatrix}$, $h^{[1]}=\begin{bmatrix}0.95257\\0.99909\\0.99331\end{bmatrix}$ and $b^{[2]}=\begin{bmatrix}1\\1\\1\end{bmatrix}$

 You can try using NumPy in python to do the above calculation.

- $\begin{bmatrix}2.94588\\4.97902\\4.94406\end{bmatrix}$

- $\begin{bmatrix}3.94588\\4.97902\\4.84406\end{bmatrix}$

- $\begin{bmatrix}2.94588\\4.99909\\4.94506\end{bmatrix}$

Ans: A. *Perform the matrix calculations as follows:*
$$z^{[2]}=\begin{bmatrix}1&0&1\\0&1&3\\1&2&1\end{bmatrix}*\begin{bmatrix}0.95257\\0.99909\\0.99331\end{bmatrix}+b^{[2]}=\begin{bmatrix}1\\1\\1\end{bmatrix}=\begin{bmatrix}2.94588\\4.97902\\4.94406\end{bmatrix}$$
#### Output of the Hidden Layer

Qn: Calculate the sigmoid output vector $h^{[2]}$ using the $z^{[2]}$ calculated in the previous question. You can try using NumPy in python to do the above calculation.

- $\begin{bmatrix}0.967707\\0.92021\\0.99909\end{bmatrix}$

- $\begin{bmatrix}0.95007\\0.99317\\0.99292\end{bmatrix}$

- $\begin{bmatrix}0.98090\\0.94560\\0.99909\end{bmatrix}$

Ans: B. *Substitute the value of $z^{[2]}$ in the sigmoid activation function formula as follows:*
$$\large{\begin{bmatrix}\dfrac{1}{1+e^{-z^{[2]_1}}}\\\dfrac{1}{1+e^{-z^{[2]_2}}}\\\dfrac{1}{1+e^{-z^{[2]_3}}}\end{bmatrix}=\begin{bmatrix}\dfrac{1}{1+e^{-2.94588}}\\\dfrac{1}{1+e^{-4.97902}}\\\dfrac{1}{1+e^{-4.94406}}\end{bmatrix}=\begin{bmatrix}0.95007\\0.99317\\0.99292\end{bmatrix}}$$
#### Cumulative Input

Qn: Calculate the cumulative input vector z[3]

Given: $w^{[3]}=\begin{bmatrix}1&0&1\end{bmatrix}$, $h^{[2]}=\begin{bmatrix}0.95007\\0.99317\\0.99292\end{bmatrix}$and $b^{[2]}=\begin{bmatrix}1\\1\\1\end{bmatrix}$. You can try using NumPy in python to do the above calculation.

- 3.0156

- 2.94299

- 2.87872

Ans: B. *Perform the matrix calculations as follows:*
$$\large{z^{[3]}=\begin{bmatrix}1&0&1\end{bmatrix}*\begin{bmatrix}0.95007\\0.99317\\0.99292\end{bmatrix}+\begin{bmatrix}1\\1\\1\end{bmatrix}=2.94299}$$

#### Output of the Model

Qn: Calculate the sigmoid output vector $h^{[3]}$ using $z^{[3]}$ calculated in the previous question.

- 0.94993

- 0.98991

Ans: A. *Substitute the value of $z^{[3]}$ in the formula as follows.*  
$$\large{y=h^{[3]}=\dfrac{1}{(1+e^{−2.94299})}=0.94993}$$
#### Fraud Classification

Qn: Consider that you are using the above network for fraud detection. Hence, basis the output calculated in the previous question, what would you conclude? Note that the ground truth labels are1= fraud, 0 = not fraud.  
 
- Fraud transaction

- Not a fraud transaction

Ans: A. *As the predicted output, 0.94993 lies closer to 1, this transaction is a fraud transaction.*

As calculated above, the **feedforward output** or the **predicted output** of the model is 0.94993. Based on the predicted output computed in the previous question, try solving this question:

#### Classification

Qn: Consider a problem where your model is required to classify whether a transaction is fraud or not. Given than the expected output for fraud = 1 and not fraud = 0.

- The transaction is fraud.

- The transaction is not a fraud.

Ans: A. *As the predicted output lies closer to 1, this transaction is a fraud transaction.*

Let’s consider another network and practise computing the dimensions of the weight matrices and the outputs of the various layers of this network. Take a look at the image given below.

![Flow of Information in Neural Network](https://i.ibb.co/vBK87PQ/Flow-of-Information-in-Neural-Network-Qn.png)

Try solving the following questions for the neural network shown in the image.

#### Input vector

Qn: What is the dimension of the input vector $x_1$?

- (5, 1)

- (1, 5)

Ans: A. *There are 5 neurons in the input layer. Hence (5,1). By default, a vector is assumed to be a column vector.*

#### Weight Matrices

Qn: What are the dimensions of the weight matrices W1, W2, W3 and W4?

- (5, 8), (8, 7), (7, 4) and (4, 8)

- (8, 5), (7, 8), (4, 7) and (8,4)

Ans: B. *The dimensions of Wl are defined as (number of neurons in layer l, number of neurons in layer l-1).*

#### Output vectors

Qn: What are the dimensions of the output vectors of the hidden layers h1 and h2?

- (8, 1) and (7, 1)

- (1, 8) and (1, 7)

Ans: A. *The dimension of the output vector for a layer l is (number of neurons in the layer, 1)*

#### Bias vectors

Qn: The dimension of the bias vector is the same as the output vector for a layer l for a single input vector. True or False.

- True

- False

Ans: A. *For a single data input, both have the same dimension.*

#### Number of Learnable Parameters in the Network

Qn: What is the number of learnable parameters in this network? Note that the learnable parameters are weights and biases.

- 156

- 160

- 176

Ans: B. *The weights have 40, 56, 28 and 32 individual parameters (the weight elements). The all the four layers 1 bias each. Therefore, there are a total of 160 learnable parameters.*

In this segment, you learnt how information flows from one layer to another in the forward direction. You also learnt about the dimensions and notations of various vectors as well as the matrices in a neural network. Then, you computed the feedforward output of the neural network.

In the next segment, you will generalise the feedforward equations into an algorithm that can be used for all neural networks and write a pseudocode for the same.