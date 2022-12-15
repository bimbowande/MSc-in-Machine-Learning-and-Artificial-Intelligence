# Image Segmentation vs Object Detection

Image segmentation divides the entire image into different segments. It focuses on labelling each pixel as a particular class of interest. Let us now try to understand how this is different from object detection. 

**VIDEO**

Image segmentation is an extension of the concept of object detection in the field of computer vision.

![Image Segmentation vs Object Detection](https://i.ibb.co/DR2sqM0/Image-Segmentation-vs-Object-Detection.png)

_Source: Jeremy Jordan – ([www.jeremyjordan.me/semantic-segmentation/](http://www.jeremyjordan.me/semantic-segmentation/))_

In object detection, the algorithm is able to detect and identify the position of the object in the image. For example, you will be able to draw and label a bounding box around the person in the image above. However, image segmentation takes this concept a step further. Instead of drawing a box with the class label around the object, it tries to map each pixel under the available segments. It is very helpful in cases where you want to understand the shape or the structure of the desired object in the image. This remains absent in the case of object detection as the bounding boxes are always rectangular in nature.

#### Image Segmentation

Qn: Which of the following cases does not require the application of image segmentation?

- Recognising a person in an image

- Estimating the forest coverage through an image

- Detecting an animal in the image

- Detecting a tumor in the brain

Ans: A C & D. *These tasks can be achieved using object detection as you do not need pixel-level segmentation.*

Now that you understand the basic process of image segmentation, let’s try to get an overview of how the loss function adapts to optimise this new problem.

**VIDEO**

_**Note**: The sum of all the probabilities associated with different classes in the predicted pixel value should be 1. There is a small error in the video as the overall sum exceeds 1._

The process of image segmentation results in a **segmentation map** where the height and width of the output are similar to the input (can differ based on the used architecture; covered later), but the depth is equal to the number of class labels. 

![Segmentation Map](https://i.ibb.co/cLF3Xsj/Segmentation-Map.png)

You can think of image segmentation as a classification problem where each pixel is classified as a specific class. Therefore, the most commonly used loss function here is a **pixel-wise cross-entropy loss**. This loss examines each pixel individually and compares the results with the class labels provided by the user as input. The result for each pixel is then aggregated in order to check the overall efficiency of the model.

![Pixel-Wise Cross-Entropy Loss](https://i.ibb.co/C7dKPvN/Pixel-Wise-Cross-Entropy-Loss.png)

Question 1/2

Mandatory

#### Image Segmentation

Qn: Suppose that you are provided with the task of segmenting a satellite image into the following sections:

-   Buildings,
-   Trees,
-   Waterbody

How many channels will be present in the final segmentation mask? Please assume that the image has additional segments which cannot be classified under the above-mentioned categories.

- 3

- 4

- 5

Ans: B. *The segmentation mask will have four channels, one for each object (buildings, trees, waterbody) and another for the background.*

#### Image Segmentation

Qn: Based on the segmentation map provided below, the pixel belongs to which of the following classes?

![Image Segmeentation Class Probabilities](https://i.ibb.co/smd128f/Image-Segmeentation-Class-Probabilities.jpg)

- 1

- 2

- 3

- 4

Ans: B. *The probability for this class is maximum in the segmentation map.*

The above elements were meant to provide a very basic understanding of the loss function in the case of image segmentation. You will learn more about this concept in future segments. As part of the next segment, you will learn about the different types of image segmentation.