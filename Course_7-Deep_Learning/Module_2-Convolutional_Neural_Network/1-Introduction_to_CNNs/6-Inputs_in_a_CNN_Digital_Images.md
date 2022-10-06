# Inputs in a CNN - Digital Images

Before we dig deep into the architecture of CNNs, let's try to understand the inputs that are fed into them. CNNs generally deal with visual data in the form of images and videos. This segment will help you understand the elements associated with the images. 

You already know that the input to any neural network should be numeric. Fortunately, images are naturally represented as arrays (or matrices) of numbers. Let's study their typical structure in the upcoming video.

**VIDEO**

The video helped in understanding the first type of visual data – grayscale images. This is the most basic input as it only has one channel that stores the shades of grey. To summarise, let’s consider this sample image of a 'zero' from the MNIST data set:

#### 18x18 grayscale image

![18x18 Grayscale Image](https://i.ibb.co/PCXdMm2/18x18-Grayscale-Image.jpg)

-   Images are made up of pixels.
-   The height and width of this image are 18 pixels, so it is stored as an 18 x 18 array.
-   Each pixel's value lies between 0 and 255.
-   The pixels having a value close to 255 appear white (since the pixels represent the intensity of white), and those close to 0 appear black.

One important point to note is that an image with more pixels holds more information and, hence, has better clarity as compared to an image with a lower pixel count. You would have come across this terminology while purchasing smartphones. When we say that the phone has a 10-megapixel camera, it means each image captured by that camera will have 10 million pixels. A 20-megapixel camera will have twice as many pixels and, hence, the captured image will have better clarity because of the extra details stored in it.

You will now learn about the colored images in the next video.

**VIDEO**

Let’s now summarise the entire part for a colored image. 

![Color Channels](https://i.ibb.co/5FY0QZD/Color-Channels.jpg)

-   Each pixel in a colour image is an array representing the intensities of red, blue and green. The red, blue and green layers are called channels.
-   Every pixel comprises the information of all three channels (RGB).
-   The height and width of the given image is five pixels each. However, the size of the matrix is 5 x 5 x 3.
-   The reason for selecting these three colors (red, green and blue) is that all the colours can be made by mixing red, blue and green at different degrees of ‘saturation’ (0-100% intensity). For example, a pure red pixel has 100% intensity of red and 0% intensity of blue and green. So, it is represented as (255,0,0). White is the combination of 100% intensity of red, green and blue. So, it is represented as (255,255,255).

#### Pixels

Qn: How many total number of pixels are there in a grayscale image whose dimension is (250,150)?

- 250

- 150

- 37500

Ans: C. *The number of pixels is $height*width=250x150=37500$.*

#### Channels

Qn: How many channels are there in an image? Mark all correct statements:

- If it is a grayscale image, the number of channels is 1.

- If it is a colour image and we represent it by RGB (Red, Green, Blue), the number of channels is 3.

- If we represent an image in HSV (Hue, Saturation, Value) format, the number of channels is 3.

- The number of channels is always 3.

Ans: A, B & C. *A greyscale image has single channel. If it is a colour image, and if we represent by RGB (Red, Green, Blue), the number of channels is 3 for Red, Green and Blue. If we represent an image in HSV (Hue, Saturation, Value) format, the number of channels is 3 for Hue, Saturation and Value.*

#### Pixels

Qn: What is the total number of pixels in an image whose dimension is (250,150,3), where ‘3’ represents the RGB channels?

- 250

- 150

- 1,12,500

- 37,500

Ans: D. *The number of pixels is 'width x height', which is 250 x 150, independent of depth.*

#### Values in a channel

Qn: What is the range of possible values of each channel of a pixel if we represent each pixel by 8 bits?

- -254 to 255

- 0 to 255

- 0 to 128

Ans: B. *$2^8\text{(bits)}=256$. So, the range is 0 to 255.*

#### Reading Digital Images

Qn: In a grayscale image, which colours represent 0 and 255?

- White-255, Black-0

- Black-255, White-0

Ans: A. *Lowest intensity - '0'  is black and the highest intensity - '255' is white.*

#### Pixels

Qn: What do the numbers signify in the pixel?

- Intensity of a colour

- Density of a colour

Ans: A. *Each number in pixel represents intensity. If it's '0', it means black with no intensity and '255' means white with the highest intensity.*

Now that you know how CNNs will leverage the data stored in an image, you will next see how one can perform video analysis using the features extracted by a CNN network.