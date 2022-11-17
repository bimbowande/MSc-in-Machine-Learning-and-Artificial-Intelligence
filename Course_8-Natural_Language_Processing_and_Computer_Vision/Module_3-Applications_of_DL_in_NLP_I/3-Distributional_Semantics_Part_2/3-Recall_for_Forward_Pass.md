# Recall for Forward Pass

In the previous segment, you learnt that neural networks are used by the Word2Vec model to produce word embeddings. Before you learn in detail how the Word2Vec model works, let’s revise the concept of neural networks.

**VIDEO**

A general representation of the Input Data Matrix is given below wherein n represents the number of features and m represents the number of samples. In the Iris data set, you saw that the number of features n is 4–sepal length, sepal width, petal length and petal width.

We designed the neural network that had 4 input neurons, as we had 4 features in the Iris data set and 3 neurons in the output layer, as we had 3 classes, which are setosa, virginica and versicolor. The number of neurons in the hidden layer is arbitrarily decided. 

![Iris Dataset Neural Network](https://i.ibb.co/yVsHCVF/Iris-Dataset-Neural-Network.png)

Now, you gained an understanding of the different components in a fully connected neural network. These are as follows:

-   Input Layer
    
-   Weight Matrix ($W_1$)
    
-   Hidden Layer 1
    
-   Activation function of layer 1 ($f_1$)
    
-   Weight Matrix ($W_2$)
    
-   Hidden Layer 2
    
-   Activation function of layer 2 ($f_2$)
    
-   Weight Matrix ($W_o$)
    
-   Output Layer
    
-   Activation function of output layer ($f_0$)
    

The dimensions of the weight matrix are deduced from the numbers of neurons in the previous layer and in the next layer.

Number of rows of the weight matrix = Number of neurons in the previous layer

Number of columns of the weight matrix = Number of neurons in the next layer

You learnt how one input sample goes through the different layers of neural network, and this is given below:

-   Input to the first layer: $l^1_{in}=<X,~W_1>+~b_1$
    
-   Output of the first layer: $l^1_{out}=f_1(l^1_{in})$
    
-   Input to the second layer: $l^2_{in}=<l^1_{out},~W_2>+~b_2$
    
-   Output of the second layer: $l^2_{out}=f_2(l^2_{in})$
    

*NOTE: The notations used in the formulae may vary. The dot product between two vectors X, Y can be denoted as$ <X,~Y>$ or $Y^TX$.* 

*In many cases, you will encounter $W^TX+b$ instead of $<X,~W>+b$ as one of the notations. Do not be alarmed; they both denote the same thing.*

#### Output layer

Qn: Our data still needs to be passed through one more layer: the output layer. What will the formulae of the output of the output layer look like if the weights are W3,b3,f3?

- Input to the output layer: $l^3_{in}=<l^2_{out},~W_3>+~b_3$  and, Output of the output layer: $l^3{out}=f_3(l^3_{in})$

- Input to the output layer: $l^2_{in}=<l^2_{out},~W_3>+~b_3$  and, Output of the output layer: $l^3{out}=f_3(l^2_{in})$

- Input to the output layer: $l^2_{in}=<l^2_{out},~W_3>+~b_3$  and, Output of the output layer: $l^3{out}=f_2(l^2_{in})$

- None of the above

Ans: A

In the next segment, let us understand CBOW model in detail.