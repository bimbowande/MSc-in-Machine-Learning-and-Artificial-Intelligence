# Graded Questions

All the best!

#### Training Time

Qn: Which of the following is the correct order if you arrange RNNs according to the network training time?

- Bidirectional LSTM > GRU > LSTM > Vanilla RNN

- Bidirectional RNN > LSTM > GRU > Vanilla RNN

- GRU > Bidirectional Vanilla RNN > LSTM > Vanilla RNN

- Bidirectional LSTM > LSTM > GRU > Vanilla RNN

Ans: D. *The time it takes to train an RNN corresponds to the number of parameters present in an architecture. If a vanilla RNN has 'n' number of parameters, then the number of parameters of GRU, LSTM and bidirectional LSTM are 3n, 4n and 8n, respectively.*

#### Keras Input

Qn: Keras accepts batch dimensions of the input data in which of the following formats?

- (\#timesteps, \#samples, \#units)

- (\#samples, \#timesteps, \#units)

- (\#units, \#timesteps, \#samples)

- (\#units, \#samples, \#timesteps)

Ans: B. *Refer to the sequence generation part of the case study notebook and the segment as well.*

#### Keras Layer

Qn: In which of the following RNN types, do you **not** use a TimeDistributed() layer at the output?

- Many-to-one

- One-to-many

- Many-to-many: Input and output have equal lengths

- Many-to-many: Input and output have unequal lengths

Ans: A. *You only use a TimeDistributed() layer when the RNN outputs a sequence. Therefore, you do not use it in a many-to-one RNN model.*
