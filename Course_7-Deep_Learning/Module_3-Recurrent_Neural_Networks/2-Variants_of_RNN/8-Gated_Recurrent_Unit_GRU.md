# Gated Recurrent Unit (GRU)

In the previous segments, you have learnt about one of the variations of RNNs which is LSTM. Let’s watch the next video as the Professor introduces another variation of RNNs, GRU (gated recurrent units).

**VIDEO**

Sometimes, you may need a lighter architecture. Considering the computational expense and the problem of overfitting, researchers have tried to come up with alternative structures to the LSTM cell.

The most popular alternative is the gated recurrent unit (GRU), which was introduced in late 2014 by Kyunghyun Cho et al.

Let’s watch the next video to learn about the architecture of GRU.

**VIDEO**

Like LSTM, GRU also has gates, but there is no external memory like cell state in the GRU architecture. GRU has two gates: the reset gate and the update gate.

Let’s watch the next video to understand how the reset gate works in GRU.

**VIDEO**

The functionality of the reset gate is to decide the influence of the previous hidden state on the update of the current hidden state in combination with the current input.

Let’s  watch the next video to understand how the update gate functions in GRU.

**VIDEO**

The functionality of the update gate is similar to that of the input gate in LSTM in terms of updating the memory with both the current information and any relevant past information.

The major characteristics of the gating mechanism of GRU is that the gates (reset and update) operate on the hidden state, and not on the cell state, which is not even present in GRU. This makes the GRU model lighter than the LSTM model.

The diagram given below represents the GRU architecture.

![GRU Architecture](https://i.ibb.co/BrRKDWb/GRU-Architecture.png)

The feedforward equations are as follows, which summarises the gating mechanism of GRU:

![Gating Mechanism of GRU Equations](https://i.ibb.co/MC2fwGL/Gating-Mechanism-of-GRU-Equations.png)

It is quite evident that the first equation belongs to the update gate (notice that it has a sigmoid layer), then we have reset gate in the second expression. The last two lines correspond to the hidden state update process as per the reset gate and update gate output.

You can easily observe that in GRU, one less gate than LSTM results in fewer sets of weights, $W_z$, $W_r$, $W_h$, and each of these weights contain two types of weights, $W_F$ and $W_R$.

There are only three sets of weights in GRU, whereas in RNN, you have just one set of weights. Therefore, the number of parameters in GRU will be three times that in RNN.

While backpropagating through the hidden state, you can observe that ht is a summation function. Therefore, the values might get smaller, but the summation operator will ensure that we have a significant value of gradients even for longer dependencies.

In practice, LSTMs and GRUs have replaced the standard RNNs most of the time because they are more effective and faster to train than vanilla RNNs (despite the larger number of parameters). In most sequence problems, the problem of vanishing gradient is far more severe than training time, which explains the more common use of advanced architectures such as GRU and LSTM.

#### GRU

Qn: GRU is a light model because \_\_\_\_\_.

- Cell state is not present

- Hidden state is not present

- Only one gate is used

- Only two gates are used

Ans: A & D. *There is no cell state in GRU and GRU has only two gates.*

Qn: GRU has the reset gate to control the \_\_\_\_\_.

- Influence of past inputs coming into the architecture

- To reset the weights of the GRU cell

- To reset the only the bias value

- None of the above

Ans: A. *Reset gate in GRU regulates the past information coming from the previous hidden state which is dependent upon past inputs.*

Qn: GRU has another gate called update gate, what does it update?

- The weights of update gate

- The previous hidden state

- The weights of the reset gate

- The cell state of GRU

Ans: B. *Reset gate updates the previous hidden state with the current input information and any relevant past information. This results in a new updated hidden state.*

Having learnt about the overview of GRU architecture, you will get to know how it compares to its counterpart LSTM architecture in terms of training parameters, complexity etc in the next segment.