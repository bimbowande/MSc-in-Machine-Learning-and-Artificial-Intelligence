# Mathematics Behind the Attention Model

You saw that the attention mechanism takes the output from all the encoder states/ timesteps rather than the last state. This forms the core principle/idea behind the attention mechanism, thus overcoming the drawbacks of a traditional CNN-RNN model. But you might be wondering how to actually implement such a model that knows where to look at each timestep. Let's dive right in and understand the mathematics and inner workings of the attention mechanism in the next video.

**VIDEO**

In the traditional NMT model, which uses the normal encoder-decoder, there is only one context/feature vector which would be passed on in the hidden state while decoding during translation. However, with an attention model, you get a varying vector based on the previously generated word at each time step. This helps you to look at different parts of the input sequence for better translation.

-   Let $(h_1,h_2, \dots, h_n)$ represent the encoder’s hidden state which captures the entire input sequence.
-   These encoder states are then passed to the attention model which provides us with the context vector $C_i$ **that summarises the context of the entire input sequence at every ith timestep.**

To calculate the importance of any encoder hidden state $h_j$, you **calculate a score between $h_j$ and the decoder’s hidden state generated at previous timestep $h_{i−1}$**.

-   This score, represented by $e_{ij}$ defines the importance of the encoder’s state for the given decoder’s state. This is represented by the equation $e_{ij}=a(h_{i−1},h_j)$.
-   To an attention model, which is a kind of neural network, you pass in **$h_{i−1}$ (decoder's previous hidden state) and $h_j$ (encoder’s hidden state). Therefore, with this information, you can get **how important is the jthstate of the encoder at the ithtime stamp.**

-   The scoring function can be imagined as a dot product which is a similarity function. If the decoder state $h_{i−1}$ has a high similarity with $h_j$ (encoder state), then the score eij will be higher and vice versa.

This score is just a representative value between $h_{i−1}$ and **hj**, but ideally, we want a distribution of score between $h_{i−1}$ and all the encoder states $(h_1,h_2, \dots. , h_n)$. Also, this distribution of score should add up to 1, i.e., it should have a probability distribution. This can be done by normalising the result using a softmax function.   
$\alpha_{ij}=softmax(e_{ij})$

The αij depicts our attention weights (the probability distribution) of all the encoder states. Once you have this value, you just need to take a weighted sum of the attention weights for each encoder state. This will represent the context vector at ith timestep.

This weighted sum produces the context vector $C_i=\sum^n_{j=1}\alpha_{ij}h_j$

![The Context Vector Generated for h2 Hidden State](https://i.ibb.co/KLJKwYD/The-Context-Vector-Generated-for-h2-Hidden-State.png)

$$\text{The Context Vector Generated for h2 Hidden State}$$

This vector captures the relevant contextual information from the input sentence for the ith step of the decoder. It uses a weighted sum of all the hidden states instead of just the last one, thus providing better interpretability.

![Computational process of Attention mechanism](https://i.ibb.co/YZ79NQw/Computational-Process-of-Attention-Mechanism.png)

$$\text{Computational process of Attention mechanism}$$

In the end, we concatenate the context vector (Ci) and the decoder’s hidden state **hi−1**. This concatenated information is then passed onto the RNN along with the previous prediction. 

Therefore, it can be said that attention is a technique using which you compute which value (encoder state) to focus on and how much for any given query (decoder state). 

![Attention Technique](https://i.ibb.co/bRVHMkZ/Attention-Technique.gif)

To summarise, given a set of vector values and a vector query, the attention function **computes a weighted sum of the values dependent on the query**. This weighted sum (context vector) is a **selective summary of the information represented by values, which the query attends to.** 

You learnt that the attention function can be used to calculate the score eij between the decoder hidden state and the encoder states. But what is this function? Let’s learn more about it in the next video.

**VIDEO**

You can use any one of the following scoring functions in your attention mechanism:

-   Dot product attention: $h^T_ih_j$
-   Multiplicative attention: $h^T_iWh_j$, where  W is a weight matrix 
-   Additive attention: $V^Ttanh(W_1h_i+W_2h_j)$, where $W_1$ and $W_2$ are weight matrices and $V$ is a weight vector.

Among these scoring functions, the most popular is additive attention (**Bahdanau** et al 2015) represented by $V^Ttanh(W_1h_i+W_2h_j)$.   
The weight matrices $W_1$ and $W_2$ are the dense layers that are operated on decoder and encoder states, respectively. 

Once the dense layers are structured, you add a non-linear mapping on top of it using the $tanh$ activation function. The $e_{ij}$ resulting from non-linear mapping is introduced with $V$ to convert $e_{ij}$ into a scalar value. 

**Note:** The attention function (like the encoder and decoder) is differentiable and can be trained end-to-end. The attention model itself will learn to assign the weights to different values on the basis of a given query.

  
For the implementation of NMT, you will be working with Bahdanu’s function to calculate the scores. 

#### Attention model

Qn: What are the inputs to the Attention model?

- Hidden state coming from the decoder model.

- The output of the decoder from the previous time-stamp.

- Text input (which is fed as a sequence to the attention model at each timestamp).

- All the hidden states coming from the encoder 

Ans: A & D. *The attention model needs the hidden state to understand what has been produced so far to have the context. The attention model, in order to create the context vector, needs two inputs: decoder's hidden state and encoder's hidden state.*

#### Context Vector

Qn: Which of the following statements is true about the context vector generated by the attention model? (More than one option may be correct.)

- The context vector captures the relevant contextual information from the input sentence for the $i^{th}$ step of the decoder. 

- It is created by the weighted sum of all the encoder's hidden states with their respective  attention weights.

- The context vector and the embedding vector is concatenated and passed to the RNN cell.

Ans: All of the above. *The context vector captures the relevant contextual information from the input sentence for the $i^{th}$ step of the decoder. The context vector is created by the weighted sum of all the encoder's hidden states with their respective attention weights. The context vector and the embedding vector is concatenated together and passed to the RNN cell.*

#### Query

Qn: Which of the following is represented as query in the attention model?

- Encoder's hidden state

- Decoder's hidden state

- Encoder's output

- Decoder's output

Ans: B. *The decoder hidden state is represented as the query on the basis of which the weighted values are computed.*

In the next segment, you will see how you will integrate this attention mechanism in the encoder-decoder architecture to create a better model.