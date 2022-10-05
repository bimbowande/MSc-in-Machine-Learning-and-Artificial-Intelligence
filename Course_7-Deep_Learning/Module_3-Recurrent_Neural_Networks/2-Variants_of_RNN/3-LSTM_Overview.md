# LSTM Overview

LSTM is an architecture based on RNN, which is obtained by introducing the gating mechanism within the RNN. In most cases, LSTM models are preferred over RNN for achieving better results and this is possible because of the gating mechanism. But what is the gating mechanism? Let’s watch the next video to learn more about this.

**VIDEO**

One of the fundamental differences between RNN and LSTM is that LSTM has an explicit memory unit that stores information that is relevant for learning a task. In the standard RNN, the only way the network remembers past information is through updating the hidden states over time, but it does not have an explicit memory to choose and store selective information.

  
On the other hand, in LSTMs, the memory, or the cell state, retains pieces of information even when the sequences get really long, thereby working as long-term memory, $C_t$. In contrast, LSTM cells have a hidden state acting as short-term memory, $h_t$ to capture the most recent information. This is the reason why LSTM is called long short-term memory.

Let’s watch the next video to learn about the overall gating mechanism inside the LSTM cell.

**VIDEO**

You saw that there are four layers in an LSTM cell: One main layer with tanh activation and three gates with sigmoid activation. These are called layers because each of them has a separate weight and bias associated with it.

The second difference between RNN and LSTM is the introduction of a gating mechanism, which allows you to modify the cell state in certain ways. The main idea is that gating mechanisms regulate the information that the network stores in memory (and passes on to the next layer) or forgets.

You can refer to the image given below for a simplified version of the LSTM architecture.

![Simplified LSTM Architecture](https://i.ibb.co/h7NXpXs/Simplified-LSTM-Architecture.png)

The gating mechanism in LSTM consists of three gates: the forget gate, the input gate and the output gate. You can consider each of these gates as a tool that can modify the cell state. The forget gate helps the model forget irrelevant information, the input gate helps in updating the cell state as per the current input, and the output gate helps in making effective predictions.

#### Cell State

Qn: What type of operations are performed on the cell state in LSTM? (Note: More than one option may be correct.)

- Forget

- Input

- Delete

- Output

Ans: A, B & D. *The gating mechanism in LSTM involves three gates, one of which is the forget gate.*

#### LSTM Input and Output

Qn: What are the inputs and outputs of an LSTM cell? Assume that we are considering a cell in the lth layer. (Note: More than one option may be correct.)

- Input: Previous cell state $(C_{t−1})$ the output of previous time step in the current layer $(h^l_{t-1})$; the output of the previous layer at the current timestep $(h^{l−1}_t)$

- Input: Current cell state $(C_t)$ the output of previous time step in the current layer $(h^l_{t-1})$; the output of the previous layer at the current timestep $(h^{l−1}_t)$

- Output: Current cell state $(C_t)$; the output of current cell $(h^l_t)$

- Output: Current cell state $(C_t)$; the output of previous cell $(h^l_{t-1})$

Ans: A & C.

In the next segment, you will learn how the gating mechanism controls the memory flow of the cell state.