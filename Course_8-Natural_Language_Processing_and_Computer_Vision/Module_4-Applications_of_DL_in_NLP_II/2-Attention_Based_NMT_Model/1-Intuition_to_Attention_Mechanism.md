# Intuition to Attention Mechanism

In the previous session, you learnt how the traditional encoder-decoder model works and performs machine translation. The results, however, are not optimal when we have longer/multiple sentences, as the model is not able to retain information and is unable to understand the context.  
How can we tackle this problem and provide a robust system which is able to translate longer sentences?

To understand the problem better, Mohit will take you through the translation game again.

**VIDEO**

As you must have figured out, the major issue was with the way how we were procuring the context vector for the decoder. The encoder receives the source sentence and produces a single vector which is the hidden state of the last cell. This vector has to capture the entire information about the input. So, as the sentence’s length increases, it will be difficult for the encoder to capture all the information within this vector.

Therefore, the model’s performance degrades whenever it is presented with long sentences as it is not able to retain all the information and tends to forget parts of it. Therefore, it can be said that the hidden vector becomes a bottleneck for the entire NMT model. 

As you saw in the video, when you hear any sentence, you do not assign the same importance to all the words present in it. On the basis of your understanding and level of significance, you give different importance to each word. 

For example, while translating the first word of output, we usually give more importance to the first few words of the input and, similarly, the last word is usually dependent on the last few words. The degree of dependency varies as well. **For example, when translating the sentence “Pass me the pencil”, the first word depends on the first few words {“pass”, “me”}. However, the word ‘me’ was given more importance compared to the word ‘pass’.** 

  
So, while decoding each word in the decoder, we need to look at the input sentence in the encoder and assign importance to the different words of the input sentence based on the significance. This intuition leads us to an interpreter who assigns varied importance at every decoding step, helping the decoder perform a better job. But how does it shift the importance/attention at each decoding step?

Let’s understand how we can expand this intuition to the NMT architecture and solve the problem of information bottleneck using attention mechanisms in the next video.

**VIDEO**

To assign the degree of importance, the model needs all the encoder hidden states, thus providing a better context vector. As the hidden state of the decoder changes at each timestamp, the context vector changes as well. For a particular word in the decoder, information from more than one encoder’s state in the context vector can help in prediction. Hence, we take the weighted sum of all the encoder states and pass it to the decoder.

![Weighted Sum of all the Encoder States and Pass it to the Decoder](https://i.ibb.co/MgJsTdP/Weighted-Sum-of-all-the-Encoder-States-and-Pass-it-to-the-Decoder.gif)

In conclusion, in the traditional model, we used to assume that the context vector can be summarised using the last timestep of the encoder. Instead of this, all the encoder states are taken and, for each decoder state, the weights of the encoder’ states are varied according to their perceived importance. The weighted average of this information provides us with the new context vector at each timestep of the decoder and the technique used is called an attention mechanism. This becomes the interpreter between the encoder and the decoder. 

![Interpreter Between the Encoder and the Decoder](https://i.ibb.co/mhrSw7g/Interpreter-Between-the-Encoder-and-the-Decoder.gif)

The attention mechanism simulates how we humans perceive textual information. To focus on essential and ignore unwanted information, such kind of spatial understanding is the core principle of the attention mechanism. This can easily overcome the limitation of the traditional models. 

  
Now, **we will pass two inputs to the decoder RNNs** – one is the output of the previous layer and the second is the output coming from the attention model, i.e., **the context vector**. With this information, the decoder layer can perform better translation for the next word. This process is repeated with a new context vector generated at every timestep until the `<end>` token is created.

#### Attention mechanism

Qn: Select the statements which are correct w.r.t Attention mechanism (More than one option may be correct)

- The context vector in the Attention-based NMT model remains fixed in the entire training process. 

- It resolves the bottleneck problem of the NMT model.

- The attention model needs the hidden state from the decoder to understand what has been produced so far, to create the context vector.

Ans: B & C. *Since all the encoder states are used in producing the context vector, the attention resolves the bottleneck problem where the complete input sequence was captured by the last hidden state. The attention model, in order to create the context vector, needs two inputs: decoder's hidden state and encoder's hidden state.*

But how does the attention model decide which word needs to be given more importance at each decoder timestep?

Let’s understand this by looking at the inner workings of the attention mechanism.