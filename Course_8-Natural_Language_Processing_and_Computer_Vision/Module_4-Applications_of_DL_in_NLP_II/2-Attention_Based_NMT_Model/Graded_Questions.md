# Graded Questions

The following questions are **graded**. All the best!

#### Attention model

Qn: What is/are the output of an attention model?

- Context vector

- Attention weights

- Both A and B

Ans: C. *The attention model returns both the context vector and attention weights.*

#### Attention based seq-2-seq model

Qn: Which of the following statements about the attention-based sequence to sequence model is correct? (Note: More than one option may be correct.)  

- The most important output state of the encoder is calculated and passed as the context vector to the decoder.

- All the output states of the encoder are passed and made available while decoding.

- The value of the attention score can be calculated based on multiple methods.

- All of the above

Ans: B & C. *All the output states of the encoder are passed and made available while decoding. There are multiple ways to calculate the attention score like Dot product attention, Multiplicative attention and Additive attention.*

#### Beam search

Qn: In beam search, if you increase the beam width, which of the following steps would you expect to take place?

- The search will take more time as the beam width has increased.

- The search will take less time as the beam width has increased.

- The quality of translations would improve to certain beam width.

- All of the above.

Ans: A & C. *As the beam width increases the search time increases as well. The number of decoding instances would proportionally increase, so the processing will increase with the increased beam width. As the beam width increases the quality of the translation would improve to certain beam width.*

