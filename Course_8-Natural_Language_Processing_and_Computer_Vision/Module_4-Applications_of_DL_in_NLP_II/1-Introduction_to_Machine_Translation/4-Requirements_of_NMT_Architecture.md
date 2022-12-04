# Requirements of NMT Architecture

To produce an efficient translation, the architecture should be robust enough to handle the variable length of the input sentence and the output sentence. It should be able to understand the subject, object and action present in the sentence to produce the best translation. Let’s understand what conditions an efficient NMT model is able to satisfy. 

**VIDEO**

A good NMT model should have the following characteristics to produce a good translation for an input sentence:

-   **It should handle sequences of variable length**: The output of the NMT model should not be dependent on the input length such that any length input can be passed in and any length output can be generated. 
-   **It should be able to maintain the correct information**: While providing translation, the decoder should maintain the syntactic as well as the semantic information as stated in the input sequence, else the meaning may change entirely.
-   **It should share parameters across the sequences**: To train the entire seq2seq model, all the parameters should be shared such that during the backpropagation, both the encoder and the decoder could be trained simultaneously. 
-   **It should track long-term dependencies**: It should be able to remember information over long time periods.

However, the vanilla RNN model does not meet all the aforementioned requirements. When we pass long sentences to the RNN, it is not able to remember all the required information and tends to forget some parts. In the next video, Mohit will focus on the drawbacks of a vanilla RNN and how LSTM plays a key role in mitigating those drawbacks.

**VIDEO**

![Long-term dependency](https://i.ibb.co/1Mc1mT7/Long-Term-Dependency.png)

If you carefully observe the given sentence, you will notice how the word ‘planet’ and ‘aliens’ stated at the very beginning of the sentence influences the word ‘earth’ and ‘extra-terrestrials’, respectively, which may come at the very end. Therefore, for a word that appears at the end of a long sentence and to be dependent by a word placed at the beginning of the sentence is called long-term dependency.
  
In the previous module of RNN, we had discussed the problem of **vanishing and exploding gradients** that RNNs face and how different variants of RNN solve it. Let’s revisit this problem to see how the NMT architecture can be improved.

-   To solve the vanishing gradients problem, many attempts have been made to tweak vanilla RNNs such that the gradients do not die when sequences get long. The most popular and successful of these attempts has been the long, short-term memory network, or the LSTM. LSTMs have proven to be so effective that they have almost replaced vanilla RNNs.
-   With the introduction of different **gating mechanisms and explicit memory**, the LSTM memory can be updated or deleted such that only the relevant part of the information is kept at all times. This mechanism **controls the problem of exploding/vanishing gradients** and, thus, helps in capturing/retaining information about long-term dependencies.

![LSTM architecture](https://i.ibb.co/r0bzCMr/LSTMArchitecture.png)

LSTM architecture

**Gated recurrent unit (GRU**), considered as a variation of LSTM, produces equally good results. GRUs by design and training are simpler than LSTM as they also have only two gates compared to its counterpart. This makes it computationally faster as well  and can therefore be used to build bigger models. 

  
In the scope of this module, we will be using the GRU model as part of our neural machine translation model. 

#### Requirements of NMT system

Qn: What should be the necessary features for a good translation system?

- It should handle sentences of variable length.

- The order of input information should be maintained correctly.

- Both encoder and decoder should share parameters for efficient training. 

Ans: All of the above. *There should be no linkage to the length of the input and the output such that any length input can be passed in and any length output can be generated. While providing translation, the decoder should maintain the syntactic as well as the semantic information as stated in the input sequence, else the meaning may change entirely. To train the entire seq2seq model, all the parameters should be shared such that during the backpropagation, both the encoder and the decoder could be trained simultaneously.*

#### LSTM

Qn: Which gate in LSTM controls how much information needs to be passed on to the next LSTM cell based on the current cell state.  

- Forget

- Input

- Reset

- Output

Ans: D. *The output gate determines what the next hidden state should be. Therefore it controls how much information needs to be passed on to the next LSTM cell based on the current cell state.*

Now that you have a basic understanding of what the constraints are and how LSTMs can solve most of the problems, let’s take a deep dive into how to train the NMT model in the next segment.