# Comparison of GRU With Other Architectures

Let’s revise our understanding of GRU before comparing it with other architectures.

**VIDEO**

So far, we have discussed three models. In most cases, LSTM may provide better results than RNN and GRU, but there are certain trade-offs in terms of speed and feasibility. In the next video, you will learn which architecture should be used when.

**VIDEO**

Some key points from the video above are as follows:

1.  When dependencies are very small, RNN might be a good option. This is because GRU has a lesser number of parameters to train.
2.  If you want better results for longer dependency and have a requirement of training time, then GRU will be a good option.
3.  When dependencies are longer and training speed is not a bottleneck, LSTM is a decent choice.

Note that if the data set is small and dependencies are longer, GRU may even outperform LSTM, as LSTM requires more data for training and is harder to train than GRU. Otherwise, a tuned LSTM model will almost always outperform RNN and GRU.

#### Faster Inference

Qn: Suppose you want to build a model for machine translation. You want good enough results but also want the model to train faster. Which of the following models would you choose in this case?

RNN

LSTM

GRU

CNN

Ans: C. *GRU’s performance is comparable with LSTM, and GRU is faster than LSTM in terms of training time. Therefore, you should use GRU in this case.*

This marks an end of the theoretical concepts covered in this session. You will revise a summary of this session in the next segment before proceeding to solve graded questions.