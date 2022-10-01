# Weights and Biases in a CNN

Filters or kernels are the most crucial components of the convolution process, as they help extract the features from the image that later helps achieve the final target. You have already learnt how to use a predefined filter to detect a vertical edge in an image. Similarly, different filters can be used to identify a variety of features from the image. The difference between all these filters (assuming that the size is the same) will be the values that will be used to convolve the underlying image.

In some cases, you are only interested in one particular feature from the image, such as vertical edge detection, a color or a texture. Here, you are not asking the network to learn anything and use the architecture to just extract a basic feature. For such tasks, you would be expected to design a filter for the network, as it will only check for the required feature across all the patches of the image. 

![Vertical Edge Detection](https://i.ibb.co/BnKjgvt/Vertical-Edge-Detection.jpg)

However, when it comes to neural networks, you do not design a filter; instead, you want the network to learn the values at each step. At each layer of CNN, a feature is extracted that will later help in the final task. As the task is different across use cases, the filter needs to be altered for every use case. For example, you cannot use the filters that were used to identify the scenery in the image to detect humans in the image. This is similar to the **weights** used in the ANN architecture. For different use cases, the network learns weights from scratch so that it is able to perform the required task accurately. In the case of CNNs, filters act as weight vectors and must be learnt using the technique of backpropagation. The image given below summarises the entire process.

![Weights in CNN](https://i.ibb.co/mt2tM2m/Weights-in-CNN.jpg)

Components:

-   _**I**_: Image tensor (5×5×3)
-   _**W**_: Weight tensor (3×3×3)
-   _**P**_: Patch from the image to be convolved using the filter (3×3×3)

So, the output of the convolution process will be a matrix that holds the dot product of the two tensors (W and _**P**_).

Output: Image (I) × W→ sum(P _**• W**_)

This equation is similar to the feedforward equation, as the inputs from the image are multiplied by the filter values to obtain the output for that particular layer. As in the ANN architecture, the filters are learnt during training, i.e., during backpropagation. Hence, the individual values of the filters are often called the **weights of a CNN**.

In the discussion so far, you have only learnt about weights; however, convolutional layers (that is, filters) also have biases. Let’s take a look at an example to understand this concept better. Suppose you have an RGB image and a 2×2×3 filter as shown below. The filter has three channels, each of which convolves the corresponding channel of the image. Thus, each step in the convolution involves the element-wise multiplication of 12 pairs of numbers and the addition of the resultant products to obtain a single scalar output.

![Channels in image and their corresponding filters](https://i.ibb.co/QY50rGK/Channels-in-image-and-their-corresponding-filters.jpg)

**Channels in image and their corresponding filters**

The following GIF depicts the convolution operation. Note that in each step, a single scalar number is generated, and at the end of the convolution, a 2D array is generated.

![Color Channel Convolution GIF](https://i.ibb.co/h9m3Ypv/Color-Channel-Convolution-GIF.gif)

You can express the convolution operation as a dot product between the weights and the input image. If you treat the 2×2×3 filter as a vector w of length 12 and the 12 corresponding elements of the input image as the vector p (that is, both are unrolled from a 3D tensor to a 1D vector), each step of the convolution is simply the dot product of wT and p. The dot product is computed at every patch to obtain a (3×3) output array as shown in this GIF provided above.

Apart from the weights, each filter can also have a **bias**. In this case, the output of the convolutional operation is a 3×3 array (or a vector of length 9). So, the bias will be a vector of length 9. However, a common practice in CNNs is that all the individual elements in the bias vector have the same value (called **tied biases**). For example, a tied bias for the filter shown in the GIF given above can be represented as shown below:
$$\large{w^T.x+b=\begin{bmatrix}sum(w^T.p_{11})&sum(w^T.p_{12})&sum(w^T.p_{13})\\sum(w^T.p_{21})&sum(w^T.p_{22})&sum(w^T.p_{23})\\sum(w^T.p_{31})&sum(w^T.p_{32})&sum(w^T.p_{33})\end{bmatrix}+\begin{bmatrix}b&b&b\\b&b&b\\b&b&b\end{bmatrix}}$$
$$\large{=\begin{bmatrix}-4&-5&5\\3&11&6\\0&1&0\end{bmatrix}+\begin{bmatrix}b&b&b\\b&b&b\\b&b&b\end{bmatrix}}$$

Another way is to use untied biases where all the elements in the bias vector are different, that is, $b_{11},b_{12},\dots,b_{mn}$. However, the untied biases are much less commonly used than tied biases.


#### Convolution Operation

Qn: Given an image of size 128 x 128 x 3, a stride length of 1, padding of 1, and a kernel of size 3x3x3, what will be the output size?

- 128x128x3

- 128x128

- 126x126x3

- 126x126

Ans: B. *Though the input and filter are now 3D, the output of convolution will still be a 2D array. This is because, in each step of the convolution, the 9 elements of the filter will be 'dot product-ed' with the 9 elements of the 3D image, giving a single scalar number as the output.*

#### Weights in the Filters

Qn: Suppose you train the same network (i.e. the same architecture) for two different multiclass classification problems (such as classification of mammals and classification of flowers). Will the two resultant sets of weights be the same?

- The weights will be the same 

- Weights will be different

Ans: B. *Weights will be different since each network will learn weights which are appropriate for the respective classification task.*

#### Number of Trainable Weights

Qn: What is the total number of trainable weights in a kernel/filter of size 3x3x3? Assume there are no biases.

- Zero - the weights are not trainable, they are specified as part of by the network architecture

- 9

- 3

- 27

Ans: D. *There are 27 weights in a (3, 3, 3) filter, which are all learnt during training.*

#### Number of Trainable Weights and Biases

Qn: What is the total number of trainable parameters in a kernel/filter of size 3x3x3? Assume that there is a single tied bias associated with the filter.

- Zero

- 9

- 27

- 28

Ans: D. *There are 27 weights and one bias in the (3, 3, 3) filter.*

#### Number of Operations in a Convolution

Qn: Given an image of size 3x3 and a kernel of size 3x3, what will be the total number of multiplication and addition operations in convolution? Assume there is no padding and there are no biases (only weights). If there are m multiplication and n addition operations, the answer will be m+n.

- 15

- 15

- 17

- 18

Ans: C. *There will be 3x3 multiplication operations and (3x3-1) addition operations (you need n-1 addition operations to add n numbers).*

#### Number of Operations in 3D Convolution

Qn: Given an image of size 3x3x3, a kernel of size 3x3x3, padding of 1, and stride length of 1, what will be the total number of multiplication and addition operations in the convolution? Assume there are no biases (only weights). If there are m multiplication and n addition operations, the answer will be m+n.

- 159

- 153

- 477

Ans: C. *The output will be of size (n + 2p - k + 1) = (3, 3). In each step of the convolution, the 3 x 3 x 3 filter will be dot product-ed with a 3 x 3 x 3 array. This dot product will involve 27 pair-wise multiplications and then 26 addition operations, or 27+26 = 53 total operations. Since this operation will happen for each of the 3 x 3 cells in the output, the total number of operations is 53 x 9 = 477.*

In the next segment, you will learn about the next component of CNNs, that is, feature maps.