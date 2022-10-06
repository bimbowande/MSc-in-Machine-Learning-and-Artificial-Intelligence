# CNN Architecture - Overview

Now, you have a basic idea about the visual system of mammals and have also understood the different inputs that can be fed to a CNN framework. In this segment, we will analyse the architecture of a popular CNN called VGGNet. This is one of the truest CNN architectures and, hence, observing the VGGNet architecture will give you a high-level overview of the common types of CNN layers before you study each one of them in detail.

Let's dig a little deeper into CNN architectures now.

**VIDEO**

As you saw in the video, the CNN architecture has been closely derived from the visual system in mammals. The VGGNet architecture that we discussed was specially designed for the ImageNet challenge, a classification task with 1,000 categories. Thus, it takes colored images as the input and the softmax layer at the end has 1,000 categories. The blue layers are the convolutional layers, while the yellow ones are pooling layers. 

![VGGNet Architecture](https://i.ibb.co/gvjw8rr/VGGNet-Architecture.jpg)

You will study each one of them in detail as we proceed ahead in the module. To summarise the learning from the video, there are three main concepts you will study in CNNs:

-   **Convolution layers**: Used for scanning the image for different features
-   **Feature maps**: Store the information for different features extracted from the image
-   **Pooling layers**: For the aggregation of the information from different neurons in the previous layer
-   Lastly, you also have the **fully connected (FC) layers** that help in the final task of classification or regression. 

The most important point to notice here is that the initial part of the network (convolution and pooling layers) acts as a feature extractor for images. For example, the VGGNet discussed earlier can extract a 4096-dimensional feature vector representing each input image. This feature vector is fed to the later part of the network that consists of a softmax layer for classification. However, you can use the feature vector to perform other tasks (such as video analysis, object detection and image segmentation).

#### Feature Extractor

Qn: Which of the following operation acts as a feature extractor?

- Convolution

- Softmax

Ans: A. *Convolution operation acts as a feature extractor.*

#### Softmax Layer

Qn: What of the following is correct for the last softmax layer in the CNN?

- Each class probability lies in the range 0-1.

- The sum of all the class probabilities is 1.

- The sum of all the class probabilities is 100.

- Each class probability lies in the range 0-100

Ans: A & B. *Probability always lies between 0 and 1. The collective sum of all the probabilities cannot exceed 1.*

With this, you have now gained the basic knowledge of a CNN framework. In the next segment, you will see a few applications where CNNs are leveraged to get a good understanding of its capabilities.