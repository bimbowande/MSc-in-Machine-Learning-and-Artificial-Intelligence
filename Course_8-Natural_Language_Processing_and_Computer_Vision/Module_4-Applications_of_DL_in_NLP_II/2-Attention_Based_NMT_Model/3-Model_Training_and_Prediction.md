# Model Training and Prediction

You have understood how the attention model calculates the context vector which solves the problem seen earlier in the traditional model. But how do we fit this attention model (intermediary) in the architecture we learnt earlier? Let's understand this in the next video.

**VIDEO**

![Attention-Based NMT Model](https://i.ibb.co/SKvGBH6/Attention-Based-NMT-Model.png)
$$\text{Attention-Based NMT Model}$$

Let's quickly go through the entire process with the attention mechanism once again.

1.  The encoder in the NMT model takes in the input sequence and produces a sequence of encoder output which is then fed to the attention model. Unlike the traditional model, here **we keep the encoder output.** 
2.  The decoder, once initialised with the hidden state coming from the encoder, produces an output based on the input it received (`<start>` token) and the context vector generated by the attention model. To generate the context vector, the **attention model takes in the encoder output from all timesteps and the decoder’s hidden state.** The resulting context vector captures the relevant contextual information from the encoder outputs for the ith step of the decoder. 
    -   The attention model’s inputs are as follows:
        
        1.  **Decoder’s hidden state:** represented by **query.**
        2.  **Outputs of the encoder:** represented by **value.**
        
        -   NOTE: The encoder output is a transformation of the hidden state. Therefore, it can be replaced as a value to the attention model. 
3.  Once the context vector is generated, it is then **concatenated with the output** from the embedding layer. This concatenated result is fed to the GRU layer as input. 
4.  The dense layer placed after the GRU does a linear transformation on the output and, thus, you get a **list of probability values for all the words present in the vocabulary**. The word with the **highest probability is selected** as the prediction for that timestep.
5.  For the next word, the hidden state generated by the GRU is fed to the attention model along with the encoder outputs. Based on this new decoder’s state, a new context vector is generated.
6.  To the next cell of the decoder, the previous word is passed as an input along with the updated context vector. Based on these inputs, the GRU repeats the generation. This sequence is continued **till we receive the `<end>/<stop>` token** at the end, which signifies the end of the translation. 

#### GRU

Qn: Which of the following is the input to the GRU?

- Embedding vector

- Context vector

- Encoder output

- None of the above

Ans: D. *The input to the GRU is the hidden state from the encoder along with the concatenated ouptut of Embedding vector and context vector.*

We have used greedy search during the model prediction stage for our traditional model. It is a simple approximation technique that selects the word with max probability at each step for the output caption. But this technique is not an efficient one while predicting the next word. Let’s see the drawbacks of the greedy mechanism and learn about a new technique – beam search in the next video.

**VIDEO**

We know that the prediction of the words by the model is done by finding out the probabilities of different words in the vocabulary. This is done by the following methods:

-   **Greedy search:** This method calculates the probability of the words according to their occurrence in the vocabulary. It takes the sample of the words, finds the probability of each of the words and then outputs the word with the highest probability. This makes the computational speed of the model fast, but the accuracy might not be up to the mark. 
-    **Beam search:** The alternative for greedy search is beam search. In beam search, the model finds the k most likely words instead of selecting a single word and these k words are passed onto the next timestep. It works on the breadth-first search algorithm.

![A Beam Search Representation for k(Width)= 2](https://i.ibb.co/w7nd3cg/A-Beam-Search-Representation-for-k-Width-2.png)
$$\text{A Beam Search Representation for k(Width)= 2}$$

As seen in the video, the beam search algorithm provides us with a better prediction during model inference as it searches for k parallel hypotheses based on conditional probability. In the end, the sentence which has the highest probability is selected. 

**NOTE**: As the beam width is increased, the quality of the predictions improves. However, it is found that the quality of the highest probability hypothesis found by beam search **degrades  
with large beam widths.**

In the next video, let's take a quick look at the model training process for an attention-based NMT model and see how it is different from the traditional model.

**VIDEO**

In the attention-based NMT architecture, the attention model is an inherent part of the decoder. The attention block takes in the encoder’s output and the decoder's hidden state. Using these two inputs, the attention model produces a context vector that summarises all the contextual information at that timestep.   
As seen in the traditional model, we employ teacher forcing here as well to regulate the model training and converge the process faster.

In the next segment, you will implement the attention-based NMT model using TensorFlow.