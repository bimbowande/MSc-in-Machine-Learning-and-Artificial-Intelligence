# Backpropagation Through Time - II

Now, let’s learn if the gradients of error with respect to WR can be calculated easily or not.

**VIDEO**

Unlike $W_F$ and $W_o$, $W_R$ will travel across the time domain also. Hence the error gradient derivative against the recurrent weights $W_R$ will be a bit complex as you will find while deriving the derivatives.

We already knew that ht and ot are similar and represented as the following.
$$\LARGE{h_t=tanh\left(E_Fx_t+W_Rh_{t-1}+b+l\right)}$$

In the video above, the terms inside the tanh has been abbreviated as $z_t$, hence $z_t=W_F*x_t+W_R*h_{t−1}+b_l$. Also when we open the gradients here, we get the following equation and mark it as **equation 1**.
$$\large{\dfrac{\delta\\E}{\delta\\W_R}=\dfrac{\delta\\E}{\delta\\z_t}\dfrac{\delta\\z_t}{\delta\\W_R}}$$

Now let’s see if we can further solve the partial derivative equation.

**VIDEO**

In the above lecture, Prof has demonstrated the calculation of the gradients of $z_t$ with respect to $W_R$ which is a factor in calculating the overall expression of recurrent weight's gradient. We mark this as **equation 2** as given below.
$$\large{\dfrac{\delta\\z_t}{\delta\\W_R}=h_{t-1}+W_R\dfrac{\delta\\h_{t-1}}{\delta\\W_R}}$$

The second term, which is a derivative of ht−1 with respect to WR, is a key operator as ht−1 will further depend upon WR. After doing further calculation, we get the following derivative and mark it as **equation 3**.
$$\large{\dfrac{\delta\\h_{t-1}}{\delta\\W_R}=tanh'(z_{t-1})\dfrac{\delta\\z_{t-1}}{\delta\\W_R}}$$

Also while calculating the gradient against $W_R$, the previous time step also comes into play as shown by the term $h_{t−1}$. Let’s see how it unfolds in the next video.

**VIDEO**

Now, we go another step further and calculate the gradient of $z_{t−1}$ with respect to $W_R$ which can be given as below **equation 4** as follows.
$$\large{\dfrac{\delta\\z_{t-1}}{\delta\\W_R}=h_{t-2}+W_R\dfrac{\delta\\h_{t-2}}{\delta\\W_R}}$$

Then  using substitution we simplify the **equation 1** further and get the below expression, which we got for backpropagation for two steps as we just calculated derivative till $h_{t−2}$.
$$\large{\dfrac{\delta\\E}{\delta\\W_R}=\dfrac{\delta\\E}{\delta\\z_t}\left[h_{t-1}+W_R.tanh'(z_{t-1}).h_{t-2}+W^2_R.tanh'\left(z_{t-1}\dfrac{\delta\\h_{t-2}}{\delta\\W_R}\right)\right]}$$

When you go just one step back in backpropagation, you get a term $W_R$ and for two step it will become $W^2_R$. Still, the dependency of WR is yet to be simplified as another function of $W_R$ is present in $h_{t−2}$. Further simplification of the equations will result in another term having factor of W3R. Hence, the common trend is that as you go backwards, you will see many weight terms getting multiplied. However, does it affect our training, let’s hear from the professor.

**VIDEO**

In the final expression of gradients, powers of $W_R$ are getting multiplied with derivatives of tanh as well. But then, the derivative of tanh is always below 1, which enhances the vanishing gradient problem. This is the reason that you may use other activation functions which have their derivative greater than one to reduce the vanishing gradient problem. However, this will enhance the exploding gradient problem.

Also, notice that the higher powers of weights are getting multiplied to earlier time step terms. This suggests that the contribution of the past inputs is harder to incorporate in the weight update gradient as we go deeper into the past. Therefore the model can easily remember the recent inputs but the problem is only when the dependencies start being longer.

Now, you understand the real cause of the vanishing gradient and exploding gradient problem, the weight term.