# Residual Net

In this segment, you will explore one of the modern CNN frameworks: residual network.

Until about 2014 (when GoogleNet was introduced), the most significant improvements in deep learning had appeared in the form of increased network depth, from AlexNet (8 layers) to GoogleNet (22 layers). Some other networks with about 30 layers were also introduced around that time. 

Driven by the significance of depth, a team of researchers asked the question: Is learning better networks as easy as stacking more layers? Let’s try to understand this in the video given below.

**VIDEO**

As you can see, with substantially deeper networks (with hundreds of layers), the team found some counterintuitive results (shown below). You can read more about it in the [paper](https://arxiv.org/pdf/1512.03385.pdf) published for ResNets.

![CIFAR10 ResNet Training and Test Error](https://i.ibb.co/PD9pJML/CIFAR10-Res-Net-Training-and-Test-Error.jpg)

The team found that the results are not because of overfitting. If that had been the case, the deeper net would have achieved a much lower training error, while the test error would have been high. Thus, the key motivator for the ResNet architecture was the observation that empirically, adding more layers was not improving the results monotonically.  This was counterintuitive because a network with n + 1 layers should be able to learn at least what a network with n layers could learn, plus something more.

Hence, to improve the performance, the ResNet team came up with a novel architecture with skip connections, which enabled them to train networks as deep as 152 layers. ResNet achieved groundbreaking results across several competitions: a 3.57% error rate on ImageNet and the first position in many other ILSVRC and [COCO object detection](http://cocodataset.org/#home) competitions.

![ResNet Architecture Skip Connections](https://i.ibb.co/bFy8Rd3/Res-Net-Architecture-Skip-Connections.jpg)

Some other key features of ResNet are summarised below:

-   ILSVRC’15 classification winner (3.57% top 5 error)
-   152 layer model for ImageNet; has other variants too (with 35, 50, 101 layers)
-   Two 3x3 convolution layers in every 'residual block'
-   No FC layer, except one last 1000 FC Softmax layer for classification
-   Global average pooling layer after the last convolution
-   Batch normalisation after every convolution layer
-   SGD + momentum (0.9)
-   No dropout used

You are also encouraged to read the detailed results in the ResNet paper provided at the bottom of this page.

In the next few segments, you will learn how to use these large pretrained networks to solve your own deep learning problems using the principles of transfer learning.

## Additional reading

1.  [The Residual Net, Kaiming He et al](https://arxiv.org/pdf/1512.03385.pdf).