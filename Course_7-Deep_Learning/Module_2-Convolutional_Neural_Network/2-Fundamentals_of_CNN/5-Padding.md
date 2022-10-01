# Padding

So far, you have gained an understanding of the basic purpose of convolution. The convolution process helps identify features such as edges, shapes and objects in an image. You can control the level or the granularity of these features using the stride value of the filter. Moreover, the level of abstraction can be controlled using the number of layers stacked in the architecture. 

However, this task gets challenging with an increase in the filter size or the stride value. Both these practices result in a reduction in size from input to output. If you remember, the 7×7 matrix shrunk to 5×5 when convolved with a 3×3-sized filter and a stride of 1. Owing to the reduction in size, it becomes difficult for the latter layers to perform the task of convolution.

In the next video, we will discuss more such challenges and provide you with a solution to overcome them. You will also be introduced to another important concept of convolution, that is, padding.

**VIDEO**

As mentioned in this video, padding helps you manage the size of the output of convolution. Padding of ‘x’ means that ‘x units’ of rows and columns are added all around the image. As shown in the image given below, padding of 1 has been introduced around a 5×5 image.

![Padding GIF](https://i.ibb.co/55SQQvv/Padding-GIF.gif)

**5×5 image with 1 padding layer**

When you convolve an image without padding (using any filter size), the output size is smaller than the image, i.e., the output ‘shrinks’. However, with the introduction of padding layers, the size of the output increases. It is important to note that only the width and the height decrease (not the depth) when you convolve without padding. The depth of the output depends on the number of filters used, which will be discussed in a later segment.

Padding helps us overcome both the challenges discussed at the beginning of the segment. However, you still have not learnt how to fill these additional rows and columns. Let’s hear from Samrat about this aspect in the next video.

**VIDEO**

As mentioned in this video, the most common way to do padding is to populate the dummy rows/columns with zeros, which is termed as **zero-padding**. It can also be a user-defined value; however, instead of an arbitrary value, it is generally zero or the pixel values at the edges.

**Preserving the size during convolution**  
If you want to maintain the same size, you can still use the technique of **padding**. Here, the padding layers are added in a manner such that the input and the output have the same size. The convolution process shrinks the input. For example, convolving a 6×6 image with a 3×3 filter and a stride of 1 gives a 4×4 output. Further, convolving the 4×4 output with a 3×3 filter will give a 2×2 output. The size has reduced from 6×6 to 2×2 in just two convolutions. 

![Preserving the size during convolution](https://i.ibb.co/Jrxjd2h/Preserving-the-size-during-convolution.jpg)

Large CNNs have tens (or even hundreds) of such convolutional layers (recall VGGNet). So, you might incur massive ‘information loss’ as you build deeper networks. This is one of the main reasons why padding is important: It helps maintain the size of the output arrays and avoid information loss. Of course, in many layers, you want to shrink the output (as shown below), but in many others, you maintain the size of the output.

![VGGNet Architecture](https://i.ibb.co/gvjw8rr/VGGNet-Architecture.jpg)

#### Input and Output of Convolutions

Qn: Given an image of size (n, n), a kernel of size (3, 3), no padding, and a stride length of 1, the output size will be: 

- (n, n)

- (n-1, n-1)

- (n-2, n-2)

- (n+1, n+1)

Ans: C. *Try convolving (3, 3), (4, 4), (5, 5) etc. images - you will note a pattern. In general, an (n, n) image will produce an (n-2, n-2) output on convolving with a (3, 3) filter.*

#### Stride and Padding

Qn: Given an image of size 5x5, filter size 3x3, stride 2, what is the padding required (on either side) to make the output size same as input size?

- 0 pixels on either side

- 1 pixels on either side

- 2 pixels on either side

- 3 pixels on either side

Ans: D. *3 pixels of padding is required around each edge of the image to make the output size the same as the image size.*

#### The Need for Padding

Qn: You saw that doing convolutions without padding reduces the output size (relative to the input which is being convolved). The main reason this is not always beneficial is that:

- Maintaining the output size results in stable models

- There will be heavy loss of information (especially in deep networks) if all the convolutional layers reduce the output size

- It does not matter much - one can build CNNs without any padding at all

Ans: B. *If all the layers keep shrinking the output size, by the time the information flows towards the end of the network, the output would have reduced to a very small size (say 2 x 2) - which will be insufficient to store information for complex tasks.*

#### A General Strategy for Maintaining the Output Size

Qn: Very often, you want to maintain the output size after convolution, i.e. if you have an (n, n) input, you want the output to be of size (n, n) as well. A general strategy to achieve this is:

- Use padding of 1 pixel (on both sides), a (3, 3) filter, and stride length 1

- Use padding of 2 pixels (on both sides) and a (3, 3) filter, and stride length 2

- Use zero padding and a (3, 3) filter, and stride length 1

Ans: A. *The output size is $\dfrac{n+2p−k}{s}+1$. With p=1, k=3, s=1, the output will always be (n, n).  Going forward, you may find remembering this useful.*

So far, you have been computing the output size manually (using the input image size, padding and stride length). In the next segment, you will learn generic formulas that will help reduce some of the manual work that you have been doing.