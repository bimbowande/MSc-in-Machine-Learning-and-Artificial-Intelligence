# Summary

In this session, you learnt the basic architecture of RNNs, some variants of the architecture applied to different types of tasks and how the information flows between various layers during feedforward and backpropagation.

RNNs are designed to work on sequences that are present in many domains such as time-series data, NLP, computer vision, music and audio. You learnt that the order of the elements in sequences is very important, and we need something more than a standard feedforward neural network to capture the relationships between entities in a sequence.

You studied the architecture of an RNN and its feedforward equations. There are two types of weight matrices – the feedforward weights, which propagate the information through the depth of the network, and the recurrent weights, which propagate information through time. The basic feedforward equation is as follows:
$$\Large{h^l_t=tanh(W^l_Fx^{l−1}_t+W^l_Rh^l_{t−1}+b_l)}$$
We also discussed the different types of RNNs and the tasks they are applicable to:

1. Many-to-one architecture
2. Many-to-many architecture
3. Standard many-to-many architecture
4. Encoder-decoder architecture
5. One-to-many architecture

Along with the training of the RNN about how the forward propagation happens, you learnt about the number of parameters present in the model with the below formulae.

1. _Number of output layer weights = Number of RNN units \* Number of output nodes_
2. _Number of biases = Number of output nodes_
3. _Number of input weights = Number of input features \* Number of RNN units_
4. _Number of recurrent weights = Number of RNN units \* Number of RNN units_
5. _Number of biases = Number of RNN units_

Finally, you briefly studied backpropagation through time (BPTT) and how it leads to the problem of vanishing and exploding gradients in RNNs.

This brings us to the end of the first session. In the next section, you will attempt the graded questions.