# Training of CBOW Model

In the previous segment, you learnt how to prepare the training data for the CBOW model. In the next video, you will gain an understanding of the architecture of the neural network.

**VIDEO**

The architecture of CBOW is shown below. The neural network is a shallow neural network with one hidden layer.

The input layer and the output layer have 7 neurons each, which is equal to the size of vocabulary. You decide the number of neurons in the hidden layer according to the number of dimensions that you want in your word embeddings.

In our case, the hidden layer has a linear activation function, whereas the output layer has the softmax activation function.

![Hidden Layer Activation](https://i.ibb.co/x5hs58t/Hidden-Layer-Activation.png)


#### CBOW

Qn: Let’s consider a CBOW model with a vocabulary size of 10,000.   
Context size = 1  
Features in word embedding = 400  
How many neurons are present in the input layer?  
 
- 10,000

- 1

- 400 

Ans: A. *The number of neurons in the input layer is equal to the vocabulary size.*

Qn: Let’s consider a CBOW model with a vocabulary size of 10,000.  
Context size = 1  
Features in word embedding = 400  
Based on this information, what is the size of the weight matrix between the input layer and the hidden layer W1?  

- (10,000,  400)

- (400,  10,000)

- (10,000,  1)

- (1,  10,000)

Ans: A. *The size of the weight matrix = (the number of neurons in the previous layer, the number of neurons in the next layer)*

For a training pair ([with, has], upGrad) 

input X = [with,has] 

output Y = upGrad

The task of the neural network is to predict the output, given the following input.

![Predict Words](https://i.ibb.co/rcLyxDG/Predict-Words.png)

One hot encoding of the words ‘with’ and ‘has’ will be the inputs of the neural network, and the output of the network should be upGrad.

![Network Structure](https://i.ibb.co/KzZ1bP7/Network-Structure.png)

The OHE of the inputs flows through the network in the forward pass in the following manner:

Output of hidden layer $=l^{out}_1=\dfrac{(<x_1,~W_1>~+~<x_2,~W_1>)}{2}$

$l^{out}_1$ is  $(1X3)$  vector

Output of last layer $=l^{out}_0=f(<l^{out}_1,~W_2>)$

$l^{out}_0$ is $(1X7)$  vector

_Note: The output of the first hidden layer is calculated by taking the average of the input vectors as specified in the [https://cs224d.stanford.edu/lecture_notes/notes1](https://cs224d.stanford.edu/lecture_notes/notes1.pdf) [https://web.stanford.edu/~jurafsky/slp3/6](https://web.stanford.edu/~jurafsky/slp3/6.pdf). Other heuristics can also be used._

The output of the neural network will not give a one hot encoding vector of upGrad. As the output layer has the activation function of softmax, we will train the network such that the probability of the target word is high in the output. 

As shown in the diagram given above, the probability is the highest in the fifth position of upGrad.

Now that you have learnt how an input passes through the forward pass, you will learn how the network is trained using backpropagation.

**VIDEO**

The neural network uses a backpropagation algorithm that compares the actual output and predicted output and tries to minimise the loss. Although you saw this for only one training sample, weight matrices are updated after training for all the training samples that were defined earlier. 

Now that our training is complete, we can predict a word given its context words. However, considering you already knew those words, why are we doing this? In the next segment, you will gain an understanding of this.