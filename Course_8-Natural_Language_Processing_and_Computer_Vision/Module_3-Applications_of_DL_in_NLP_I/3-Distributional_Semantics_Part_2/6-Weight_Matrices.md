# Weight Matrices

In the previous segments, you learnt how to create input training samples, architecture, forward pass and backpropagation for the CBOW model. However, this is not what we are actually interested in. We are interested in what the model has learnt and is stored in weight matrices. 

Word embeddings are stored in weight matrices. In the next video, you will learn how to extract word embedding or word vectors from these weight matrices.

**VIDEO**

We have considered W1 as our embedding matrix.

You understood that if you multiply the one hot encoding form of the word with the matrix, you will obtain word embedding of that word. As seen in the video, the OHE of upGrad is as follows.

| 0 | 0 | 0 | 0 | 1 | 0 | 0 |
|---|---|---|---|---|---|---|


$W_1$ (the weight matrix of the hidden layer) =

![Word Embedding](https://images.upgrad.com/9f6468d3-d015-4edb-9217-6650467d6a3b-Screenshot%202021-06-02%20at%203.39.34%20PM.png)

Word Embedding

The word embedding or word vector of upGrad is as follows.

| 0.56 | 0.21 | 0.67 |
|------|------|------|


You will observe that every row in the weight matrix $W_1$ is a word embedding. Rather than multiplying the OHE by a weight matrix, we can directly pick the row according to the position of 1 in OHE and use $W_1$ as a look-up matrix.

The word embedding of a word not only captures the meaning of the word but also reduces the dimensions of the word vector. 

The dimension of word vector (OHE) was 7, which was reduced to 3 in the word embedding. 

Why is the weight matrix a word embedding matrix?

To find the answer to this, let’s watch the video given below.

**VIDEO**

The neural network learns by minimising the loss function and maximising the dot product between the input word vector and the output word vector. 

You learnt how one OHE of upGrad gets transformed when it is multiplied by $W_1$ and $W_2$. Now, you will learn how you can relate this to maximising the dot product between the input and the output word.

_Note: $W_1$ and $W_2$ are not transposes of each other, although we have considered $W_1$ to be our word embedding matrix in our calculations._ 

**VIDEO**

Now, we can conclude that weight matrices are word embedding matrices.

With this, you have learnt how the CBOW model works. In the next segment, you will gain an understanding of the Skip Gram and the differences between the Skip Gram and CBOW models.