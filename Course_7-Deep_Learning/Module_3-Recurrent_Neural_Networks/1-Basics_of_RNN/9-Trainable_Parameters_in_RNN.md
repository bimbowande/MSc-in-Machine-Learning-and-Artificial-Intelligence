# Trainable Parameters in RNN

Now that we know about the elements involved in building RNN architectures for different numbers of inputs and outputs, let’s see how they differ in terms of the number of parameters involved.

Let’s consider a RNN unit having two inputs and two outputs. Let’s start with calculating the output layer’s parameters first.

**VIDEO**

So you saw that output layer parameters are due to the dense connections between the output layer and the RNN layer (hidden layer). Output parameters will only be present when we add an explicit output layer on top of RNN layer. Since it will be a dense connection, you can get the number of output parameters in the following way.

  
Number of output layer weights = Number of RNN units * Number of output nodes  
Number of biases = Number of output nodes

Now, let’s learn about the parameters involved with the input layer as well as the RNN layer.

**VIDEO**

You learnt that the hidden RNN layer constitutes connections across each of the RNN units as each of these units needs to know what is going inside the other unit for efficient results.

Now, do you always need to write down all the parameters for calculation? The answer is no. In the next video, Professor Mouli will derive a formula for calculating the number of parameters involved for each of these layers for simple RNN Units.

**VIDEO**

So, you learnt the following formula to calculate the number of parameters for a particular type of layer.

  
$\large{\text{Number of input weights}=\text{Number of input features}*\text{Number of RNN units}}$  
$$\large{\text{Number of recurrent weights}=\text{Number of RNN units}*\text{Number of RNN units}}$$$$\large{\text{Number of biases}=\text{Number of RNN units}}$$
Summing all of the aforementioned parameters, you can get the total number of parameters for a model. Let’s understand through an example. Assuming we have an RNN network with 4 input features, then 5 RNN units and then 3 output labels. Note that there will be an output layer as well because it is a classification problem depicted by output labels.

  
$$\text{Number of input weights}=\text{Number of input features}*\text{Number of RNN units}=4*5=20$$
$$\text{Number of recurrent weights}=\text{Number of RNN units}*\text{Number of RNN units}=5*5=25$$
$$\text{Number of biases}=\text{Number of RNN units}=5$$
$$\text{Number of output layer weights}=\text{Number of RNN units}*\text{Number of output nodes}=5*3=15$$$$\text{Number of biases}=\text{Number of output nodes}=3$$$$\text{Hence total parameters}=\text{input parameters}+\text{recurrent parameters}+\text{output parameters}$$$$=20+(25+5)+(15+3)=68$$
Just like the ANNs, the dimensions of the weights and biases in RNNs will be dependent upon the number of input features, number of hidden RNN units and number of output nodes. In the network we used above, considering that each input will be a single numeric value hence overall dimensions (1x4), the input weights will be of dimension (4x5). Similarly the recurrent weights will have dimensions (5x5), the recurrent bias (1x5) and Output weight will be a matrix of dimension (5x3).

#### Parameters Breakdown

Qn: What will be the number of input layer parameters and recurrent layer parameters respectively, for a RNN model with three input and four output sequences (not considering output layer)?

- 16, 9

- 12, 20

- 9, 16

- 20, 12

Ans: B. *The total input parameter = number of inputs*number of recurrent units = 4 \* 3 = 12. Total recurrent parameters = recurrent weights + bias = 4 \* 4 + 4 = 20*

#### Minimum Parameters

Qn: What will be the minimum number of parameters for a RNN model with three input and four output sequences (not considering output layer)?

- 32

- 36

- 28

- 40

Ans: A. *Total = 12 +20 = 32.*

#### Output Parameters

Qn: Suppose you need to add an output layer with 4 outputs to the RNN model you had built in previous questions. Now, what will be the number of output layer parameters, for the same RNN model which had three inputs and four units in the hidden layer?

- 16

- 4

- 20

- 12

Ans: C. *Total = 4 x4 + 4(bias) = 20*

So that’s how you can calculate the number of parameters in an RNN model. Depending upon the variations in input and output dimensions, the number of parameters will increase or decrease. Similarly there will be changes in the model as well. Following on the same lines you will learn about the types of RNN in the next segment.