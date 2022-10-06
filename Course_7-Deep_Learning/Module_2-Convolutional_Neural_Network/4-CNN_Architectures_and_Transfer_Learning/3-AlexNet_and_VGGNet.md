# AlexNet and VGGNet

In this segment, we will briefly look into the architecture of AlexNet and understand how it is different from VGGNet.

The AlexNet was one of the very first architectures to achieve extraordinary results in the ImageNet competition (with about a 17% error rate). This architecture paved the way for other CNN architectures by helping in realising the potential that CNNs hold.

Let’s hear about this framework in the upcoming video.

**VIDEO**

![AlexNet Framework](https://i.ibb.co/NpPSBcP/Alex-Net-Framework.jpg)

The following details summarise the AlexNet framework:

-   The network used either layers (five convolutional and three fully connected). 
-   Unlike VGGNet, the architecture had various kernels of large sizes such as (11, 11), (5, 5), etc. 
-   Due to large filter sizes, the network had nearly 61 million parameters (weights and biases).
-   Because of the lack of good computing hardware, it was trained on smaller GPUs (with only 3 GB of RAM). Thus, the training was distributed across two GPUs in parallel (figure shown below). 

![AlexNet Architecture](https://i.ibb.co/SKnXTsB/Alex-Net-Architecture.jpg)

-   AlexNet was also the first architecture to use the ReLU activation heavily.

It is highly recommended that you go through the [AlexNet paper](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf) (you should be able to read most CNN papers comfortably now). Some of the other important highlights of the network are as follows:

-   Along with the 11x11 filter, the AlexNet architecture also uses a large stride of four. Moreover, the filter size reduces as we move ahead in the layers. This helps in reducing the number of operations in the feedforward network as the number of scans reduces.
-   AlexNet was the first to use dropouts, which were quite recent back then.

The VGGNet succeeded the AlexNets in the ImageNet challenge by reducing the error rate from about 17% to less than 8%. Let's compare the architectures of both networks in the upcoming video.

**VIDEO**

![VGGNet AlexNet](https://i.ibb.co/g7JyYN0/VGGNet-Alex-Net.jpg)

You are already familiar with VGGNet from the previous session. The following points summarise the discussion on the differences between the two networks:

-   The number of layers increased in the VGGNet framework (19 layers). This also led to the increase in the overall features extracted by the architecture. Even though the final count of features is 4,096 in both the architectures, with the increase in convolution layers in VGGNet, the network can explore more lower-level features to combine them into the last layer.
-   Compared to the large and varied filter sizes in AlexNet, VGGNet has used all filters of the same size (3, 3) across all the layers. This also helped in increasing the depth of the network.

## Comprehension - Effective Receptive Field

The key idea in moving from AlexNet to VGGNet was to increase the depth of the network by using smaller filters. Let's understand what happens when we use a smaller filter of size (3, 3) instead of larger ones such as (5, 5) or (7, 7).

Consider the example discussed in the video. Say we have a 5 x 5 image, and in two different convolution experiments, we use two different filters of size (5, 5) and (3, 3), respectively.

![Effective Receptive Field](https://i.ibb.co/JvDcW4v/Effective-Receptive-Field.jpg)

-   In the first convolution, the (5, 5) filter produces a feature map with a single element (note that the convolution is followed by a nonlinear function as well). This filter has 25 parameters.
-   In the second case with the (3, 3) filter, two successive convolutions (with stride = 1, no padding) produce a feature map with one element.

We say that the stack of two (3, 3) filters has the same effective receptive field as that of one (5, 5) filter. This is because both these convolutions produce the same output size (1 x 1 here) when convolved over the same 5 x 5 image. However, the output will not be the same, as the weights learnt will be different from each other.

Note that with a smaller (3, 3) filter, we can make a deeper network with more nonlinearities and fewer parameters. In the aforementioned case:

-   The (5, 5) filter has 25 parameters and one non-linearity, and
-   The (3, 3) filter has 18 (9+9) parameters and two non-linearities.

Since VGGNet used smaller filters (all of 3 x 3) compared to AlexNet (which had used 11 x 11 and 5 x 5 filters), it was able to use a higher number of nonlinear activations with a reduced number of parameters.

#### Effective Receptive Field

Qn: A (7, 7) filter has the same effective receptive field as (assuming zero padding and stride length 1):

- Two (3, 3) filters

- Two (5, 5) filters

- Three (3, 3) filters

Ans: C. *Consider an (n, n) image. A (7, 7) filter will result in an (n-6, n-6) output. Now consider some convolutions with a (3, 3) filter. The first convolution will produce an (n-2, n-2) output, the second will produce an (n-4, n-4) output, and the third will produce an (n-6, n-6) output.*

In the next segment, we will briefly study GoogleNet, which has outperformed VGGNet.

## Additional Readings

We strongly recommend you read the AlexNet and VGGNet papers provided below. By now, you should be able to read CNN-based papers comfortably.

-   [The AlexNet paper, Alex Krizhevsky et. al.](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)
-   [The VGGNet paper, Karen Simonyan et. al.](https://arxiv.org/pdf/1409.1556.pdf)