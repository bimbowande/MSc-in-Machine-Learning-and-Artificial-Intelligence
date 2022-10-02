# Graded Questions

#### Sentiment Classifier

Qn: Suppose you are building a sentiment classifier based on users’ reviews on a product. The model is expected to predict a numeric ‘sentiment score’ for each review. Which of the following RNN architectures will be most suitable for this kind of problem?

- One-to-many architecture

- Many-to-one architecture

- Encoder-decoder architecture

- Standard many-to-many

Ans: B. *The input, a review, is a sequence of words and the output, the sentiment label, is a single entity. Hence, this architecture will be most suitable in this case.*

#### Sequence

Qn" The basic characteristic of a 'sequential data set/problem' which is absent in non-sequence problems is that: (Choose the option that captures the essence of a 'sequence')

- A sequence contains multiple elements which are fed to the network one by one, not all together.

- The elements of a sequence can be reordered without affecting the sequence.

- There is significant dependence between the elements of a sequence and the order of the elements is important.

Ans: C. *The main idea is that of dependence and order – in a sequence, each element depends on the previous one and so on.*

#### Basic Idea of RNN

Qn: The most crucial idea of RNNs which makes them suitable for sequence problems is that: (Please select the best answer)

- There are two sets of weight matrices WF and WR which increases the 'learning capacity' of the network.

- The state of the network updates itself as it sees new elements in the sequence.

- They can take sequences as inputs which normal neural nets cannot do.

Ans: B. *This is the core idea of an RNN – it updates what it has learnt as it sees new inputs in the sequence. The 'next state' is influenced by the previous one, and so it can learn the dependence between the subsequent states which is a characteristic of sequence problems.*

#### Architecture of an RNN

Qn: The 'depth' of an RNN refers to:

- The number of time-steps of the input sequence

- The number of layers in the RNN

Ans: B. *Depth refers to the number of layers, not time steps.*

#### RNN

Qn: Which of the following is true about the state of an RNN?

- The state changes only after the RNN consumes the entire sequence.

- The state changes each time after the RNN consumes an element of the sequence.

- A and B both will result in the same state. So, it does not matter.

Ans: B. *The state of the RNN changes after it consumes each entity of the sequence.*
