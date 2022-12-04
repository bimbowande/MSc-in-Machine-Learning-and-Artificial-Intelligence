# Upsampling

The previous segments helped you with the architecture of U-Net. The architecture is based on two key processes of downsampling and upsampling. 

![Downsampling Upsampling](https://i.ibb.co/z4s4Zrm/Downsampling-Upsampling.png)

The encoder is responsible for the process of downsampling which is the same as the convolutional neural network. The pooling layers used in the architecture reduce the size of the input at each level, resulting in a spatially reduced output. However, the concept of upsampling is new. This segment will help you understand the need for upsampling and also focus on the technique used in the U-Net framework.

The upcoming video talks about the first part, that is, the need of upsampling the feature maps obtained from the encoder.

**VIDEO**

As mentioned in the video, the semantic segmentation algorithm focuses on two parts:

1. **What**: Classes that the architecture is expected to identify
2. **Where**: Position (pixels) of the object in the image

The encoder answers the ‘what’ component as it is able to extract the features to identify the classes, however, the architecture loses the spatial information in the process. Therefore, the process of upsampling is required to map the identified features back to their position in the image. As mentioned in the video, the following upsampling techniques can be used:

- Bi-linear interpolation
- Cubic interpolation
- Nearest neighbor interpolation 
- Unpooling
- Transposed convolution

The segment will focus only on transposed convolution as the U-Net framework uses this technique for upsampling.

Let’s hear about transposed convolution from Georgios in the upcoming video.

**VIDEO**

**Transposed Convolution**  
This upsampling technique is the reverse of the convolution process. The convolution process results in the reduction of the size of the input, whereas, the transposed convolution method is used to upscale the image. As explained in the video, the filter matrix used is transformed and then multiplied with the downsampled values to obtain the upsampled output. 

**Important:** Note that the architecture uses the filter matrix to learn the shape of the transformed matrix used for transposed convolution. The values in this matrix are the same as weights as they are learnt using the process of backpropagation.

#### Transposed Convolution

Qn: What will be the shape of the transposed filter matrix if the convolution process has the following specifications?

1. the input size is $n$ x $n$,

2. the kernel size is $k$ x $k$

3. padding is $p$

4. stride is $s$
- $k^2$ x $n^2$

- $\left(\dfrac{(n+2p−k)}{s}+1\right)^2$ x $n^2$

- $n^2$ x $k^2$

- $n^2$ x $\left(\dfrac{(n+2p−k)}{s}+1\right)^2$

Ans: D. *The output of matrix multiplication with dimensions $a$ x $b$ and $c$ x $d$ is $a$ x $d$, where b and c should be equal. In transposed convolution, the output should be $n^2$ x $1$ as the resulting output is a flattened array that contains all the input pixels. So, the first dimension of the transposed filter matrix will be $n^2$. The second dimension is dependent on the output of the normal convolution process. The transposed filter is multiplied with a flattened array of output from the normal convolution process. Hence, the second dimension is $\left(\dfrac{(n+2p−k)}{s}+1\right)^2$.*

Qn: Assuming you have the following inputs for the convolution process, select the correct option associated with the transposed filter matrix generated during the process of upsampling in U-Net.

Input:

| 3   | 10  | 5   |
| --- | --- | --- |
| 10  | 4   | 3   |
| 1   | 5   | 10  |

Kernel:

| 1   | 0   |
| --- | --- |
| 0   | 1   |

Assume padding is 1 and stride is 1.

- The above information is sufficient to calculate the transposed filter matrix.

- The dimensions of the transposed filter matrix will be 9 x 16.

- The dimensions of the transposed filter matrix will be 16 x 9.

Ans: B. *As highlighted in the previous question, the dimensions of the transposed filter matrix are: $n^2$ x $\left(\dfrac{(n+2p−k)}{s}+1\right)^2$.*

The next segment will deal with one of the loss functions that can be used to optimise the performance of the segmentation model.

## Additional Reading

1. [A guide to convolution arithmetic for deep learning](https://arxiv.org/pdf/1603.07285.pdf)