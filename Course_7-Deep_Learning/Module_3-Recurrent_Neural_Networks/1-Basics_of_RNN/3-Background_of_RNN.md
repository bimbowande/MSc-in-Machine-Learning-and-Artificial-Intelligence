# Background of RNN

Just like CNNs, which were designed to process images, Recurrent Neural Networks (RNNs) are designed to process sequential data.

Before we get started, let’s understand what Recurrent in RNN means.

**VIDEO**

Let’s first revise our understanding of artificial neural networks, abbreviated as ANN.

**VIDEO**

Let’s also refresh the understanding of CNN which will help in understanding RNN better.

**VIDEO**

Now, you understand that simple feedforward neural networks such as ANN and CNN have the following two major issues:

1.  Cannot handle varying input/output length
2.  Consider each data points to be independent from each other

RNN architecture enables us to address both these problems. In the next video, Professor Mouli will discuss the speciality of RNN in detail.

**VIDEO**

So, RNN not only has connections across layers but also across the time domain. This added feature helps RNNs in learning the sequential ordering of data.

#### Feature of RNN

Qn: What makes RNN better than CNN for sequential modelling?

- Increased number of layers

- Extra dimension which connects the model across time steps

- More number of units in each layer

- Use of special activation function

Ans: B. *There is an additional time domain in RNN acting as a recurrent connection.*

RNNs have an added time dimension but how do we use this feature of RNNs to formulate and solve problems? Let's discuss that in the next segment.