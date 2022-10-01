# Summary

This session focused on the key components of convolution neural networks (CNNs), which are as follows:

-   Convolution layer
-   Feature maps
-   Pooling layer

You learnt that specialised filters, or kernels, can be designed to extract specific features from an image (such as vertical edges). A filter convolves an image and extracts features from each ‘patch’. Multiple filters are used to extract different features from the image. Convolutions can be done using various combinations of strides and paddings.

The formula to calculate the output shape after convolution is given by:
$$\left(\dfrac{n+2p−k}{s}+1\right),~\left(\dfrac{n+2p−k}{s}+1\right)$$

where,

-   The image is of size  $n$ × $n$
-   The filter is of size $k$ × $k$
-   Padding is $p$ layers
-   Stride is $s$

The filters are learned during training (backpropagation). Each filter (consisting of weights and biases) is called a neuron, which covers a small patch of the entire image. Multiple neurons are used to convolve an image (or feature maps from the previous layers) to generate new feature maps. The feature maps contain the output of convolution + non-linear activation operations on the input. 

A typical CNN unit (or layer) in a large CNN-based network comprises multiple filters (or neurons), followed by non-linear activations and then a pooling layer. The pooling layer computes a statistical aggregate (max, sum, etc.) over various regions of the input and reduces the sensitivity to minor, local variations in the image. Multiple such CNN units are then stacked together, followed by some fully connected layers, to form deep convolutional networks.  
 

In the next session, you will learn to build and train CNNs using TensorFlow + Keras.