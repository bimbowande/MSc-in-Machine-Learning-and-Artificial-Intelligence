# Batch Normalization

Let's take a look at one of the widely used techniques in training a neural network called **batch normalization.** Take a look at the upcoming video where Usha will introduce the concept to you:

**VIDEO**

You are already familiar with the process of normalization, which was used in machine learning models. The term ‘batch normalization’, as the name suggests, normalizes the output of each batch. This can be done in the following way:

1. Computing the batch mean: $\mu_B\gets\dfrac{1}{m}\sum^m_{i=1}x_i$  
     
2. Mini-batch variance: $\sigma^2_B\gets\dfrac{1}{m}\sum^m_{i=1}(x_i−\mu_B)$  
     
3. Normalization: $xi=(x_i−µ_B)/(\sigma^2_B+\epsilon)^{1/2}$  
     
4. Scale and shift: $y_i=(\gamma.x_i+β)$

Let’s use these formulas and try to solve an example in the next video.

**VIDEO**

Batch normalisation is performed on the output of the layers of each batch, Hl. It essentially involves normalizing the matrix Hl across all data points in the batch. Each vector in Hl is normalized by the mean vector μ and the standard deviation vector ^σ computed across a batch.

  
The image given below shows the batch normalisation process for a layer $l$. Each column in the matrix Hl represents the output vector of layer $l$, $h^l$, for each of the m data points in the batch. We need to compute the $\mu$ and the $\hat{\sigma}$ vectors, which represent the mean output from layer l across all points in the batch. We then need to normalize each column of the matrix Hl using μ and ^σ as shown below:

![Batch Normalization](https://i.ibb.co/52YZg1q/Batch-Normalization.jpg)

Hence, if layer $l$ has five neurons, we will have $H^l$ of the shape (5, m) where 'm' is the batch size, and $\mu$ and $\hat{\sigma}$ vectors are of shape (5,1). The first element of $\mu$ ($\mu_1$) is the mean of the outputs of the first neuron for all the 'm' data points, the second element $\mu_2$ is the mean of the outputs of the second neuron for all the 'm' data points and so on. Similarly, we get vector $\hat{\sigma}$ as the standard deviation of the outputs of the five neurons across the 'm' points. The normalisation step can be written as:
$$\large{H^l=\dfrac{H^l-\mu}{\hat{\sigma}}}$$
  
This step is performed by **broadcasting** $\mu$ and $\hat{\sigma}$. The final $H^l$ after batch normalisation is shown on the left side of the image given above. Batch normalisation is usually done for all the layer outputs except the output layer.

  
However, one small problem is performing batch normalisation during **test time**. Test data points are fedforward one at a time, and there are no 'batches' during test time. Thus, we do not have any $\mu$ and $\hat{\sigma}$ with which we can normalize each test data point. So, we take an average, i.e., the **average of the μ's and $\hat{\sigma}$'s** of the different batches of the training set. 

  
To understand how batch normalisation solves the problem of decoupling the weight interactions and improves the training procedure, let's reiterate why the normalisation of the input data works in the first place. The loss function contours the change after normalisation, as shown in the figure below, and it is easier to find the minimum of the right contours than the minimum of the contours on the left. The image below shows the normalization process:

![](https://images.upgrad.com/6025a6cb-df40-4fd5-b6dd-b5c88b6090a6-MLC_7.1.3_Img09-01.jpg)

Note that the batch normalisation process can also be applied to the cumulative input vector into the layer $Z^l$ instead of $H^l$. These are different heuristics. However, you need not worry about them since deep learning frameworks such as Keras use empirically proven techniques; you just need to write a simple line of code.

  
Libraries such as Keras use a slightly different form of batch normalisation. We can transform the above-mentioned equations as follows:
$$\large{H^l=\dfrac{H^l-\mu}{\hat{\sigma}}=\dfrac{H^l-\mu}{\sqrt{\hat{\sigma}^2+\epsilon}}=\gamma\\H^l+\beta}$$

Here, the constant ϵ ensures that the denominator does not become zero (when the variance is 0). The constants γ, β are hyperparameters. In Keras, you can implement batch normalisation as follows:

```python
model.add(BatchNormalization(axis=-1, epsilon=0.001, 
                         beta_initializer='zeros', 
                         gamma_initializer='ones'))
```

The 'axis= -1' specifies that the normalisation should happen across the rows.

This brings us to the end of this session. In the next segment, we will summarise all the topics covered in this session.

## Additional Reading:

1.  Dropouts can be explained using the notion of manifolds. You can explore this aspect in the [StackExchange answer](https://datascience.stackexchange.com/questions/5694/dimensionality-and-manifold) explaining the intuition of manifolds.
2.  You can read more about batch normalization in this [research paper](https://arxiv.org/pdf/1502.03167.pdf).