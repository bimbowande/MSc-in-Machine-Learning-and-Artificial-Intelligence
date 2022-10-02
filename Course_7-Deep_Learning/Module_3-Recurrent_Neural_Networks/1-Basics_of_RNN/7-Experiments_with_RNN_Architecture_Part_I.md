# Experiments with RNN Architecture - Part I

In the previous segments, you learnt about the basic RNN architectures where no other architectures were present and we treated hidden state as the final output as well. But this will not be the case always and you will need different modifications in the RNN architecture as per your problem at hand. Let’s first learn about adding an additional layer at the top of RNN.

**VIDEO**

In the above video, you learnt that you apply a sigmoid function on the current hidden state information by multiplying it with a weight matrix and a bias to get it in the desired shape of the output Similarly, for a regression problem, the activation function may vary.

Now, there might arise a situation where there are multiple inputs in a single time step or multiple sequences input at once.a. In such a situation, we tweak our RNN architecture a little.

Let’s see how we do that in the next video.

**VIDEO**

So, now you understand that you will need a different set of weights for each input sequence. If you input two sequences at the same time into the RNN, there will be two sets of weights for each of the sequences.

#### RNN Output

Qn: What is the relation between the final output ($\hat{y_t}$) and hidden state ($h_t$)?

- They will be the same if only RNN architecture is used to make predictions

- They will be different if a classification layer is added on top of the RNN layer.

- They will always be a copy of each other

- They will always be independent of each other

Ans: A & B. *A RNN cell will always output the hidden state hence if we add another layer on the top of it, the overall output $\hat{y_t}$ will be different from the hidden state ($h_t$).*

For some use cases, you might need two output sequences at each time step. Will you again need some modifications in RNN architecture? Let’s find the answer in the next segment.