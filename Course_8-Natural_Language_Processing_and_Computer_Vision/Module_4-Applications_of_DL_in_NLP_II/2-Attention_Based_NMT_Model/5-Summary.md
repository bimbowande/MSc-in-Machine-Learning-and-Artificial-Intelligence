# Summary

You have come a long way! You have learnt what is Attention modelling in NMT architecture and how does it work. The most important points to reiterate are:

In the traditional model it is assumed that the context vector can be summarised using the last timestep of the encoder. However, in the Attention-Based NMT model, all the encoder states are taken and for each decoder state the weights of encoder’ states are varied according to their perceived importance. 

#### Attention model

The weighted average of this information provides the new context vector at each timestep of the decoder. This technique is called an attention mechanism which becomes the interpreter between the encoder and the decoder.

![Representation of the Attention-Based Encoder-Decoder Architecture](https://i.ibb.co/MgJsTdP/Weighted-Sum-of-all-the-Encoder-States-and-Pass-it-to-the-Decoder.gif)

$$\text{Representation of the attention-based encoder-decoder architecture.}$$
 
**Greedy search:** This method calculates the probability of the words according to their occurrence in the vocabulary. It takes the sample of the words, finds the probability of each of the words and then outputs the word with the highest probability. This makes the computational speed of the model fast, but the accuracy might not be up to the mark. 
  
**Beam search:** The alternative for greedy search is beam search. In beam search, the model finds the k most likely words instead of selecting a single word and these k words are passed onto the next timestep. It works on the breadth-first search algorithm.

**BLEU score**

-   Once you have done the prediction, the BLEU score is used as an evaluation metric for the predicted word. It determines the "difference" between the predicted sentence from the human-created sentence.