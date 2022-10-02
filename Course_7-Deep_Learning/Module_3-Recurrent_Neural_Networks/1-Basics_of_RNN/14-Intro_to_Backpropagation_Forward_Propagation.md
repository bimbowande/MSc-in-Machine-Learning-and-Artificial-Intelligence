# Intro to Backpropagation - Forward Propagation

Until now, the Artificial neural networks or the Convolution Neural Networks that you have learnt, the backpropagation happens from the last layer to the first layer. Hence, there is only one dimension along which backpropagation happens. However, in the case of RNNs, a particular layer gets inputs from the previous layer as well as the previous time step. Hence, the backpropagation happens across the time dimension as well as the layer dimension and this makes backpropagation in RNN complex.

Since the backpropagation is also done through the time domain, it is called backpropagation through time (BPTT). In the below diagram, the path along which BPTT happens is highlighted in red.

![BPTT](https://i.ibb.co/K2Xyhm7/BPTT.png)

Let’s start by revisiting the forward propagation of the many-to-one RNN model.

**VIDEO**

As the architecture of the RNN model changes from many-to-one to many-to-many, the forward propagation also changes in some way. Let’s hear about it from the professor.

**VIDEO**

Apart from the forward propagation of the many-to-one RNN model, you also learnt that you sum up the errors occurring at each time step with this particular type of RNN where you have one output at each time step.

Now, let’s learn about the backpropagation overview to understand what actually happens under the hood.

**VIDEO**

So, you saw that just like backpropagation is done in the feedforward path, the same follows in recurrent path as well. We can summarise the backpropagation with the below diagram where backpropagation in the feed-forward path is highlighted in yellow and backpropagation in recurrent path is highlighted in red.

![Backpropagation in the Feed-Forward Path](https://i.ibb.co/HqMxyM3/Backpropagation-in-the-Feed-Forward-Path.png)

The backpropagation along the feed-forward path is done to update the feed-forward weights $W_F/W_O$, hence the gradient is also calculated with respect to these weights. Similarly, the recurrent weight is updated through the backpropagation on the recurrent path.

Eventually, we get the following expression for gradients against the recurrent weight $W_R$ for two backpropagation steps, which is crucial for our understanding.
$$\large{\dfrac{\delta\\E}{\delta\\W_R}=\dfrac{\delta\\E}{\delta\\z_t}\left[h_{t−1}+W_R*tanh'(z_{t−1})*h_{t−2}+W^2_R*tanh'\left(z_{t−1}*\dfrac{\delta\\h_{t-2}}{\delta\\W_R}\right)\right]}$$
Here,  $z_t=W_R*h_{t−1}+W_F*x_t+b$ which is the cumulative input to the tanh activation.

Note that the above equation is the derivation for calculating the gradient for the weight update for the recurrent weight, $W_R$. We have started from the last time step and gone back just 1 timestep back and have gotten the above equation. We have gotten this big an equation because of the recurrent nature of the weight $W_R$, due to which ht is dependent on $h_{t−1}$ which is dependent on $h_{t−2}$ which is dependent on $h_{t−3}$ and so on. Hence, if you expand the equation. expression above further, you tend to have all the previous hts in the expression.

Now, there is something interesting to note here. If you notice $h_{t−2}$has the coefficient WR and upon further expansion, ht−3 will have the coefficient W2R and so on, $h_{t−n}$ will have the coefficient Wn−1R. Hence, as you go back in time the power of WR keeps on increasing. Now, this becomes a problem. Why?

If we go 25 steps back, $h_{t−25}$ will have the coefficient $W^{24}_R$. Now, even if $W_R$ is equal to 0.75, $W^{24}_R$ becomes $10^{−3}$. This means the gradient will have literally no contribution of $h_{t−25}$. This is known as the problem of vanishing gradient. As you go back in time, due to the presence of higher powers of $W_R$ and the derivative of tanh terms, which is also less than 1, the compound effect is that you are not able to capture that information in weight updates and that is one of the limitations of RNN.

**Note that even if you are not able to completely understand the above equation, it's alright! You just need to understand the causal effect of the equation on the calculation of gradients as explained in the couple of paragraphs above.**

If you wish to go further deep and explore the actual derivations of backpropagation in RNN, then kindly refer to the optional session on backpropagation where you can also learn the derivation of the gradients. 

You saw that backpropagation is quite a complex process in RNNs. You have already seen that one of the drawbacks of RNNs is the vanishing and exploding gradients.

#### Gradients

Qn: During backpropagation, we calculate gradients for:

- $W_F$ only

- $W_R$ only

- none

- Both a and b

Ans: D. *Backpropagation is done for both $W_F$ and $W_R$.*

#### Gradient Equation

Qn: Correct gradient equation involves which of the following?

- Multiplication of recurrent gradients

- Addition of recurrent gradients

- Division of recurrent gradients

- None of the above

Ans: A. *Gradient equation involves multiplication of recurrent gradients.*

Let's discuss the effects of backpropagation on the feasibility of RNN and some other drawbacks in the next segment.