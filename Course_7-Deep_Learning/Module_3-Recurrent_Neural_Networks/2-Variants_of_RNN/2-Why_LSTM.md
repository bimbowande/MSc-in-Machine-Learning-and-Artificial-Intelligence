# Why LSTM?

The vanishing gradient problem is a serious issue in RNNs, as that causes RNNs to forget everything they have seen earlier. But what if the model can control what it wants to learn or what it wants to forget? Well, this will certainly help the model to take some of the irrelevant information away and learn only useful data. This is what GRU and LSTM try to achieve.

Before we proceed further, let’s revise the vanishing gradient problem of RNN and learn about the features incorporated into LSTM to counter this.

**VIDEO**

In the case of RNNs, the main problem is the vanishing gradient problem.

To solve the vanishing gradient problem, many attempts have been made to tweak the vanilla RNNs such that the gradients do not die when sequences get long. The most popular and successful of these attempts has been the long short-term memory network, or the LSTM.

LSTMs have proven to be so effective that they have almost replaced vanilla RNNs. The main drastic improvement that LSTMs have brought is because of a novel change in the structure of a cell itself.

An LSTM cell has a gating mechanism involving several gates along with a dedicated memory called cell state. You also saw that there are more inputs and outputs in an LSTM cell. One interesting point that Prof. mentioned is that the output $C_t$ goes to the next layer but the hidden state, $h_t$ does not. Note that we are talking about LSTM layers and not time steps within the layer. You will learn more about it in the next segment.

As LSTMs are very effective models, they are used in various ways for different purposes. Let’s watch the next video to learn more about this.

**VIDEO**

LSTMs have a diverse range of applications, and based on the type of applications, they can be changed in the way they are combined within and also with other architectures.

#### LSTM

Qn: LSTM tries to solve the \_\_\_\_\_ problem of RNN in particular.

- Exploding gradient

- Constant gradient

- Vanishing gradient

- Both a and c

Ans: D. *The LSTM architecture is designed to overcome the vanishing gradient problem of RNN. But it also solves the exploding gradient problem as you will learn in later segments.*

Having understood the importance of LSTM architecture and that it brings a plethora of applications in diverse domains, let’s learn what LSTM models look like in the next segment.