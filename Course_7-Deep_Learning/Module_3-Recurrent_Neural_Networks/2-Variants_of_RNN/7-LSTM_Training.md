# LSTM Training

We may want a model to perform well but until we train it, we cannot say much about its performance. In this segment, you will learn how to train LSTM models.

Let’s hear from Professor Mouli as he elaborates on this.

**VIDEO**

As you learnt in the video above, error calculation is similar to RNN error calculation. However, while training a model, the number of parameters of the model increases by  four times, thereby increasing the complexity of training an LSTM model.

In LSTM, you need to add a classification layer to make predictions on top of hidden state output (ht) which was also stated as Ot in the video. For example, in the case of many-to-one classification problems, you will need to add a classification layer on top of the hidden state output. All these steps can be formulated into expressions given below.

![LSTM Training Equation](https://i.ibb.co/S3dPMSV/LSTM-Training-Equation.png)

Now , the real training happens through the backpropagation of error gradients.

There are four sets of weights in LSTM, each corresponding to gates and cell state: Wf, Wi, Wo and Wc. Each cell has its own WF and WR, hence upscaling the number of parameters to four times that in RNN. The increased number of parameters leads to increased computational costs. For the same reason, LSTM is more likely to overfit the training data than a normal RNN.

Having said that, most real-life sequence problems such as speech recognition, translation, and video processing are complex enough to need LSTMs.

At the time of gradient calculation, the gradients depend on the derivation of Ct, which is a summation function. Therefore, however small the values become, they will have an addition (the plus sign while updating Ct) operation rather than a recursive multiplication, thus overcoming the vanishing gradient problem.

#### Backpropagation in LSTM

Qn: While backpropagating, which of the following gates will not involve gradient calculation?

- Forget gate

- Input gate

- Output gate

- Gradients will flow through all gates.

Ans: D. *Each gate provides a way for the flow of gradients. However, the flow is maximum through the connection between $C_{t−1}$ and $C_t$ and minimal through the gates.*

In the next segment, you will learn about the training parameters in LSTM, which makes its architecture complex.