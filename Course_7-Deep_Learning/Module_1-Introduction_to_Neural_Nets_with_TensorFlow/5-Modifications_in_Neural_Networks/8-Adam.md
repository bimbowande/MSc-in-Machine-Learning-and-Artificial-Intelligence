# Adam

**Adam** is yet another gradient descent optimization method that uses both **momentum** and **RMS Prop** but with the exponentially weighted average with the corresponding bias corrections. Let us learn about this algorithm in the upcoming video.

Play Video

3221820

Adam is the abbreviated form of **Adaptive Moment Estimation.** As you saw in the video above, it uses both momentum-based optimisers and RMS Prop techniques. Let us understand the implementation of the Adam optimiser as shown below:

1.  Initialize $v_{dW}=0$, $v_{db}=0$, $S_{dW}=0$, $S_{db}=0$
2.   On iteration $t$:
    1. Compute $dW$, $db$ for the current mini-batch   
    2. $v_{dW}=\beta_1∗v_{dW}+(1−β_1)dW$  
    3. $v_{db}=\beta_1∗v_{db}+(1−\beta_1)db$  
    4. $S_{dW}=\beta_2∗S_{dW}+(1−\beta_2)dW^2$  
    5. $S_{db}=\beta_2∗S_{db}+(1−\beta_2)db^2$  
    6.  Apply bias correction on all the terms as follows:
        1. $v^{corrected}_{dW}=\dfrac{v_{dW}}{1−\beta^t_1}$
        2. $v^{corrected}_{db}=\dfrac{v_{db}}{1−\beta^t_1}$
        3. $S^{corrected}_{dW}=\dfrac{S_{dW}}{1−\beta^t_2}$
        4. $S^{corrected}_{db}=\dfrac{S_{db}}{1−\beta^t_2}$
    7. $W_{new}=W_{old}−\alpha∗\left(\dfrac{v^{corrected}_{dW}}{S^{corrected}_{dW}}+\epsilon\right)$  
    8. $b_{new}=b_{old}−\alpha∗\left(\dfrac{v^{corrected}_{db}}{S^{corrected}_{db}}+\epsilon\right)$

Let us understand a bit more about the significance of bias correction in the Adam optimisers. As you can see, there are two values of $\beta$ i.e, $\beta_1$ and $\beta_2$. You have already seen that the value of β1(momentum related hyperparameter) is usually 0.9, therefore, $1−\beta_1$ becomes 0.1. On the other hand, $\beta_2$ is usually considered to be 0.999, therefore, $1−\beta_2$ becomes 0.001.

Let us take the momentum equation and substitute the values of β to understand the need for bias correction. Take a look at the equation below:
$$\large{v_{dW}=\beta_1∗v_{dW}+(1−\beta_1)dW=0.9∗v_{dW+}0.1∗dW}$$

The initial value of $v_{dw}=0$. Therefore, the first iteration will be:
$$\large{v_{dW1}=0.9∗0+0.1∗dW}$$
$$\large{\therefore,~vdW1=0.1dW}$$

Now let us go back to the stock price forecasting example, you saw in the momentum-based optimisers. Let us consider the price of the stock for today to be 55 INR. The price of stock tomorrow will be given by the momentum equation where $dW=55$.
$$\large{\text{Tomorrow's price, }v_{dW1}=0.1dW=0.1∗55}$$
$$\large{v_{dW1}=5.5}$$

There is a huge difference between the stock prices for today and tomorrow based on the prediction above. However,  this is very unlikely and the prediction is incorrect. This is because we have initialised vdw=0 which when multiplied by β1=0.9 makes the equation biased. To fix this issue and get a good result, bias correction is performed as follows:
$$\large{v^{corrected}_{dW}=v_{dW1}−\beta^t_1}$$

Therefore, for day 2 $(t=2)$, you will get:
$$\large{v_{dW}=0.9∗v_{dW}+0.1∗dW=0.9∗5.5+0.1∗dW=4.95+0.1∗dW}$$
$$v^{corrected}_{dW}=\dfrac{v_{dW}}{1−\beta^t_1}=\dfrac{4.95+0.1∗dW}{1−(0.9^2)}==\dfrac{4.95+0.1∗dW}{1−(0.19)}=26.05+0.53dW$$

For $dW=55$, you will get the following result:
$$\large{v^{corrected}_{dW}=26.05+0.53dW=26.05+0.53∗55=55.2}$$

As you can see that the value of stock predicted now lies near the current stock price. This is a more likely situation and a much more efficient prediction. This is how bias correction can help in the model performance. 

As you can see above, Adam computes both the momentum terms and the RMS Prop terms and uses both in order to update the parameters. Therefore, it provides an adaptive learning rate along with noise-free gradients. This advantage makes adam a widely used optimiser in the world of neural networks.

Now that you have completed the different gradient descent optimisers, let us learn about a problem faced by neural networks and how to deal with it in the next segment.