# Graded Questions

All the best!

#### LSTM

Qn: Which of the following is not a feature of an LSTM **cell**?

- Gating mechanism

- The ability to replace an entire RNN layer   

- Additional cell state

- All of the above

Ans: B. *An LSTM is similar to an RNN layer, except the fact that RNN cells are replaced with LSTM cells. Hence a LSTM cell cannot replace the whole layer/ unit.*

Qn: Which of the following are present in the input gate of an LSTM cell?

- Two sigmoid functions

- Two tanh functions and one sigmoid function

- Two sigmoid functions and one tanh function

- A sigmoid function and a tanh function

Ans: D. *The update gate in an LSTM cell has one sigmoid function and one tanh function.*

#### RNN and LSTM

Qn: Which of the following statements is incorrect?

- An LSTM cell has more parameters than a vanilla RNN cell.

- You can build a network with multiple LSTM layers.

- You can build bidirectional RNNs only in the case of online sequence processing tasks.

- Only the forget gate and the input gate are the 2 gates responsible for the new cell state $C_t$ of a cell in an LSTM cell.

Ans: C. *Bidirectional RNNs can only be built in the case of offline sequences where the sequences are already available.*

#### RNN

Qn: When should you use a plain RNN?

- When dependencies are very long

- When we want to train a model faster and dependencies are smaller

- When we have independent data

- All of the above

Ans: B. *RNNs can be used effectively when you want to train a model faster for smaller dependencies.*
