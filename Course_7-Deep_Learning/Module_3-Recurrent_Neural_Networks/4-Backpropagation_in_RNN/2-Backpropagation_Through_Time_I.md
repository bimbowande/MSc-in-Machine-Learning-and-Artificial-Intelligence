# Backpropagation Through Time - I

You have already learnt about the forward pass in the RNNs in detail. Hence, let’s first get into how the backward pass happens.

**VIDEO**

You learnt about the backward pass which follows the path depicted by the diagram below.

![Backward Pass](https://i.ibb.co/hVPdLps/Backward-Pass.png)

You can see that for all of the weights, the gradients at multiple time steps are used for updating them. As you do backpropagation after a time number of time steps, here, t. Hence, you use the sum of errors at all these time steps for weight updation.

These error gradients are necessary to update the weights to minimise the error. Also note that we sum up all the error values as well as gradients before processing for calculations.

With that note, let’s start by calculating the gradients with respect to $W_o$.

**VIDEO**

So, calculating the gradient wrt $W_o$ is not a very complex derivation. It follows a similar process to ANN and CNN. We get the following expression for the gradient.
$$\large{\dfrac{\delta\\E}{\delta\\W_o}=\dfrac{\delta\\E}{\delta\hat{y_t}}\dfrac{\delta\hat{y_t}}{\delta\\W_o}}$$

Where $\hat{y_t}$ is the output we get out of the RNN model. Now $\hat{y_t}$ is just a function of $o_t$, which will have no further dependency upon $W_o$. Therefore no further expansion is required in the final expression of gradients. You'll take the derivates of the error at multiple time steps and sum them up to update Wo as the objective function you are minimizing is the sum of all the errors until time step $t$.

But what about $W_F$? Let’s hear from the professor.

**VIDEO**

While calculating the gradients against $W_F$ , you will just need to expand the gradients one step further as here $\hat{y_t}$ will have dependence upon $o_t$ which will further depend upon $W_F$. Finally we get the following expression.
$$\large{\dfrac{\delta\\E}{\delta\\W_o}=\dfrac{\delta\\E}{\delta\hat{y_t}}\dfrac{\delta\hat{y_t}}{\delta\\o_t}\dfrac{\delta\\o_t}{\delta\\W_o}}$$
∂E∂WF=∂E∂^yt∂^yt∂ot∂ot∂WF

In the next segment, you will learn to calculate the gradients of $W_R$.