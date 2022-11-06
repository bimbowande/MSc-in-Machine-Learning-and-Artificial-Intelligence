# U-Net: Architecture - I

You have seen how encoder-decoder architecture is used to extract the features and develop a pixel map for the purpose of semantic segmentation. U-Net is an extension of the same framework but uses skip connections to connect the layers present in encoder and decoder. This segment will help you develop a deeper understanding of the architecture as it discusses all the sections in detail.

Note: The segment presents one of the many possible U-Net architectures. The model attributes such as input size, convolution parameters (layers, padding, stride, etc.) can vary to suit the purpose.

Let’s start by understanding the different elements of the architecture in the upcoming video.

**VIDEO**

As discussed in the video, the images provided below summarises the elements of U-Net architecture.

![U-Net Architecture](https://i.ibb.co/bHfmWt7/UNet-Architecture.png)

![U-Net Architecture Legend](https://i.ibb.co/1fDJvsj/UNet-Architecture-Legend.jpg)

It can be seen that this variant of the architecture takes input images of size 572 x 572. The output from each layer is a collection of feature maps and is represented in the form of red boxes. The dimensions of these feature maps are also highlighted along with them. Moreover, the arrows represent the different operations performed over the feature maps. 

The architecture consists of the following three sections:

- Encoder
- Bottleneck
- Decoder

The upcoming videos will now go deeper into each section of the U-Net framework. Let’s start with the contraction phase in the next video.

**VIDEO**

### Encoder/Contraction  

This phase marks the start of the architecture and is responsible for the downsampling process. There are multiple levels in the downsampling process as the architecture follows. As an example, we have taken a 572 x 572 image as the input. 

- In the first level, the input image passes through **two convolutional layers** that have 64 filters each. These layers are responsible for extracting the lower level features which will be combined along the encoder phase to obtain higher-level features present in the image. Apart from this, the example also highlights the reduction in height and width dimensions because of the convolution parameters (filter size, padding, stride) selected. These elements can be altered based on the user requirements to either increase or decrease the output at each layer.  
   

- At the end of the convolution layers, you have an output with 64 channels as depth which is passed through a **max pooling layer** with a 2 x 2 window and a stride of 2. This is the key factor that results in downsampling as each pooling layer reduces the dimensions to half. So, 568 x 568 is reduced to 284 x 284. However, note that this doesn’t impact the depth or the number of feature maps.  
   

- The above process is repeated with the increase in the number of feature maps and reduction of width and height dimensions at each level. The table below summarises the same.
  
  | Level | Input           | Output          |
  | ----- | --------------- | --------------- |
  | 1     | 572 x 572       | 284 x 284 x 64  |
  | 2     | 284 x 284 x 64  | 140 x 140 x 128 |
  | 3     | 140 x 140 x 128 | 68 x 68 x 256   |
  | 4     | 68 x 68 x 256   | 32 x 32 x 512   |

As you can see, the input image of size 572 x 572 has been reduced to 32 x 32, and there are 512 different features extracted from the image that will help in categorising each pixel into a specific class.

#### U-Net

Qn: Which of the following architectures can be used as an encoder in the U-Net framework? Select the most suitable answer.

- VGG-16

- ResNet-50

- GoogleNet

- All of the above

Ans: D. *You can use any CNN framework to build the U-Net architecture.*

Suppose you are working with the following architecture:

![](https://images.upgrad.com/aa781b78-17ca-400f-8671-c160529793ee-Image%2003.jpg)

Qn: What will be the dimensions of the output at Point A? Assume that the architecture extracts 64 features from the image in the first level of the architecture.

- 256 x 256 x 64

- 512 x 512 x 64

- 512 x 512 x 3

- 256 x 256 x 64

- 1024 x 1024 x 64

Ans: D. *Calculate the output size using $\left(\dfrac{(n+2*p-k)}{s}+1,~\dfrac{(n+2*p-k)}{s}+1\right)$*

- *$n$ is the input size (1024)*
- *$p$ is padding (1)*
- *$s$ is stride (1)*
- *$k$ is filter size (3)*

*Calculation: $1024 + 2*1 -3 + 1 = 1024$*

*The third dimension represents the number of feature maps which is 64 here.*

Qn: What will be the input dimensions at Point B? Assume the previous level extracted 128 features in the last layer.

- 512 x 512 x 128

- 512 x 512 x 256

- 256 x 256 x 128

- 256 x 256 x 256

Ans: C. *As there were a couple of pooling operations till point B, the size of the input reduces to **1024/4 = 256**. Moreover, the pooling operation doesn't alter the depth of the input so the number of feature maps stays the same as 128.*

Qn: Which of the following statements is true for point C?

- The height and width of the input at point C are 64 x 64.

- The feature extraction process ends at the layer marked in point C.

- Point C marks the end of the encoder section of the architecture.

Ans: A & C. *The initial input has gone through four pooling operations which reduce the dimensions to half at each layer. Hence, the final dimensions are $1024/(2^4)$ x $1024/(2^4)$ = 64 x 64. The downsampling process ends at point C. This marks the start of the bottleneck section of the architecture.*

The next segment will deal with the remaining components of the U-Net architecture.
