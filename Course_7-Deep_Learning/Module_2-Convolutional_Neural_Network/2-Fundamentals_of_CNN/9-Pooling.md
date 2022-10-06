# Pooling

You started the session with the following three tasks in mind:

1. Scanning the image 
2. Identifying different features
3. Aggregating the learnings from individual neurons in succeeding layers

The convolution layer takes care of the first two steps by extracting different features from the image at different levels. After extracting the features (in the form of feature maps), CNNs typically aggregate these features using the pooling layer. Let’s take a look at how the pooling layer works and how it is useful in extracting higher-level features.

**VIDEO**

As discussed in this video, the pooling layer helps to determine whether a particular region in the image has the required feature or not. It essentially looks at larger regions (having multiple patches) of the image and captures an **aggregate statistic** (max, average, etc.) of each region. In other words, it makes the network **invariant to local transformations**. 

![Statistical Aggregate](https://i.ibb.co/981PMWn/Statistical-Aggregate.jpg)

The two most popular aggregate functions used in pooling are ‘max’ and ‘average’. The intuition behind these functions is as follows:

- **Max pooling**: If any one of the patches says something strongly about the presence of a certain feature, then the pooling layer counts that feature as ‘detected’.
- **Average pooling**: If one patch says something very firmly about the presence of a certain feature but the other ones disagree, the pooling layer takes the average to find out.

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

Let’s now compare the two techniques of pooling and understand both of them in detail in the next video.

**VIDEO**

As discussed in this video, max pooling is effective when you want to extract distinguished features. However, both max and average pooling techniques are effective when you want to make the network invariant to local transformations. You can also observe that pooling operates on each feature map independently. It reduces the size (width and height) of each feature map, but the number of feature maps remains constant. 

![Max Pooling](https://i.ibb.co/NLqJhxh/Max-Pooling.jpg)

Pooling offers the advantage of making the representation more compact by reducing the spatial size (height and width) of the feature maps. This attribute is really helpful when you want to make the entire process faster, since the decrease in the size of the layers results in the reduction of the number of convolution operations to be performed at each layer. This aspect is depicted in the following image:

![Convolution Max Pooling](https://i.ibb.co/CQ1p1xq/Convolution-Max-Pooling.jpg)

On the other hand, the pooling process also had a disadvantage. It loses a lot of information. Having said that, pooling has empirically been proven to improve the performance of most of the deep CNNs.

**Pooling in VGGNet**  
As mentioned in the video, the pooling layer of VGGNet is defined as follows:

- Window size: 2×2 (Aggregation of four 2×2 patches into one value)
- Stride: 1

![VGGNet Architecture Pooling](https://i.ibb.co/wdk8RfB/VGGNet-Architecture-Pooling.jpg)

The VGGNet architecture performs pooling at multiple layers in the architecture. This helps reduce the calculations in the entire process, which, in turn, helps in a faster result generation when the model is deployed.

#### Pooling

Qn: Which of the following statements related to pooling are correct?

- It makes the network invariant to local transformations.

- It makes the representation of the feature map more compact, thereby reducing the number of parameters in the network.

- It reduces the width, height and depth of the input.

- It reduces only the width and the height.

Ans: A, C & D. *Since it takes an average, max or some other operation over group of pixel, it does not look at an individual pixel, making network invariant to local transformation. It decreases the height and width, which reduces the number of parameters in a feature map. It reduces only the width and the height, not the depth.*

In the next segment, you will learn how all the concepts come together in the entire CNN architecture.  
 

#### Pooling parameters

Qn: How many trainable parameters are there in the pooling layer?

- 0

- 1

- 2

- It depends on the stride, padding and size of the input image.

Ans: A. *There are no parameters in pooling. The pooling layer just computes the aggregate of the input. For e.g. in max pooling, it takes max over group of pixels. We do not need to adjust any parameter to take max.*



#### Average Pooling

Find the output of the 'average pooling' in the following matrix X with a stride length of 2. X

|     |     |     |     |
| --- | --- | --- | --- |
| 1   | 6   | 12  | 9   |
| 3   | 9   | 0   | 5   |
| 3   | 5   | 1   | 7   |
| 6   | 4   | 0   | 1   |

- | 9   | 12  |
| --- | --- |
| 6   | 7   |

- | 1   | 2   |
| --- | --- |
| 3   | 4   |

- | 4.75 | 6.5  |
| ---- | ---- |
| 4.5  | 2.25 |

- | 19  | 26  |
| --- | --- |
| 18  | 9   |

Ans: C. *Average pooling is , take for example the first number, 4.75 is average of first 4 numbers, that is (1+6+3+9) /4 .  Similarly, calculate for others.*



## Additional Reading

Can you design a network without pooling? Capsule networks were designed to address some of the potential drawbacks of the conventional CNN architecture. You can refer to the article on ‘[Capsule Networks](https://arxiv.org/pdf/1710.09829.pdf)’ for details.