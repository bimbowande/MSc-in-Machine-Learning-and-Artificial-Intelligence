# Adagrad

In this segment, we'll explore a variant of the momentum-based method which you previously learnt. In addition to the advantages of the momentum-based gradient descent algorithm, **adagrad** adapts the learning rate to the parameters of the model. Let us understand how this algorithm works in the upcoming video.

**VIDEO**

So far you have seen the commonly used value of learning rate to be α=0.01. Now, suppose you have a dataset with certain features that occur more frequently than the others. Can you apply this value to all features in a dataset?

The answer is no. If you do so, the model will learn more about certain features than the others leading to incorrect results. Therefore, you need learning rates that can **adapt** to the features of the dataset. This can be achieved by using the adagrad optimiser. Adagrad provides us with the following:

1.  **Adaptive Learning Rate**: α adapts to the shape of the function.
2.  **Differential Learning Rate**: α is now a vector with different values for different features.

The adaptive learning rate enables the model to learn efficiently as you just learnt and the differential learning rate is required for calculating gradients during backpropagation. These advantages are the reason why this algorithm is widely used. 

Let us now understand the implementation of this algorithm. As you already know, you can update weights as follows:
$$\large{W_{new}=W_{old}−\alpha*\dfrac{\delta\\L}{\delta\\W}}$$

The adaptive learning rate α can be given as follows:
$$\large{\alpha=\dfrac{\alpha}{\sqrt{\epsilon+\sum^N_{i=1}\left(\dfrac{\delta\\L}{\delta\\W}\right)^2}}}$$
$$\large{\therefore~W_{new}=W_{old}−\dfrac{\alpha}{\sqrt{\epsilon+\sum^N_{i=1}\left(\dfrac{\delta\\L}{\delta\\W}\right)^2}}*\dfrac{\delta\\L}{\delta\\W}}$$

This adaptive learning rate takes a higher value for less frequent features and a low learning rate for frequently occurring features. Therefore, there is no need to update the learning rate manually.  ϵ is also present in the denominator so that the adaptive learning rate does not shoot up when the gradient of the particular weight becomes very less.

However, this algorithm also has a disadvantage i.e., the learning rate keeps decreasing with every iteration. This leads to very slow convergence.

This issue can be solved by another optimiser which you will learn in the next segment.