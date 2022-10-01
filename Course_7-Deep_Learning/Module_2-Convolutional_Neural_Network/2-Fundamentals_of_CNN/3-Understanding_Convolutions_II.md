# Understanding Convolutions - II

Let's continue with the example from the previous segment to understand how convolutions are used to detect features (such as vertical or horizontal edges) in an image.

**VIDEO**

In this video, you saw an example of how the convolution operation (using an appropriate filter) detects certain features in images, such as edges. An important point mentioned in the video was that a filter is learnt by the network through the process of backpropagation through the network. However, depending on your use case, you can use some predefined filters to extract specific features from the image.  
 

Another interesting observation can be seen in the convolution output provided below. Only the middle two columns (columns 2 and 3) of the output matrix are nonzero, while the two extreme columns (columns 1 and 4) are zero. This is an example of vertical edge detection.  

#### Vertical Edge Detection

![Vertical Edge Detection](https://i.ibb.co/BnKjgvt/Vertical-Edge-Detection.jpg)

Note that each column of the 4×4 output matrix looks at exactly three columns of the input image. The idea behind using this filter is that it captures the **amount of change (or gradient) in the intensity** of the corresponding columns in the input image along the horizontal direction.

For example, the output in columns 1 and 4 is 0 (20 - 20 and 10 - 10, respectively), which implies that there is no change in intensity in the first three and the last three columns of the input image, respectively. On the other hand, the output in columns 2 and 3 is 30 (that is, 20 - (-10)), indicating that there is a gradient in the intensity of the corresponding columns of the input image.

Through similar processes, the CNN architecture extracts a given feature using filters. However, the task does not end here. Like mammals, the convolution layers also operate in a hierarchical order. The CNN architecture has multiple convolutional layers stacked together to build on top of the basic or elementary features extracted by the initial layers. As the level of abstraction increases, the depth of the model can be increased by increasing the number of these convolution layers.  
 

**Other Filters**  
Based on the filter for vertical edge detection, you can design a filter for detecting the horizontal edges. As shown below, the objective will now be able to capture the change in intensity in the vertical direction.

![Filter Horizontal Edge Detection](https://i.ibb.co/6n1dW9T/Filter-Horizontal-Edge-Detection.jpg)

Although only simple filters have been discussed here, you can design arbitrarily complex filters for detecting edges and other patterns. For example, the following image shows the **Sobel filter,** which can detect both horizontal and vertical edges in complex images.

![Sobel Filter Output](https://i.ibb.co/nR1vLRV/Sobel-Filter-Output.jpg)

Question 1/3

Mandatory

#### Matrix in form of Image

Which of the following image approximately represents the given matrix?

| 0   | 0   | 0   | 0   | 0   | 0   |
| --- | --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 0   | 0   | 0   |
| 100 | 100 | 100 | 100 | 100 | 100 |
| 100 | 100 | 100 | 100 | 100 | 100 |
| 50  | 50  | 50  | 50  | 50  | 50  |
| 50  | 50  | 50  | 50  | 50  | 50  |

- ![Matrix in form of Image Ans 1](https://i.ibb.co/bFm3cNM/Matrix-in-form-of-Image-Ans-1.png)

- ![Matrix in form of Image Ans 2](https://i.ibb.co/x2xr9z5/Matrix-in-form-of-Image-Ans-2.png)

Ans: B. *Lower value of pixel means lower intensity and higher value for high intensity. Like '0' for black and '255' for white.*

#### Vertical Edge Detection

Given an input image X, which of the following filters will detect an edge in the vertical direction? More than one option may be correct:

![Vertical Edge Detection Qn](https://i.ibb.co/sKhrhM1/Vertical-Edge-Detection-Qn.jpg)

- ![Vertical Edge Detection Ans 1](https://i.ibb.co/zbKRBnJ/Vertical-Edge-Detection-Ans-1.png)

- ![Vertical Edge Detection Ans 2](https://i.ibb.co/TPCfT8P/Vertical-Edge-Detection-Ans-2.png)

- ![Vertical Edge Detection Ans 3](https://i.ibb.co/sCBKhLQ/Vertical-Edge-Detection-Ans-3.png)

- ![Vertical Edge Detection Ans 4](https://i.ibb.co/pxD6mzt/Vertical-Edge-Detection-Ans-4.png)

Ans: A, B & D. *Any matrix that takes the difference between the left and the right pixel can find the edge.*

#### Diagonal Edge Detection

Which of the following filters can be used to detect a diagonal edge (an edge at an angle of 45 degrees from the x-axis) in an image? Choose all the correct options.

- ![Diagonal Edge Detection Ans 1](https://i.ibb.co/kSS9H2K/Diagonal-Edge-Detection-Ans-1.png)

- ![Diagonal Edge Detection Ans 2](https://i.ibb.co/hY74Bg8/Diagonal-Edge-Detection-Ans-2.png)

- ![Diagonal Edge Detection Ans 3](https://i.ibb.co/Ss5k1sJ/Diagonal-Edge-Detection-Ans-3.png)

- ![Diagonal Edge Detection Ans 4](https://i.ibb.co/9Hw9CZv/Diagonal-Edge-Detection-Ans-4.png)

Ans: A & B.

You have now gone through some simple examples of filters and convolutions. However, given the wide range of options and parameters, you may have some questions such as the following:

- Can filters have arbitrary sizes?
- Can a given filter convolve any given image?

These questions can be answered through the concepts of stride and padding, which will be discussed in the coming segments.
