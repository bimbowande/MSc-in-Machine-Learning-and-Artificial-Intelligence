# Feature Maps

As you learnt in the previous segment, the values of the filters, or the weights, are learnt during training. Let's now understand how multiple filters are used to detect various features in images. In this segment, you will learn the concepts of neurons and feature maps.

**VIDEO**

Let's summarise the important concepts and terms discussed in this video: 

-   A **neuron** is a filter whose weights are learnt during training. For example, a 3×3×3 filter (or neuron) has 27 weights. Each neuron relates to a particular region in the input (that is, its ‘receptive field’).
-   A **feature map** is a mapping of where a certain feature is found in the image. It is derived using a collection of multiple neurons each of which relates to a different region of the input with the same weights. All neurons associated with a particular feature map extract the same feature (but from different regions of the input). 

The following figure shows feature maps derived from the input image using three different filters. 

![Feature Maps from Color Channels](https://i.ibb.co/1GdDNCn/Feature-Maps-from-Color-Channels.jpg)

You can have multiple such neurons convolving an image, each having a different set of weights and each producing a feature map.

**Convolution in VGGNet**  
Before moving on to the next component of CNNs, let’s summarise the entire process of convolution using the VGGNet architecture.

**VIDEO**

As mentioned in the video, the VGGNet architecture was designed with the following specifications:

-   Input size: 224×224×3
-   Filter size: 3×3×3
-   Stride: 1
-   Padding: Same padding (The input and the output sizes from one convolution layer to another convolution layer are the same)
-   13 convolution layers
-   Feature maps: 4096 at the end of the convolution layers

![VGGNet Architecture Feature Maps](https://i.ibb.co/txXKdMm/VGGNet-Architecture-Feature-Map.jpg)

The first convolutional layer takes the input image of size 224×224×3, uses a 3×3×3 filter (with some padding) and produces an output of 224×224. This 224×224 output is then fed to a **ReLU** to generate a 224×224 **feature map**. Note that the term ‘feature map’ refers to the (non-linear) **output of the activation function**, instead of the input to the activation function (that is, the output of the convolution).

Similarly, multiple other 224×224 feature maps are generated using different 3×3×3 filters. In the case of VGGNet, 64 feature maps of size 224×224 are generated, which are referred to in the figure as the tensor 224×224×64. Each of the 64 feature maps tries to identify certain features (such as edges, textures, etc.) in the 224×224×3 input image. The 224×224×64 tensor is the output of the first convolutional layer. In other words, the first convolutional layer consists of 64 3×3×3 filters, and hence, they contain 64×27 trainable weights (assuming that there are no biases). 

The 64 feature maps, or the 224×224×64 tensor, are then fed to a pooling layer, which you will explore in the next segment. However, as you proceed ahead, the network extracts more features and finally ends up with the 1×1×4096 tensor. This suggests that there are 4096 different feature maps at the end of the convolution blocks. Now, the architecture can leverage these 4096 features to classify the image accurately.

#### Number of Feature Maps

Qn: If we use 32 filters (or kernels) of size 3x3x3 to convolve an image of size 128x128x3, how many feature maps will be created after the convolution?

- 1

- 3

- 0

- 32

Ans: D. *We have already seen that each kernel of 3x3x3 will produce 1 feature map on an input of size 224x224x3. With 32 kernels, we will get 32 feature maps.*

#### Output Size

Qn: Given an image of size 128x128x3, a stride of 1, padding of 1, what will be the size of the output if we use 32 kernels of size 3x3x3?

- 128x128x3

- 128x128x32

Ans: B. *Each filter will produce a feature map of size 128x128 (with stride and padding of 1).  Thus, 32  filters will produce 32 feature maps of size 128x128.*

#### Output Size

Qn: Given an image of size 128x128x3, a stride of 1, zero padding, what will be the size of the output if we use 32 kernels of size 3x3x3?

- 128 x 128 x 3

- 126 x 126

- 128 x 128

- 126 x 126 x 32

Ans: D. *The output of one kernel will be (128 - 3 +1) = 126 x 126, and thus, the output of 32 kernels will be 126 x 126 x 32.*

#### Feature Map and Activation

Qn: FIll in the blank: "The values in a feature map are \_\_\_\_\_ related to the weights of the filter generating the map."

- Linearly

- Non-linearly

Ans: B. *Feature map is the output from the activation function, which is usually non-linear (such as ReLU). That is, for a patch vector p and weight vector w, the values in the feature map will be $f(w^T.p)$ where $f$ is a non-linear activation function.*

In the next segemnt, you will learn about the third component, that is, pooling.