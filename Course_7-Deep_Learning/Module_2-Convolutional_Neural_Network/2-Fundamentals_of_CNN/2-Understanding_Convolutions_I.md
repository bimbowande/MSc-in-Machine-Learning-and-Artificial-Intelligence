# Understanding Convolutions - I

By now, you have a fair idea of the three main terms related to the CNN architecture:

- Convolutions
- Feature maps
- Pooling

As mentioned in the previous session, these components are closely derived from how the visual system works in mammals. They perform three broad tasks as listed below:

1. Scanning the image 
2. Identifying different features
3. Aggregating the learning from individual neurons in succeeding layers

This segment will deal with the first component, that is, the convolution layer, which helps scan an image for different features. It is the core building block of a CNN. Essentially, convolution is a mathematical operation, but before moving onto numbers, let’s first understand the intuitive sense of this operation from Samrat in the next video.

**VIDEO**

This video gave you a basic idea of what convolution is. The convolution process comprises a **filter** or a **kernel**, which is similar to the receptive field of a neuron in mammals. Similar to a neuron, this filter scans the entire image for a visual feature. This feature could range from basic elements, such as an edge (horizontal or vertical), shape, colour or texture to high-level objects, such as a face, a car or an animal. This filter is systematically moved across to cover the entire height and width of the image to extract the desired feature.

Let’s now try to understand the concept of convolution mathematically in the next video.  
 
**VIDEO**

As shown in this video, the convolution operation is the summation of the element-wise product of two matrices. In CNNs, the image and the filter are translated into arrays of numbers, which are then convolved together to produce the final result. Take a look at the graphic given below to visualise the entire process. 

![Convolution Visualisation](https://i.ibb.co/7Nx94BR/Convolution-Visualisation.gif)

*The blue-coloured 4×4 matrix is the input image. The 3×3 box that moves over the blue map is the filter, and the resultant output is the green-coloured 2×2 matrix.*

Let’s take a look at another example for more clarity.

**Convolution Example**  
Consider the image shown below and convolve it with a 3×3 filter to produce a 3×3 array. 

![Convolution Example Image](https://i.ibb.co/rp9wLC5/Convolution-Example-Image.jpg)

![Convolution Example Filter](https://i.ibb.co/sRB4txP/Convolution-Example-Filter.jpg)

The GIF shown below demonstrates the convolution operation.

![Convolution Example Operation](https://i.ibb.co/Y88qL0X/Convolution-Example-Operation.gif)

#### Understanding Convolution

Qn: Given an input matrix X of size (2,2) and filter matrix Y of size (2,2), find the output value after we perform convolution of X and Y.

X

| 1   | 4   |
| --- | --- |
| 0   | 9   |

Y

| 4   | 0   |
| --- | --- |
| 2   | 1   |

- 10

- 13

Ans: B. *Convolution of 2 matrices X and Y is : $1*4+4*0+0*2+9*1=13$*

#### Convolution of X with Y

Given an input image X (3,3) and a filter Y of size (2,2), as shown below, what is the output matrix after convolution?

![Convolution of X with Y Qn](https://i.ibb.co/5kBGh73/Convolution-of-X-with-Y-Qn.jpg)

- ![Convolution of X with Y Ans 1](https://i.ibb.co/gTY7dF7/Convolution-of-X-with-Y-Ans-1.png)

- ![Convolution of X with Y Ans 2](https://i.ibb.co/zH4NMfJ/Convolution-of-X-with-Y-Ans-2.png)

Ans: A. 

#### Output size

Qn: Given an input image of size (10,10) and a filter of size (4,4), what will be the size of the output size on convolving the image with the filter? (Assume step size = 1)

- (8,8)

- (7,7)

- (6,6)

- (5,5)

Ans: B. *If we move (4,4) matrix on a matrix of size (10,10), there will be 7 vertical and 7 horizontal positions.*

Now that you have understood the basic idea behind filters and convolutions, let's try to understand how convolutions are used to detect features (such as vertical or horizontal edges), in the next segment.
