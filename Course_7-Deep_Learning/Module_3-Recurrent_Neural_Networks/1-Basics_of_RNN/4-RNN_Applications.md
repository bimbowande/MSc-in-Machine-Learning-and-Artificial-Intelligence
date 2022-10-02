# RNN Applications

RNNs are made for processing sequential data. Let's see an example which uses this “recurrent” feature of RNNs.

**VIDEO**

Now that you know why you need RNN, let's get to know some use cases which highlight the features of RNN which weren’t present in ANN and CNN as we learnt in the previous segment.

1.  Handling variable length input
2.  Taking help from past inputs to make predictions at current time step

**VIDEO**

So, there can be various sequential problems such as sentiment prediction, machine translation, speech recognition and handwriting recognition. These use cases require the sequential understanding of the input sequence to make good predictions such as to predict the sentiment of a piece of text, you will need to have a good understanding of the sequences. Similarly, there can be variable lengths of inputs and outputs such as machine translation, where the translated sequence can be of any length.

#### Sequential Problems

Qn: Which of the following problems are better suited for RNN than CNN or plain ANN?

- Laptop sales prediction

- Human activity recognition in videos

- Machine translation

- Loan prediction

Ans: A, B & C. *Sequential understanding is required to solve the problem efficiently. Hence, RNN should be the preferred choice.*

#### Sequential Problems

Qn: Which of the following problems are there while solving sequential problems with CNN or plain ANN?

- Unable to learn sequential dependencies

- Unable to process variable length of inputs

- Not considering past inputs for predicting current output

- Not considering current input for predicting current output

Ans: A, B & C.

- *Sequential understanding is required to solve the problem efficiently. Since ANN and CNN don’t relate previous inputs to current inputs they are unable to learn sequential dependencies.*

- *Both ANN and CNN cannot handle variable length inputs because they expect fixed input length at each training batch.*

- *ANN and CNN don’t consider previous inputs as only the data at the current time step is given as input hence there is no involvement of previous inputs. It prevents ANN and CNN from learning any sequential dependencies. You can refer to this video to learn more.*

In the next segment, we'll dive deeper into the architecture of RNN.