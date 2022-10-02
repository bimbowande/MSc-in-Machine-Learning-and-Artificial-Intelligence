# Drawbacks of RNN

As far as backpropagation is concerned you have already learnt about how the gradients flow and how the weights are updated using the gradients with respect to the error. Due to different types of weights in RNN ($W_R$ and $W_F$), especially recurrent weight ($W_R$), the backpropagation in RNN becomes a complex process. Given the complexity of backpropagation for the RNN models (through layers and time), the learning process does have some drawbacks. Let’s learn about it in this segment.

Although RNNs are extremely versatile and can (theoretically) learn extremely complex functions, the biggest problem is that they are extremely time-consuming to train, especially when the sequences get very long.

RNNs are designed to learn patterns in sequential data, i.e., patterns across 'time'. RNNs are also capable of learning what is called long-term dependencies. For example, in a machine translation task, we expect the network to learn the interdependencies between the first and the eighth word, learn the grammar of the languages, etc. This is accomplished through the recurrent layers of the network – each state learns the cumulative knowledge of the sequence seen so far by the network.

Although this feature is what makes RNNs so powerful, it introduces a severe problem – as the sequences become longer, it becomes much harder to backpropagate the errors back through the network. The gradients 'die out' by the time they reach the initial time steps during backpropagation.

Let’s hear more about it from Professor Mouli.

**VIDEO**

We saw earlier that the gradients against the recurrent weight expanded till one previous time step can be expressed by the below equation.
$$\large{\dfrac{\delta\\E}{\delta\\W_R}=\dfrac{\delta\\E}{\delta\\z_t}\left[h_{t−1}+W_R*tanh'(z_{t−1})*h_{t−2}+W^2_R*tanh'\left(z_{t−1}*\dfrac{\delta\\h_{t-2}}{\delta\\W_R}\right)\right]}$$
This equation forms the core idea of vanishing and exploding gradients as you can notice that for two backpropagation steps $W_R$ is raising to the power of two for the contribution of time step $t-1$. This will follow a similar path as we take more steps backwards - $W_R$ will keep rising in its power and if the value of $W_R$ is less than one, the gradients will vanish till they reach longer dependencies. The same is also valid for weights being greater than one, leading to the explosion of gradients as they get multiplied.

Now, even if the gradient at each time step is as good as 0.9, it will fade after a mere 25 words as $(0.9)^{25} < 0.1$. Hence, the words that the model saw in the later time steps will have almost nil gradient till they reach the last hidden state. It will further prohibit our model in learning longer dependencies.

In more detail, the weights update will not take place for words with longer dependency. You know the weight update equation as $W_{new}=W_{old}-\text{learning rate}*\text{gradient}$. If the gradient is almost zero, then Wnew = Wold and the model will not learn anything.

This problem of gradient becoming insignificant in case of longer dependency is called the problem of vanishing gradients. Following are the three ways to overcome this problem:

1.  Initialise weights as identity matrix and bias as zero matrix.
2.  Use other activations which have gradients greater than zero such as ReLU.
3.  Improve the architecture to retain the memory of longer dependencies.

**The first solution** of the vanishing gradient problem prevents the vanishing gradients by using specific initialisation of weights and biases. So when matrix multiplication happens between weights and inputs, they do not vanish or explode too quickly, as the weights are neither too much bigger than 1 nor too much less than 1. The multiplication of the identity matrix with the values doesn’t let the weights sum up and bias, being zero also has very little effect.

**The second solution** of the vanishing gradient problem can result in another problem called the problem of exploding gradients. Earlier when you used tanh, the gradient value of tanh function was below one, which enhanced the vanishing gradient problem, but similarly other activation functions having gradients greater than one will encourage the exploding gradient problem.

This problem is about gradients becoming too large to store in the memory as all the gradients being greater than 1 get multiplied. For example, if gradients have a value of 5 at each time step, then for a sequence of 25 words, the gradient will become $5^25$ which is greater than $10^17$. Now, imagine that the gradients get even bigger, or the number of words increases in the paragraph, the values will only become larger, pushing our memory to its limit.

One way of preventing exploding gradients is by using gradient clipping where we reset the gradient values whenever they get bigger than a threshold value. For example, if gradients get bigger than threshold = $10^8$, you reset it to 10.

**The third solution** of the vanishing gradient problem is done by making changes in the RNN architecture itself. You will learn more about it in the next session.

#### Backpropagation Through Time

Qn: Which of the following techniques will have no effect on either of the two problems – vanishing and the exploding gradients?

- Making the sequences longer or shorter

- Putting an upper limit to the gradient by clipping it

- Changing the Simple RNN architecture from many-to-many to many-to-one

- None of the above

Ans: C. *Changing the architecture will have no effect on it as far as calculations are concerned. The vanishing and exploding gradients problem is because of sequence length, not because of the type of architecture in use.*

#### Backpropagation Through Time (BPTT)

Qn: Which of the following is the correct way to overcome the vanishing gradient problem in RNN?

- Initialise weights as identity matrix and bias as zero.

- Use some activation function such that gradients become more than 1.

- Use gating mechanism-based architecture.

- All of the above

Ans: D. *All of the mentioned techniques are intended towards overcoming the vanishing gradient problem.*

#### Gradient

Qn: Suppose you are currently at $t=20$ and your RNN model needs to remember the word from $t=5$ to make a correct prediction. Considering all the gradients while backpropagation are 0.8, will your model be able to remember that word?

- Yes

- No

Ans: B. *The gradients will get multiplied at each step of backpropagation. In this case the relevant word is 15 time steps away hence the gradients will be multiplied 15 times hence their effective value will be $0.8^{15}=0.03$. Hence the model will not be able to use this information.*

Qn: Suppose you are currently at $t=20$ and your RNN model needs to remember the word from $t=18$ to make a correct prediction. Considering all the gradients while backpropagation are 0.8, will your model be able to remember that word?

- Yes

- No

Ans: A. *The gradients will get multiplied at each step of backpropagation. In this case the relevant word is just 2 time steps away hence the gradients will be multiplied 2 times hence their effective value will be $0.8^2=0.64$. Hence the RNN model will be able to remember this information.*

In the next segment, we'll summarise our learnings.