# Training of RNN

Until now, you have seen the basic architecture of a simple RNN. You have also learnt how the architectures vary basis the different types of use cases and even calculated the number of trainable parameters. . But how does training of these parameters happen? How does the model learn? Let’s find answers to these questions in the next video.

**VIDEO**

So, you learnt that RNNs are trained in parts which is basically sequence length of the training sequences. For example, suppose you are training a model for POS tagging with sequence length of 8. Then, in the first training iteration, words 1-8 will be given as input and, similarly, in the second training iteration, words 9-16 will be given as input. This is a parameter which can be decided by experimenting with its values for best results.

For each iteration of training, the loss will be computed, backpropagated and subsequently the weights will be updates. Let’s have a quick revision of the training process in the next video.

**VIDEO**

So, you learnt what a training cycle looks like. You also learnt that the objective of the loss function is to optimise the model’s weights and bias parameters. You may use different types of loss function depending on the use case at hand.

Now, let’s revisit some finer aspects related to backpropagation before we go through the specific training process of RNNs.

**VIDEO**

The sole objective of backpropagation is to find the gradients so that we can minimise the loss and update the weights and biases to achieve that. You also saw a few factors which we should keep in mind to determine the training time for the model. Some of these factors are the maximum number of training loops (epochs), the change in the delta of the loss function.

#### Many-to-One RNN Training

Qn: Which hidden state can we consider if we want to use RNN for a many-to-one use case?

- At the last time step

- At all of the time steps

- None of the above

- Both a and b

Ans: D. *Both a and b are correct because you can either consider the last hidden state or consider all of the hidden states at once to make predictions.*

#### Prediction

Qn: Suppose you are building a many-to-one RNN. For a regression task (output can be any non-negative integer), which of the following equations best represent the output?

- $\hat{y_t}=softmax(W_Oh_t)$

- $\hat{y_t}=sigmoid(W_Oh_t)$

- $\hat{y_t}=softmax(W_Ox_t)$

- $\hat{y_t}=ReLU(W_Oh_t)$

Ans: D.

You will learn more about backpropagation in later segments.