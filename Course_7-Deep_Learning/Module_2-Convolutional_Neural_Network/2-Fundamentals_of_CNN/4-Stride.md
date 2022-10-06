# Stride

In the previous segment, the filter was moved by exactly one pixel (both horizontally and vertically) while performing convolutions. However, it is not the only way to do convolutions. You can move the filter by an arbitrary number of pixels based on the task requirement. This concept is known as **stride**.

Watch the next video to learn this concept in detail.

**VIDEO**

As you learnt in this video, there is nothing sacrosanct about the stride length 1. You can alter the stride value based on your underlying objective. 

![Convolution Visualisation](https://i.ibb.co/7Nx94BR/Convolution-Visualisation.gif)       ![Convolution Visualisation 2](https://i.ibb.co/3mBnHw3/Convolution-Visualisation-2.gif) 

**(Left: Stride = 1 ; Right: Stride = 2)**

If you increase the stride value, some of the information will be lost in translation from one layer to another. If you think that you do not need many fine-grained features for your task, you can use a higher stride length (2 or more).

Let's discuss this in detail through an example.

**VIDEO**

As you can see, a higher stride value also results in the same result. The benefit of increasing the stride length is that it results in faster processing and less information is translated between the layers. Let’s understand this concept through the image provided below.

![Strides](https://i.ibb.co/0yj06BC/Strides.jpg)

_(Source: www.terraprints.com)_

-   **Case 1:**  
    In the first case, suppose you are building a CNN model to identify the presence of any water body in a given satellite image. This task can be done smartly by not exploring each and every pixel of the image. The output will be ‘yes’ if the object is found in any part of the image. Hence, you can skip a few pixels and save both time and computational resources in the process.
-   **Case 2:**  
    Suppose you are building a model on the same image to extract the region covered by the water body in the given area. Here, you will be expected to closely map the entire structure of the water body, and hence, you would need to extract all the granular elements from the image. Therefore, the stride value should not be kept high.

So, depending on the use case, you must use the appropriate stride value.

#### Stride

Qn: Which of the following problems can be handled using a large stride value?

- Performing facial recognition on an image

- Classifying the scenery of an image as a landscape

Ans: B. *Here, an overview of the image can also help in identifying the scenery. So, a large stride value can be used.*

In the next segment, you will learn another important concept associated with the convolutional layer, that is, padding.