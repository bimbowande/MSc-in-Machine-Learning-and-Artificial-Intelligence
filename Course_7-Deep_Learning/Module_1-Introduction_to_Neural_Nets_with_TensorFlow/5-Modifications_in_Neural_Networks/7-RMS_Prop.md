# RMS Prop

In the previous segment, you learned about the Adagrad optimizer. Adagrad leads to shutting down the updates to some of the parameters if the gradients become too big. In this segment, you'll understand why this happens and how RMS Prop tends to solve this problem.

**RMS Prop** is the abbreviated form of **Root Mean Square Prop** optimiser. It was proposed by Geoff Hinton. Let us hear about this optimised from Usha in the upcoming video.

**VIDEO**

RMS Prop aims to solve the problem faced in adagrad. Let us understand how it is done by revisiting the implementation you saw in the video above. The algorithm for RMS Prop can be written as follows: 

1. On iteration $t$:
    1. Compute $dW$, $db$ for the given mini-batch
    2. $S_{dW}=\beta∗S_{dW}+(1−\beta)dW^2$
    3. $S_{db}=\beta∗S_{db}+(1−\beta)db^2$
    4. Update the parameters: $W_{new}=W_{old}−\alpha∗\dfrac{dW}{S_d{dW}}$ and $b_{new}=b_{old}−\alpha∗\dfrac{dW}{S_{db}}$

where $\alpha$ and $\beta$ are hyperparameters.

Instead of directly storing the squares of gradients as you saw in Adagrad, the RMS Prop optimiser takes care of the diminishing learning rate problem by considering the average of previous gradient squares in the $\dfrac{dW}{S_{db}}$ term.

However, RMS Prop suffers from the problem of manually defining the hyperparameters which might lead to slow convergence. Let us see how to solve this issue by learning about our last optimiser: **Adam.**