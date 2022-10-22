# Architecture of RNN - II

Until now, you have an overview of the RNN architecture. You also saw an example of POS tagger that requires sequential understanding to make predictions and why RNNs are suitable for these kinds of tasks. Now let’s zoom into the RNN architecture to find out what goes inside an RNN unit, the red box.

**VIDEO**

So, you saw that an RNN cell is just a single input/output model whereas an RNN unit consists of many iterations of an RNN cell and hence returns sequences as well. Refer to the below diagram where an RNN cell is repeated at each time step and as a whole can be called RNN unit.

![RNN Unit](https://i.ibb.co/CVD5t5c/RNN-Unit.png)

Now if you take a snapshot of just one of the time steps (right figure in the above diagram at t=0), you will get an RNN cell, where the input and output are just a single entity. Whereas the left figure in the above diagram as a whole represents the RNN unit having a sequence of inputs and sequence of outputs.

In order to understand this even better, you may compare these with classes and objects of OOPS concept. Just like objects are an instance of classes, the RNN cell is an instance of an RNN unit. However you don’t need to worry about it much as you can use it interchangeably most of the time.

You also learnt that RNNs have two sets of weights – recurrent and feed forward – unlike plain ANNs. The recurrent weight is associated with the hidden state input coming from the previous time step, ht−1 whereas feedforward weight regulates the input at current timestep, xt.

#### RNN Cell vs RNN Unit

Qn: Which of the following are true?

- RNN cell is provided with just one external input and gives just one output

- RNN cell can be shown as instances of RNN unit at each time step

- RNN unit receives multiple inputs (sequence) and gives multiple outputs (sequence)

- RNN unit is a iterated version of RNN cell

Ans: All of the above.

- *The RNN cell receives just one input and gives one output. Although this input and output can be multi dimensional as well.*

- *RNN cells can be shown as a snapshot of the RNN unit at each time step.*

- *The RNN unit receives a sequence as input and also outputs a sequence.*

- *RNN unit simulates the RNN cell over an iteration or a for loop.*

Let’s now learn about the equations governing the feed forward pass in an RNN in the next video.

**VIDEO**

The following figure shows a vanilla RNN architecture:

![Vanilla RNN Architecture](https://i.ibb.co/Wy5nzFK/Vanilla-RNN-Architecture.png)

In a vanilla RNN, we get the new hidden state by passing two inputs through activation – the previous hidden state (ht−1) and the current input (xt). Note that initially, an arbitrary initial hidden state is supplied. At each time step, you get a new hidden state ht, which you can use further with activation to make predictions at time t. You will learn more about it in the next few segments.

The feedforward equation for a vanilla RNN can be formulated as follows:
$$\large{h_t=tanh(W_Fx_t+W_Rh_{t−1}+b_l)}$$
Note that in the above SimpleRNN, we have considered a single value xt and also only a single RNN unit in the hidden layer. Well, this might not always be the case. You can have a vector of inputs and more than one unit in the hidden layer. You need not worry about how this changes the structure and the equations now as we’ll learn about this in the future segments.

As you know, ANNs and CNNs have multiple layers in the architecture. Similarly, RNNs can also have multiple layers which we call deep RNN. Let’s have a look at the rolled representation of a deep RNN architecture.

![Rolled Deep RNN Architecture](https://i.ibb.co/WtxT5WP/Rolled-Deep-RNN-Architecture.png)

Here, multiple RNN layers are stacked on top of each other with a dense connection and a single red box denotes an RNN layer. Each cell in layer l (refer to the RNN cell highlighted in yellow in the above diagram) gets the input from two directions – hidden state/activations of the previous layer at the current timestep $h^{l-1}_t$ and hidden state/activations of the current layer from the previous timestep $h^l_{t-1}$.

![Unrolled Deep RNN Architecture](https://i.ibb.co/gMzNm6z/Unrolled-Deep-RNN-Architecture.png)

Similarly, the activations (outputs from each layer $l$, $h^l_t$) go in two directions – towards the next layer at the current timestep (through $W_F$) and towards the next time step in the same layer (through $W_R$). Both of the outputs are denoted as $h^l_t$. Note that the subscript denotes the time step and the superscript denotes the layer number.

For a deep RNN having multiple layers:
$$\large{h^l_t=tanh(W^l_Fx^{l-1}_t+W^l_Rh^l_{t−1}+b_l)}$$

You saw that at each timestep, the hidden layer is output from the RNN cell. However, you might need to add another layer just to get output in a particular format. For example, you will need a classification layer (which is not an RNN layer) that takes the output of the RNN layer for classification tasks. You will learn about it in the next segment.

#### RNN Architecture

Qn: Which of the following acts as an input to the multilayer (deep) RNN?   
(Note that the subscript denotes the time step and the superscript denotes the layer number)

- $h^{l−1}_t$ and $h^l_{t−1}$

- $h^{l−1}_t$ and $h^{l-1}_{t−1}$

- $h^l_t$ and $h^{l-1}_{t−1}$

- $h^l_t$ and $h^{l-1}_t$

Ans: A. *RNN receives two inputs - hidden state/activations of previous layer at current time step and hidden state/activations of current layer from previous time step.*

Qn: How does the previous hidden state ($h_{t-1}$) and current input ($x_t$) combine to form the RNN input?

- Summed up directly

- Multiplied with a common weight and then summed up

- Multiplied with their respective weights and then summed up

- Multiplied with each other

Ans: C. *Each of the inputs of RNN, hidden state from previous time step and current input have their own dedicated weights. Hence they get multiplied with their own weights and then summed up to form the input.*

Qn: Which of the following can be the input or output dimension of RNN?

- A single numeric value

- A vector of numeric values

- A multidimensional matrix

- All of the above

Ans: D. *RNN input and output can assume any shape be it a single value or a vector or multidimensional array.*

#### Feed Forward Expression

Qn: Which of the following is the right formula to get the new hidden state from the old one? (Consider that $W_F$ is the feed forward weight and $W_R$ is the recurrent weight)

- $f_w(W_F∗x_t+W_R∗h_t)$

- $f_w(W_R∗x_t+W_F∗h_{t-1})$

- $f_w(W_F∗x_{t-1}+W_R∗h_{t-1})$

- $f_w(W_F∗x_t+W_R∗h_{t-1})$

Ans: D. *The overall input with forward weight $W_F$ will be current input at time $t$, $x_t$ and old hidden state $h_{t−1}$ with recurrent weights $W_R$.*
