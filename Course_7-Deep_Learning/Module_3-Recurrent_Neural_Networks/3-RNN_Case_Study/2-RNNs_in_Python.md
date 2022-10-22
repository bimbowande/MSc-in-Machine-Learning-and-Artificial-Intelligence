# RNNs in Python

Before moving to the case study implementation, you will learn to implement various types of RNNs in this segment. You may refer to the below colab notebook for the reference of model building of RNNs. Kindly feel free to change the parameters and put additional layers.

Download [Python implementation of RNNs](RNNs_in_Python.ipynb)

Below are the key highlights of the notebook.

1.  SimpleRNN, LSTM, GRU are layers just like dense layers in Keras API.
2.  The Vanilla RNN model will contain just one RNN layer.
3.  When we have return_sequences=False, which is also a default value, the RNN layer will return all the outputs simultaneously at the last time step, therefore ensuring the one output for many-to-one output.
4.  The many output can be achieved by
5.  Using return_sequences=True for RNN layer to get outputs at each time step.
6.  Using a TimeDistributed wrapper layer around the dense layer to access the RNN outputs at each time step separately.
7.  The many-to-many odd length RNN model will use two RNN models:
8.  As an encoder to receive the inputs at each time step and then output at the last.
9.  As a decoder to receive the inputs initially and then decode it to the output at various time steps further.
10.  To implement the GRU or LSTM model, you just need to replace the “SimpleRNN” with “GRU” or “LSTM”.

#### Return Sequence

Qn: Where do we use `return_sequences=True`?

- To return the full output sequence of all the time steps

- To return all the input sequences

- To build RNN models such as many-to-many and one-to-many where we need outputs at each time step

- To connect two RNN layers for using multilayer RNN models

Ans: A, C & D. 

- *`return_sequence=True` is used for taking RNN output at each time step whereas False value will let it return only the last output.*

- *You will need to use `return_sequences=True` for many output type RNNs as output is needed at each time step.*

- *`return_sequences=True` returns all the outputs rather than just the last time step hence the next RNN layer can easily fit input format at each time step.*

#### Time Distributed Layer

Qn: Why do you need to use dense layers with time distributed layer wrapper for many output type RNNs instead of just a plain dense layer?

- Time distributed layer ensures that RNN output at each time step is treated separately by the dense layer.

- Time distributed layer facilitates the backpropagation through time (BPTT) in dense layers.

- Time distributed layer changes the dense layer activations  at each time step

- Time distributed layer gets the time distributed input from the dense layer.

Ans: A. *Time distributed layer ensures that RNN output at each time step is treated separately by the dense layer. Suppose you want to build a POS tagger then you will need to output the classes for the input words at each time step, hence the dense layer should be active at each time step which is facilitated by the time distributed layer.*

#### Number of parameters

Qn: Build an RNN model with 10 time steps where the number of input features is 10, 2 hidden RNN layers with 15 units each and an output dense layer with 5 nodes. Which of the following will be the number of parameters according to `model.summary()`?

- For many-to-one RNN model, # parameters = 939 and for many-to-many RNN model, # parameters = 919

- Both many-to-one as well as many-to-one RNN will have # parameters = 935.

- For many-to-one RNN model, # parameters = 919 and for many-to-many RNN model, # parameters = 939

- None of the above

Ans: B. *Both many-to-one as well as many-to-many RNN will have the same number of parameters as only the number of time step outputs changes but the connections remain the same. Refer to the notebook for more details.*

Qn: Build an RNN model where the number of input features is 6, 3 hidden RNN layers with 10 units each and an output dense layer with 4 nodes. Which of the following will be the number of parameters according to `model.summary()`?

- For 10 time steps # parameters = 674 and for 10 time steps # parameters = 634

- For 10 time steps # parameters = 634 and for 10 time steps # parameters = 674

- Both RNN models with 10 and 20 time steps will have same # parameters = 634.

- None of the above

Ans: C. *Number of time steps doesn’t change the number of parameters as the same RNN cell will be used across time steps.*
