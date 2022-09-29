# Cross Entropy Loss Function

In the previous session, you went through the different aspects related to the definition of the loss function. Let's now look at some other advantages in using the cross-entropy loss in this lecture.

**VIDEO**

So, you can see that the cross-entropy loss helps in differentiating amongst the wrong decisions that the model makes. If the loss function was a simple comparison between the input and output, all the wrong decisions would have been on the same pedestal. But with cross-entropy loss, you are able to say that a certain decision is more incorrect than the other by looking at the loss value generated.

  
You have even seen that the differential of the cross-entropy loss has $y'_i$ in the denominator due to the log. Hence, if you decrease y′i by 10 times, the differential increases by 100 times. In short, the more $y'_i$ is away from $y_i$, the stronger is the push to move towards $y_i$.

Let us now understand this in more depth in the upcoming video:

**VIDEO**

Let consider the example that you saw in the above video to understand this better:

Actual output, $y=1$

**Decision 1:** Predicted output, $y'=0.97$

As you have already computed in the previous sessions, the gradient of the loss with respect to the predicted output can be given as follows:
$$\large{\dfrac{\delta\\L}{\delta\\y'}=\dfrac{y'−y}{y'(1−y')}}$$
$$\large{\dfrac{\delta\\L}{\delta\\y'}=\dfrac{0.97−1}{0.97*(1−0.97)}=\dfrac{−0.03}{0.97∗0.03}}=-1.031$$

**Decision 2:** Predicted output, $y'=0.81$
$$\large{\dfrac{\delta\\L}{\delta\\y'}=\dfrac{y'−y}{y'(1−y')}}$$
$$\large{\dfrac{\delta\\L}{\delta\\y'}=\dfrac{0-0.81}{0.81*(1−0.81)}=\dfrac{−0.19}{0.81∗0.19}}=-1.235$$

As you can see the absolute value gradient of the loss with respect to the predicted output for decision 1 is lesser than that of decision 2 as decision 1 is much closer to the actual output than decision 2. This is how cross-entropy loss can indicate if the function is going in the wrong direction.

As you have already learnt that **generalizability** and **keeping the error low** are two of the main objectives of training a neural network. Achieving generalizability is not possible if you use simple the classification loss calculation method ie., the loss is zero if actual and predicted output lies in the same class or else it is 1. Such a model will simply learn on every point of the training data in order to keep the error low. This will **lead** **to** **overfitting** which is highly undesirable. 

The cross-entropy loss solves the above problem to some extent. It helps in achieving the **generalisability** of the model with respect to the true loss function. In other words, the cross-entropy loss helps us in the prediction of the points which are outside the training data as it predicts the probability of the data point rather than declaring the point as correctly(0) or incorrectly(1) classified as in the case of the true loss function.

However, overfitting can also happen while using the cross-entropy loss. Let us see how this can be handled in the next video.

**VIDEO**

The issue of overfitting can be addressed while using the cross-entropy loss using the early stopping criteria. It states that you should stop the training at the point where the validation error starts increasing as you know that the training or the empirical error will keep decreasing as you increase the number of epochs or training as shown in the image below:

![Error vs Epochs](https://i.ibb.co/KW5rxcL/Error-vs-Epochs.png)

So far you have covered some interesting aspects revolving around loss functions. In the upcoming segment, you will learn more about the gradient descent algorithm.