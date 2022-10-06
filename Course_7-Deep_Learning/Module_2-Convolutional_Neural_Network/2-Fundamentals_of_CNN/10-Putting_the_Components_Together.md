# Putting the Components Together

You have now studied all the main components of a typical CNN, including convolutions, feature maps and pooling layers. Let’s now quickly summarise and put them together to get an overall picture of CNN architecture.  

**VIDEO**

To summarise, a typical CNN architecture comprises three types of layers:

1.  Convolution layers
2.  Pooling layers
3.  Fully-connected (FC) layers

The convolution and pooling layers together form a CNN unit or a CNN layer. This unit is responsible for extracting the features from the image. You start with an original image and do convolutions using different filters to get multiple feature maps at different levels. The pooling layer calculates the statistical aggregate of the feature maps to reduce the spatial size and to make the entire process robust against the local transformations. 

![CNN Architecture](https://i.ibb.co/P9k77Ym/CNN-Architecture.jpg)

The above image is a simple representation of a CNN unit in the VGGNet architecture. Each feature map, of size c×c, is pooled to generate a c/2×c/2 output (for a standard 2×2 pooling. Moreover, the pooling process only reduces the height and the width of a feature map, and not its depth (that is, the number of channels).

![VGGNet Architecture Final](https://i.ibb.co/K9Jq32p/VGGNet-Architecture-Final.jpg)

Once all the features are extracted, the output from the convolution layers is flattened in the FC layers. As shown in the above image, the size of the last pooling layer (7×7×512) is reduced to (1×1×4096). These 4096 features are fed to the softmax layer for the final task of classification.

#### Pooling Operation

Qn: Given an input of size 224x224x3 and stride of 2 and filter size of 2x2, what will be the output after the pooling operation?

- 112x112

- 112x112x3

- 224x224

- 224x224x3

Ans: B. *Pooling will reduce only the height and the width, not the depth. So, depth of channel, here '3' will be there in the output. You can even calculate the output size by the formula ((n+2p-k)/s +1). In pooling, we don't pad the input and the value of padding will always be '0'.*

#### A CNN Unit

Qn: What does a typical CNN 'unit' (also called a CNN 'layer') comprise of?

- A collection of feature maps

- A pooling layer

- A collection of feature maps followed by a pooling operation

- None of these

Ans: C. *What we refer to as a CNN layer or unit is a collection of m feature maps each of which is pooled to generate m outputs. Typically, the output of pooling reduces the size to half, since the most common form of pooling is with a stride of 2.*

#### Size of Feature Maps

Qn: In a typical deep CNN, the size of each subsequent feature map reduces with the depth of the network. The size reduction is typically done in two ways  - 1) convolution without padding or 2) by pooling. What is the main reason we prefer a lower dimensional output of an image from the network?

- Lower dimensional outputs capture more information than a higher-dimensional one.

- Lower dimensional outputs make the network easier to train (i.e. during backpropagation).

- We want a compact representation of the image as the output, one which preferably captures only the useful features in the image.

- Low dimensional outputs have empirically proven to be more useful than high dimensional ones.

Ans: C. *The reason we want a compact representation of the image is to get rid of all the redundancies in the image. For e.g. all the 224 x 224 x 3 pixels may not be required to do a classification or object detection task, just a smaller vector (say of length 5000) may be enough.*
