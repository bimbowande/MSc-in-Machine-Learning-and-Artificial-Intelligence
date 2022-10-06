# Graded Questions

The following questions are graded.

#### Average filter

Qn: Suppose we want to take the average over a (3, 3) patch in an image using a filter. Which of the following represents the 'average filter'?

- $\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}$

- $\begin{bmatrix}1&0&1\\1&0&1\\1&0&1\end{bmatrix}$

- $(1/16)*\begin{bmatrix}1&2&1\\2&4&2\\1&2&1\end{bmatrix}$

- $(1/9)*\begin{bmatrix}1&1&1\\1&1&1\\1&1&1\end{bmatrix}$

Ans: D. *The filter needs to give equal importance to all the values in the patch since we are taking an average.*

#### Convolution

Qn: Suppose we convolve an image X of size 4x4 with filter Y. We use 'zero-padding' of 1 (i.e. adding zeros around each edge of the image) and a stride length of 1. Find the output of the convolution X*Y.
$$\large{X=\begin{bmatrix}1&0&0&1\\-1&2&1&0\\0&1&0&0\\0&0&1&-3\end{bmatrix},~Y=\begin{bmatrix}0&1&0\\0&0&0\\0&1&0\end{bmatrix}}$$

- $\begin{bmatrix}1&0\\2&2\end{bmatrix}$

- $\begin{bmatrix}0.25&0\\0.5&0.5\end{bmatrix}$

- $\begin{bmatrix}−1&2&1&0\\1&1&0&1\\−1&2&2&−3\\0&1&0&0\end{bmatrix}$

- $\begin{bmatrix}0&2&1&0\\1&1&0&1\\0&2&2&0\\0&1&0&0\end{bmatrix}$

Ans: C. *Pad zeros all around the image X and then do the convolution X\*Y.*

#### Trainable parameters

Qn: Which of the following layers contains trainable parameters and which does not?

- Convolution and fully connected layers contain parameters, pooling does not.

- Convolution and fully connected layers do not contain parameters, pooling does.

- None of the layers - convolution, pooling, FC - contains trainable parameters.

- All the layers - convolution, pooling, FC - contain trainable parameters.

Ans: A. *The pooling layer does not contain any trainable parameters, Convolution and fully connected layers do. We learn the value of those parameters during backpropagation. Since pooling is just taking aggregate, there are no parameters involved in it. Say, we want to take an average of 4 numbers, we will just do (1/4) ( 4 numbers). There are no parameters that need to be learned.  Fully connected layer obviously has weights, we already know that from multilayer perceptron.*

#### Filters

Qn: Which of the following is correct about filters in the convolutional layer? More than one options may be correct.

- If a filter is extracting a particular feature at one spatial location $(x,~y)$, it must be the extracting the same feature at some other spatial location $(x_2,~y_2)$.

- If a filter is extracting a particular feature at one spatial location $(x,~y)$, it may or may not extract the same feature at some other spatial location $(x_2,~y_2)$.

-  Multiple different filters extract a variety of features from the same patch in an image.

- Though we use multiple different filters, they are not really required, since all the filters end up extracting the same feature.

Ans: A & C. *Each filter extracts the same feature from different spatial locations. Different filters extract different features from the same patch.*

#### Padding

Qn: What is the advantage of padding other than to keep the spatial dimension (width and height) of the output constant?

- If we don’t do padding then the information at the borders would be “washed away” too quickly.

- Padding is just for preserving the spatial dimension.

Ans: A. *Padding helps to preserve the information at the edges, otherwise, the convolution operation would extract information only from the central regions of the image.*

#### Pooling

Qn: Which of the following statements related to pooling are correct? More than one options may be correct.

- Pooling reduces the width and height of the output, thereby reducing the number of parameters and the amount of computation being done in the network.

- Since it reduces the number of parameters in the network, it also helps control overfitting.

- Pooling does not help control overfitting.

- Pooling makes the network invariant to certain local transformations.

Ans: A, B & D. 

- *Pooling reduces the width and height, thereby reducing the number of parameters and the amount of computation (since with less number of parameters there will be fewer computations involved in feedforward/backpropagation etc.).*

- *Pooling reduces the number of parameters and computation, it also controls overfitting.*

- *Since pooling takes a statistical aggregate over multiple regions of an image, it makes the network invariant to 'local transformations' (such as the face being tilted a little, or an object being located in a different region than what the training data had seen).*

#### Compact representation of network

Qn: Which of the following methods can be deployed to reduce the spatial dimensions of feature maps (width and height), and thereby, to make the representation of the network more compact? More than one options may be correct.

- Pooling operation 

- Convolution operation

Ans: Both. 

- *Pooling reduces the spatial dimension of the output.*

- *If we use convolution operation with stride > 1, e.g. with a filter of 2x2 and stride of 2, the output spatial dimension will reduce to half.*
