# Skip-Gram Model

In the previous segments, you learnt in detail how the CBOW model works. In this segment, you will gain an understanding of the working of  the Skip-Gram model.

**VIDEO**

In the case of skip-gram, we try to predict the context words given the target word. So, the training data for the skip-gram model for the context size 1 looks like this.

![Training Data](https://i.ibb.co/N2K7n60/Skip-Gram-Context.png)

The input of CBOW becomes the output of skip-gram and vice versa. An example is given below.

|           |             |             |
|-----------|-------------|-------------|
| Model     | X (input)   | Y (output)  |
| CBOW      | [with, has] | upGrad      |
| Skip-Gram | upGrad      | [with, has] |

Remember that these training samples need to be converted to OHE before feeding into the neural network.

Now, you have learnt how to get the training input samples.  Next, you will gain an understanding of the architecture and training of the skip-gram model.

**VIDEO**

The architecture of skip-gram is the same as the CBOW model.

The neural network is a shallow neural network with 1 hidden layer.

The input layer and the output layer have 7 neurons, and this is equal to the size of the vocabulary. 

The hidden layer has a linear activation function, whereas the output layer has the softmax activation function.

The difference appears when you perform forward pass and backpropagation.

The main difference is in the output of the first layer, which appears when you take  the average of two input words in CBOW, but it is not necessary to consider the average of the input words, as only one input word is present in the skip-gram model.

The output of the first layer in CBOW is $l^{out}_1=\dfrac{(<x_1,~W_1>~+~<x_2,~W1>)}{2}$

On the contrary, the output of the first layer in skip-gram is lout1=<x1,W1>  

The differentiating factor in the backpropagation step is that the error needs to be calculated for the two output words [with,has] in the skip-gram model as shown below.

![Skip-Gram Structure](https://i.ibb.co/gSXRtfM/Skip-Gram-Structure.png)

After training the skipgram model, the weight matrix W_1 is a word embedding matrix, which is the same as the CBOW model.   
 
#### Skip-Gram

Qn: Which of the following characteristics is of the skip-gram model?

- Uses the neighbouring words to predict the current word

- Use the current word to predict the words in the neighbourhood

Ans: B. *This is a characteristic of the skipgram model.*

Qn: What is the input vector in the skip-gram model?

- It is represented as a 1-hot-encoded vector

- It is a vector of probability distribution.

Ans: A. *The input vector represents the current/target word and is simply represented as a one hot encoded vector.*

#### Output Vector Dimensions

Qn: On which of the following does the length of the output vector depend?

- Vocabulary size 

- Context size

- The number of words in the sentence

Ans: A. *The output vector size depends on vocabulary size.*

In this segment, you understood the differences and similarities between the CBOW model and the Skip-Gram model. Now, let’s go through a code demonstration wherein we will use these models to create word vectors using the Gensim library.