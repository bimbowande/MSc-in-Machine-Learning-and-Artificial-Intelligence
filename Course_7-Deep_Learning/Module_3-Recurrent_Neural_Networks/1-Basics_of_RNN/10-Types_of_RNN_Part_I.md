# Types of RNN - Part I

In the previous segments, you have gone through different kinds of problems that RNNs can solve. You might want to classify a particular review into positive and negative, the architecture of which will have only a single output. On the other hand, you might want to assign a part of speech tag to each word in the text and, hence, the architecture will need multiple outputs. Based on this change in input and output dimensions, RNNs require slight change in the architecture. Let’s look at the different types of RNN in the next video.

**VIDEO**

You learnt that there are two controlling factors for the different types of RNNs -

1.  Number of inputs
2.  Number of outputs

Based on this, you saw how one-to-one and one-to-many works.

  
One-to-one takes just one input and gives one output, hence only one RNN cell is sufficient to achieve this configuration. Let’s take the example of binary image classification where you can input the whole image at once into the RNN cell and similarly get the output also from the same RNN cell only. Hence this is just a one-to-one example.

However for one-to-many units, since you will need a sequence of outputs, hence you will need to have multiple RNN cells to build this type of model. Let’s take an example of image captioning where you can still give an image as an input at once into an RNN cell but you will need to have outputs at different RNN cells to generate accurate captions. Therefore, it is an one-to-many example.

Let’s learn more about the remaining types of RNN from Professor Mouli.

**VIDEO**

RNN can be of the following types based on input/output dimension with examples:

1.  One-to-one RNN: Just like a simple feedforward neural network
2.  One-to-many RNN: Image captioning
3.  Many-to-one RNN: Sentiment classification
4.  Many-to-many RNN (even length): Part of speech tagging
5.  Many-to-many RNN (Odd length): Machine translation

Note that here the time steps taken for input and output is the determining factor to distinguish the type of RNN. For example let's take the example of POS tagger, which is a many-to-many RNN. In the case of POS tagger, we input the words one by one at each time step to understand the underlying dependencies and get output at each time step, hence it’s a many-to-many RNN problem.

Let’s take another example of Sentiment analysis, where we input words one by one so that our model can understand the sequential meaning of the sentence. But we take output at only the last time step hence the output is just one, meaning it is a many-to-one RNN problem.

So, wherever you find that sequential understanding is required to model the data, RNN is the go-to model. Now, let’s revise these important RNN types before going forward.

#### Many-to-One Architecture
In this architecture, the input is a sequence while the output is a single element. We have already discussed an example of this type – classifying a sentence as grammatically correct/incorrect. The following figure shows the many-to-one architecture:

![Many-to-One Architecture](https://i.ibb.co/WHH2Zdx/Many-to-One-Architecture.png)

Some other examples of many-to-one problems are as follows:

1.  Predicting the sentiment score of a text (between -1 to 1). For e.g., you can train an RNN to assign sentiment scores to customer reviews, etc. Note that this can be framed as either a regression problem (where the output is a continuous number) or a classification problem (for e.g., when the sentiment is positive/neutral/negative)  
     
2.  Classifying videos into categories by analysing the sequence of frames or images constituting the video; for example, say you want to classify YouTube videos into two categories 'contains violent content’ and ‘does not contain violence'. The output can be a single softmax neuron which predicts the probability that a video is violent.

You are using just the output of the final timestep to make the prediction for the classification/ regression problem.

You will use this architecture in the third session where you will implement a case study on predictive maintenance.

  
#### Many-to-Many (Equal Length) Architecture
You are already familiar with this type of architecture. In this type of RNN, the input (X) and output (Y) both are a sequence of multiple entities spread over timesteps. The following image shows such an architecture.

![Many-to-Many (Equal Length) Architecture](https://i.ibb.co/RBSxxSR/Many-to-Many-Equal-Length-Architecture.png)

In this architecture, the network spits out an output at each timestep. There is a one-to-one correspondence between the input and output at each timestep. Hence, this is a many to many equal length RNN.
  
#### Many-to-Many (Unequal Length) Architecture
In the previous many-to-many example of POS tagging, we had assumed that the lengths of the input and output sequences are equal. However, this is not always the case. There are many problems where the lengths of the input and output sequences are different. For example, consider the task of machine translation – the length of a Spanish sentence can be different from the corresponding English sentence.

To summarise, the encoder-decoder architecture is used in tasks where the input and output sequences are of different lengths. The architecture is shown as follows:

![Many-to-Many (Unequal Length) Architecture](https://i.ibb.co/VJQy2CL/Many-to-Many-Unequal-Length-Architecture.png)

The given architecture comprises two components – an encoder and a decoder, both of which are different RNNs themselves. The output of the encoder, called the encoded vector (and sometimes also the 'context vector'), captures a representation of the input sequence. The encoded vector is then fed to the decoder RNN which produces the output sequence.

You can see that the input and output can now be of different lengths since there is no one-to-one correspondence between them anymore. This architecture gives the RNNs much-needed flexibility for real-world applications such as language translation.

#### RNN Model Selection

Qn: Suppose you have a use case at hand which involves sequential modelling of many-to-many architecture. Which of the following architecture types will you follow?

- Normal RNN architecture if input and outputs are always of same length

- Normal RNN architecture if input and outputs are of different length

- Encoder-decoder RNN architecture if input and outputs are of different length

- Encoder-decoder RNN architecture if input and outputs are always of same length

Ans: A & C. *Normal RNN architectures (many-to-many) can be used when inputs and outputs are always of the same length. Encoder-decoder RNN architectures (many-to-many) can be used when inputs and outputs are of different length.*

You learnt that RNN can be categorised based on input and output dimensions spread across time steps but there is another way of classifying RNNs. You will learn about it in the next segment.