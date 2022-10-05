# LSTM Architecture: Gates and Memory

Gates and the cell state are the integral components that make LSTM effective. In the previous segment, you learnt about the functionalities they perform. But how do these components perform their respective functionalities? Let’s find that out in this segment.

Before we dive deeper into an LSTM cell, let’s understand what a gate is. A gate is a sigmoid layer followed by pointwise or element wise multiplication. Therefore, a gate outputs values between 0 and 1 and thus regulates the information flow. The diagram below depicts a gate.

![LSTM Gate](https://i.ibb.co/85YV6yn/LSTM-Gate.png)

There are few other terminologies related to a gate, as mentioned below.

![LSTM Terminologies](https://i.ibb.co/xj4NYh8/LSTM-Terminologies.png)

  
Note that pointwise multiplication is also called element-wise multiplication.

Now, you are better equipped to understand the architecture of LSTM. The entire LSTM architecture can be broken down into various parts consisting of gates and cell state. Let’s hear from Professor Mouli as he elaborates on this.

**VIDEO**

NOTE: The multiple input and output LSTM part that Porf mentioned in the video, will be covered in later segments.

In the video above, you learnt about the functionalities  of the forget and input gates and the cell state with the help of an example. You also saw how these components combine with each other to account for a lot more effectiveness to capture longer dependency than a simple RNN.

Let’s understand the intuition of each gate with a specific example. Suppose you are working on a video tagging problem where you need to tag the action that takes place in each frame of the video. Let’s take a look at the function of each gate in the context of this problem.

### Forget gate
This gate controls how much information needs to be discarded from the previous cell state (Ct−1) depending on the new input. In the video tagging problem, whenever a new action takes place, this gate needs to decide how much information to retain from the previous frames. If the same action is happening repeatedly, then a very small amount of information should be discarded. When the action changes, the forget gate 'forgets' a considerable amount of information.

### Input gate
This gate updates the previous cell state  by writing a new piece of information to it. In the video tagging problem, when the action changes, this gate updates the cell state with the information that is relevant to the new action. In case the action is the same as the previous frame, negligible information is written to the cell state. If the scene changes drastically, the update will also be drastic.

Let’s watch the next video to learn about the working  of the output gate and cell state.

**VIDEO**

You learnt that LSTM has two types of memory - short-term memory $(h_t)$ and long-term memory $(C_t)$. Hence to make effective predictions through the output gate, LSTM uses both short-term information $(h_{t−1})$ as well as long-term information $(C_t)$. The output ht is further treated as an updated short-term information. Did you notice that here $\hat{y_t}$ is not the same as $h_t$ since we are having an additional sigmoid layer?

#### LSTM

Qn: Which of the following statements is correct about the sigmoid function in the forget gate?

- Higher value of sigmoid will mean that higher amount of memory will be erased from the previous cell state.

- Higher value of sigmoid will mean that higher amount of memory will be erased from the previous hidden state.

- Higher value of sigmoid will mean that lesser amount of memory will be erased from the previous cell state.

- Higher value of sigmoid will mean that lesser amount of memory will be erased from the previous hidden state.

Ans: 

You have gotten an intuition of the gates. We'll dive deeper into the functionality and the equations in the next segment.