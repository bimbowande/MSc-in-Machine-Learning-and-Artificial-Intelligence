# Flow of Information in Neural Networks - I

In the previous session, you learnt about the basic structure of a neural network and understood its various aspects such as topology, hyperparameters and simplifying assumptions for neural networks. In this segment, you will learn how information flows from one layer to the next in a neural network and how the network output is computed. 

  
In the next video, let’s quickly revise the important notations and matrix representations that you will use commonly throughout this session.

**VIDEO**

#### Notations

Qn: Which of the following is correct for layer 1?

- $w^{[1]}=(3,2)$

- $z^{[1]}=w^{[1]}∗h^{[1]}+b^{[1]}$

- $z^{[1]}=w^{[1]}∗h^{[0]}+b^{[1]}$

- $w^{[1]}=(2,3)$

Ans: A & C. 

- *If you recall the previous segment, the weight matrix notations are $(n^{[l]}, n^{[l−1]})$ . Therefore, it will be (3,2).*

- *The cumulative input is given by $z^{[l]}=w^{[l]}∗h^{[l−1]}+b^{[l]}$ . Therefore, for $l=1$,  it will be $z^{[1]}=w^{[1]}∗h^{[0]}+b^{[1]}$.*

In this video, you were introduced to a simple neural network with two hidden layers and an input and output layer, with each layer having a different number of neurons, weights and biases associated with them as shown in the image given below.

![Neural Network Notations](https://i.ibb.co/2hgfjH2/Neural-Network-Notations.png)

In artificial neural networks, the output from one layer is used as an input to the next layer, which is referred to as a **feedforward neural network**. This means the network contains no loops, that is, information is always fed forward and never fed back. 

  
In the next video, let’s start by solving a simple example using the network shown above to understand the feedforward mechanism.

**VIDEO**

#### Bias Vector

Qn: As you saw in the video, the notation of the bias vector is (3,1) i.e., (number of layers,1). Consider the neural network given above. The bias vector of this network is given by:  $b=\begin{bmatrix}2\\1\\1\end{bmatrix}$. What will be the bias of the first, second and third neuron of the second hidden layer?   
 
- 2, 1, 1 respectively

- 1, 1, 1 respectively

- 2, 2, 2 respectively

Ans: B. *The bias of all the neurons in the second hidden layer is the same and is given by the second element of the bias vector i.e., 1.*

Note: In the video at [02:57], the SME mentions that for layer 2, $h^{[l]}$ is the input calculated at the previous layer 1. Instead, $h^{[l]}$ is the input to this layer 2, which is the output of the previous layer 1.

In the video above, you considered an example, let us take a look at this example and understand the notations in detail. Given below are the notational representations of the input, weight matrices and bias vector for this example:

-   Input vector, $x=\begin{bmatrix}x_1\\x_2\end{bmatrix}$

As you have already learnt in the previous session, the superscript of the weight matrix between layer 'l' and 'l-1' is denoted by 'l'.

The subscript nomenclature followed represents the

(number of the neuron in layer 'l-1', that of the neuron in layer 'l').

Let us write the weight matrix notations for each layer:

-   The weight matrix between the input layer(2 neurons) and 1st hidden layer(3 neurons) will have (3 X 2) dimensions and can be written as $w^{[1]}=\begin{bmatrix}w_{11}&w_{21}\\w_{21}&w_{22}\\w_{31}&w_{23}\end{bmatrix}$  
     
-   The weight matrix between the 1st(3 neurons) and 2nd(3 neurons) hidden layer will have (3 X 3) dimensions and can be written as $w^{[2]}=\begin{bmatrix}w_{11}&w_{21}&w_{31}\\w_{21}&w_{22}&w_{23}\\w_{31}&w_{23}&w_{33}\end{bmatrix}$  
     
-   The weight matrix between the 2nd hidden layer(3 neurons) and output layer(1 neuron) will have (1 X 3) dimension and can be written as $w^{[3]}=\begin{bmatrix}w_{11}&w_{21}&w_{31}\end{bmatrix}$

Note that the above nomenclature is something that has been followed in this literature. In many of the literatures found on the internet, you might find that the subscript nomenclature of the individual weights in the weight matrix would represent the

(number of the neuron in layer 'l', that of the neuron in layer 'l-1'). 

As a result, the weight matrix representation changes and becomes the transpose of the weight matrices defined above. The important point that you need to realise is that even though the nomenclature is different, the conceptual understanding will not change.

You have previously seen that the value of the bias vector for all neurons in a particular layer is the same. Let's understand some key features of the bias vector.

-   The bias vector dimensions for this example will be (3 X 1) as there are three layers, aside from the input layer, in this network.
-   Therefore bias vector can be written as follows: $b=\begin{bmatrix}b^{[1]}\\b^{[2]}\\b^{[3]}\end{bmatrix}$
-   $b^{[1]}$, $b^{[2]}$ and $b^{[3]}$ are the bias vectors for layers 1, 2 and 3 respectively. 
-   $b^{[1]}$, $b^{[2]}$ and $b^{[3]}$ for all practical implementations are usually a vector of a single element as it helps in reducing the number of learnable parameters.

Therefore, you can summarise the following: 

1.  The dimensions of the weight matrix are given by $(n^{[l]}, n^{[l−1]})$.
2.  The dimensions of the bias vector are given by $(n^{[l]}, 1)$.

Here, ‘l’ denotes the layer number, and ‘n’ denotes the number of neurons in that layer.

Next, you also learned the feedforward equations, i.e., the equations for the z and h vectors. The cumulative input $z^{[l]}$ and the output of the hidden layer $h^{[l]}$ are calculated from the values of inputs, weights and biases using the formulas given below.

1.  Cumulative Input, $\large{z^{[l]}=w^{[l]}*h^{[l−1]}+b^{[l]}}$
2.  The output of hidden layer(sigmoid), $\large{h^{[l]}=\dfrac{1}{(1+e^{−z^{[l]}})}}$

Note: In the previous session, you learnt about the formula for cumulative input, which is $\large{z=w^T*x+b}$. You will notice that the formula for $z^{[l]}$ given above does not have a transpose term because the dimensions of the inputs and the weights for each layer, i.e., $(n^{[l]}, n^{[l−1]})$, are already considered such that they are compatible for mathematical operations, and you do not need to transpose these matrices. It has already been taken care of in order to reduce the complexity of the calculations required for this multi-layered neural network.

Let us move to the next segment, and solve this example and compute the output of the network.