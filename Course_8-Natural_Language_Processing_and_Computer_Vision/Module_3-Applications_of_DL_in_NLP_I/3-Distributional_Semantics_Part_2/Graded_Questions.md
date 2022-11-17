Let us solve the following questions based on what we have learnt in this session:

After training the neural network, to extract the word embeddings, you obtain the weight matrix (the one between the input layer and the hidden layer). Assume that the vocabulary size is 10. Also, you used a skip gram model to train the network.  
Our vocabulary contains the following.

| man | machine | tower | capital | flight | grass | football | league | Germany | France |
| --- | ------- | ----- | ------- | ------ | ----- | -------- | ------ | ------- | ------ |

The following table represents the relative position of each word in the vocabulary.

| 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

The weight matrix is given below:

| 0.21 | 0.47 | 0.18 |
| ---- | ---- | ---- |
| 0.34 | 0.55 | 0.70 |
| 0.15 | 0.17 | 0.89 |
| 0.66 | 0.1  | 0.2  |
| 0.6  | 0.38 | 0.4  |
| 0.5  | 0.27 | 0.7  |
| 0.42 | 0.17 | 0.9  |
| 0.52 | 0.56 | 0.11 |
| 0.23 | 0.51 | 0.85 |
| 0.7  | 0.4  | 0.3  |

Answer the following comprehension questions:

#### Input Layer

Qn: How many neurons are present in the input layer?

10

3

9

8

Ans: A. *The size of the input layer is equal to the size of the vocabulary.*

#### Input Vector

Qn: The input word is ‘tower’. According to the skipgram model, how would this input be represented?

- (0,1,0,0,0,0,0,0,0,0)

- (0,0,1,0,0,0,0,0,0,0)

- (0,0,0,1,0,0,0,0,0,0)

- (0,0,0,0,1,0,0,0,0,0)

Ans: B. *This is the input vector for the word ‘tower’*

#### Word Vector

Qn: According to the weights generated above, what will be the word vector corresponding to the word ‘flight’?

- (0.6, 0.38, 0.4) 

- (0.5, 0.27, 0.7)

- (0.66, 0.1, 0.2)

- (0.42, 0.17, 0.9)

Ans: A. *This is the word vector for the word ‘flight’.*

#### CBOW vs Skip-Gram

What is a similarity between the CBOW model and the Skipgram model for a given context size?

The number of neurons in the input layer and the output layer

The input training samples

The output of the first hidden layer 

All of the above

Ans: A. *The architecture of the neural network is the same in both models.*

Qn: What is/are the difference in the CBOW and Skipgram Model for a given context size? (Multiple options can be correct)

- The number of neurons in the input layer and the output layer

- The input training samples

- The output of the first hidden layer 

- All of the above

Ans: B & C. *The input training samples and the output of the first hidden layer are different in the CBOW model and the skipgram model.*

Let us summarise what we have learnt in the next segment.

