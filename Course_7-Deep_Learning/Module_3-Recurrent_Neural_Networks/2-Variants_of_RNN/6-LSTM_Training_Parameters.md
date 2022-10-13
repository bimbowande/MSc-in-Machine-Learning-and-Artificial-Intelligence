# LSTM Training Parameters

Having learnt the architectural concepts regarding LSTM, you will learn to calculate the training parameters in an LSTM architecture which is quite crucial before you learn the actual training process. Let’s watch the next video to learn how to calculate the training parameters in LSTM.

**VIDEO**

As you learnt in the video above, the training parameters in LSTM have an additional multiplying factor, called the number of layers, compared to RNN. An LSTM cell has a total of four layers (one main layer + three gates), each getting two inputs: the current input data and the old hidden state. Because of this LSTM has four fold trainable parameters than a simple RNN.

Let’s watch the next video to understand what happens if we have more than one output.

**VIDEO**

As you learnt in the above video, the number of parameters increases significantly as we increase the number of outputs. But what if we also increase the number of inputs? Will it have the same effect on the number of parameters? Let’s watch the next video to find out.

**VIDEO**

You saw in the above video that increasing the number of inputs will affect only the number of input parameters. You can tweak the LSTM architecture according to your requirements.  You may have two hidden state outputs, but you can always apply a dense layer at the top to obtain the appropriate output.

#### Parameters in LSTM

Qn: Suppose you have an RNN model that has 200 training parameters. After training the model, it does not seem to perform well. So, you want to replace the RNN model with an LSTM model. How many training parameters will this model have? (Considering that no additional layers have been used).

Ans: *An LSTM layer has four times the parameters of a vanilla RNN. The number of parameters will increase from 200 to 800.*

Qn: Suppose you have an LSTM network with 3 input features, a hidden layer with 5 LSTM units and no output layer. What will be the number of recurrent parameters involved?

- 25

- 30

- 120

- 100

Ans: D. *Each LSTM unit would be connected to each LSTM unit, where total 4 sets of weights will be used hence total input parameters will be $4*5*5=100$. Additionally there will be $4*5$ bias terms as well hence the total parameter will be $100+20=120$. Refer to the videos used in the segment for the formula.*

In the next segment, you will learn about the GRU architecture, which is lighter than LSTM.