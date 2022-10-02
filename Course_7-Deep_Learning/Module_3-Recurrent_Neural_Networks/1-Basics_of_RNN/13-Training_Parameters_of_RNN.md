# Training Parameters of RNN

In the previous segment, you had a quick revision of the training process of a neural network. In this segment, you will learn how the parameters involved in training the RNN model behave differently.

**VIDEO**

In the above video, you learnt that the number of parameters while training a model depends on the number of hidden layers and the number of units in those particular layers. The weight parameters feed forward weight ($W_F$), output weight ($W_O$) and recurrent weight ($W_R$) behave differently in the feedforward and hence the training process for them will also be different. The recurrent weight, $W_R$ at time step $t$ will depend on the weight value at time step ($t-1$) and therefore, becomes a recursive calculation. On the other hand, the value of forward weights and output weights are not dependent on the value of corresponding weights values at previous times steps.

Next, let’s learn how weights and biases affect model training.

**VIDEO**

As you had seen earlier that during backpropagation, there are two different types of weights, the recurrent weights, $W_R$ and the feedforward weights (which includes the output weights as well): $W_F$, $W_O$. In the below diagram, the backpropagation is started from time step n, where the error value is $E_n$. Here, the feed-forward weights ($W_F$, $W_O$) will be updated through the yellow path, whereas recurrent weights will be updated through the backpropagation in the red path.

![Training Parameters of RNN](https://i.ibb.co/Phv69ZF/Training-Parameters-of-RNN-Image.png)

**VIDEO**

As Professor mentioned in the above video, the following two types of issues can arise in RNN while performing backpropagation:

1.  Vanishing gradient
2.  Exploding gradient

Both of the aforementioned issues occur while backpropagating along the recurrent path. The vanishing gradient problem makes the gradient so small that no weight updates happen in the model. On the other hand, the exploding gradient problems cause the gradients to explode to a very large value such that either the weights value are difficult to store or the weight updates are so huge that they mislead the model training. You will learn more about it in the next segment.

#### Weight Updates

Qn: Recurrent weights updates depend upon which of the following values in case of a multilayer RNN?

- Recurrent weights of the previous layer

- Recurrent weights of previous time step

- Neither of the above

- Both a and b

Ans: D. *Recurrent weights of a multilayer RNN will depend upon both the weights of the previous layer as well as the previous time step, as the backpropagation will be done on both of these.*

#### Vanishing Gradients

Qn: Which of the following statements is not true?

- Vanishing gradient problem occur in recurrent as well as feed forward weights

- Recurrent weights have recurring multiplication with each other which leads to more serious vanishing gradient problem

- Gradients with a value of 0.9 are most likely to vanish with just 20 words long sequence

- Gradients will never die if some of them are greater than one

Ans: D. *This statement is wrong because even if some gradient values are greater than one, other gradient values can be really low to force gradients to vanish. Hence having some gradient values greater than one doesn’t guarantee that vanishing gradient problem will not occur.*

#### Exploding Gradients

Qn: Assuming all the gradients have numerical value 10, and memory allocated is only 4 bytes to the place holder. After how many time steps the gradients will explode?

- 8

- 9

- 10

- 11

Ans: C. *The maximum value of the gradients that placeholder can keep is $2^{32}=4*24∗10^9$. When you multiply gradients 9 times, it will still be within the limits, but further multiplication will result in exploding gradients hence the correct answer would be 10.*

You saw the forward propagation involving the loss calculation in the forward path and weight updates through backpropagation. You also learnt about the recurrent weight updates being different from feed-forward weights. Next, we will discuss backpropagation in detail.