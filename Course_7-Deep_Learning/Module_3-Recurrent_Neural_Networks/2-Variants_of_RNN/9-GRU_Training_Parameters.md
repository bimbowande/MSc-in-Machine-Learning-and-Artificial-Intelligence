# GRU Training Parameters

As you have already learnt about the GRU architecture, it’s time to know about the trainable parameters involved that makes the GRU lighter architecture. Let’s get to know about it from Professor Mouli.

**VIDEO**

So you experienced the calculation of trainable parameters in GRU and in the process, found out that it’s three times that of simple RNN architecture. But when you implement it in keras API, you see that two sets of bias parameters are being used, which is just to enhance the ability of GRU architecture. Now let’s take an example again to see if it’s really the case with any GRU implementation.

**VIDEO**

Now you would be sure that it’s just the keras implementation, which takes the extra set of bias parameters for the model building.

As the training of GRU will be similar to LSTM architecture, we will not discuss that in this session. However you can go out and explore online available materials.

#### Parameters in GRU

Qn: Suppose you have an GRU network with 3 input features, a hidden layer with 5 GRU units and no output layer. What will be the number of input parameters involved? Note: You can ignore the bias term.

- 15

- 30

- 45

- 60

Ans: C. *Every input node would be connected to every GRU unit, where total 3 sets of weights will be used hence total input parameters will be $3*3*5=45$. Refer to the videos used in the segment for the formula.*

Qn: Suppose you have an GRU network with 3 input features, a hidden layer with 5 GRU units and no output layer. What will be the number of recurrent parameters involved? Note: You can ignore the bias term.

- 25

- 90

- 120

- 75

Ans: D. *Each GRU unit would be connected to each GRU unit, where total 3 sets of weights will be used hence total input parameters will be $3*5*5=75$. Refer to the videos used in the segment for the formula.*

In the next segment, you will get to know how it compares to its counterpart LSTM architecture in terms of training parameters, complexity etc in the next segment.