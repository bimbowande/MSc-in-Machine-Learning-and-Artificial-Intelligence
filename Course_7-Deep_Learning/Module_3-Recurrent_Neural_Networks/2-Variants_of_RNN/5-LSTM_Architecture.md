# LSTM Architecture

In the previous segment, you understood how the gating mechanism works in tandem with the help of an unrolled LSTM architecture. In this section, you will get a more detailed understanding of the LSTM architecture. First, let’s understand how individual gates function mathematically in the next video.

**VIDEO**

Each gate has a separate set of weight and bias, as you saw with the forget and input gates. With the help of an example, you learnt how these two gates work on sentences to remember or forget words, which enhances the effectiveness of LSTMs.

Let’s watch the next video to learn how the cell state is modified and how the output gate makes predictions.

**VIDEO**

The cell state gets modified by the forget and input gates, which essentially is a function of the current input. The output gate considers each piece of information available in the cell (cell state, hidden state and current input) to make predictions.

### Cell state  
The new cell state $c_t$ is the cumulative result of the information discarded from $C_{t−1}$ by the forget gate and the new information freshly updated to $C_{t−1}$ by the update gate.

### Output gate
This gate controls how much information needs to be passed on to the next LSTM layer based on the current cell state.

  
A more detailed view of the LSTM architecture is represented in the diagram given below.

![LSTM Architecture](https://i.ibb.co/nr1n5hj/LSTM-Architecture.png)

  
To summarise, an LSTM cell is analogous to an RNN unit, and each LSTM layer contains multiple LSTM cells. The cell receives the following inputs:

1.  The output of the previous time step $h_{t−1}$
2.  The current input  $x_t$
3.  The previous cell state $C_{t−1}$

The cell produces the following two outputs:

1.  The current cell state $C_t$
2.  The current state output $h_t$

  
The formulas that drive the gate functionalities of the LSTM architecture as feedforward equations are as follows:

![LSTM Architecture Equations](https://i.ibb.co/c8gNPMY/LSTM-Architecture-Equations.png)

In the set of equations given above, the first one is a part of the forget gate, the second and third equations depict the functionality of the input gate, and the last two equations represent the output gate. The third-last equation denotes the cell state update at time step ‘$t$’.

### Dimensions involved in LSTM
Before moving onto the training of LSTM models, you also need to understand the dimensions of various elements involved in LSTM architecture. Suppose you have an LSTM cell where input (xt) dimensions are 80x1 (80 features) and output ($o_t$) dimensions are 12x1 (12 classes).

Now if the output dimension is 12x1, the hidden state will also have the same dimension 12x1 since output dimensions are directly corresponding to the hidden state. Similarly Ct will also have dimensions (12x1). Further because of element wise multiplication all around both ft and it will be of 12x1 dimension.

Now $W_{fF}$ will also be of dimension (12 x 80) so that it can be multiplied with $x_t$ and $W_{fR}$ will be of dimension (12 x 12) to get multiplied with $h_t$. Similarly all the forward weights will be of dimension (12x80) and all the recurrent weights will be of dimension (12x12). Whereas all the biases will be of dimension (12x1) since they are directly related to $f_t$, $i_t$, $C_t$, ht and ot all having the same dimensions.

Also note that these dimensions will be true for every time step, hence the time step doesn’t have any impact on the dimensions.

#### Gating Mechanism in LSTM

Qn: What is the rationale behind using a tanh function and a sigmoid function in the input gate?

- The gradients flow much more easily while backpropagating.

- A combination of tanh and sigmoid is always better than two sigmoid functions.

- The sigmoid function decides how much information to write to the new cell state, while the tanh function decides whether to increase or decrease the value of the next cell state.

- A combination of tanh and sigmoid is always better than two tanh functions.

Ans: C. *Using a tanh function and a sigmoid function allows you to make an update more effectively.*

Qn: The output gate contains a sigmoid function and a tanh function. Which of the following statements is correct about the output gate? (Note: More than one option may be correct.)

- Higher value of sigmoid will mean that higher amount of information will transmit to the next hidden state.

- Higher value of sigmoid will mean that lesser amount of information will transmit to the next hidden state.

- When tanh is positive, the value of the next hidden state is increased.

- When tanh is positive, the value of the next hidden state is decreased.

Ans: A & C. *The sigmoid function is applied on $h_{t-1}$ and is then multiplied with $tanh(C_t)$. Higher value of the sigmoid function will mean that higher amount of information is transmitted to $h_t$. When tanh is positive, $h_t$ is increased from its current value.*

#### LSTM Gates

Qn: In a standard LSTM architecture what can be the output of the forget gate?

- 2

- 200

- 20

- 0.2

Ans: C. *Forget gate will always output values between 0 and 1 as sigmoid activation function is used. This is valid for all the gates as they all have sigmoid activation.*

Qn: Which of the statements is true about the outputs of the gates in LSTM?

- All the outputs of the gates will be same as all the gates take the same inputs - current input xt and previous hidden state ht−1

- All the outputs of the gates will be different because of different weights and biases used

- All the outputs of the gates will be same as each gate will use same set of weights

- None of the above

Ans: B. *Even if the inputs are the same for every gate in LSTM but they have different sets of weights hence their output will always be different.*

#### LSTM Dimensions

Qn: For a LSTM network with input of dimension (20x1) and output of dimension (50x1), what will be the dimensions of the previous hidden state (ht−1)?

- 50x50

- 50x1

- 1x50

- 1x1

Ans: B. *Hidden state will have similar dimensions as the output hence 50x1 is the correct answer.*

Qn: For a LSTM network with input of dimension (20x1) and output of dimension (50x1), what will be the dimensions of the feed-forward weights of forget and input gate respectively?

- 50x20, 50x20

- 50x50, 20x20

- 20x50, 20x50

- 50x20, 20x50

Ans: A. *All the feed-forward weights will be of the same dimension 50x20, kindly refer to the example given in the segment.*

You have now understood the architecture of LSTM and how it combines gates and cell state. In the next segment, you will learn that this architecture consists of more parameters than simple RNN which is the reason for its superior performance.