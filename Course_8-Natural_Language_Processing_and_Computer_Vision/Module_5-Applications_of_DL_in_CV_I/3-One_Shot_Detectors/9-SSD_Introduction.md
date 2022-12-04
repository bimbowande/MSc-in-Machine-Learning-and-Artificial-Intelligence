# SSD - Introduction

In this segment, you will learn about another one-shot detector: **SSD**. SSD stands for single-shot detector. 

As the name suggests, similar to the YOLO detector, SSD uses a single pass to detect the presence of objects in the input image. You will learn more about this algorithm from Georgios in the forthcoming video.

**VIDEO**

The SSD algorithm consists of two main parts:

1.  A neural network at the base and
2.  Convolutional layers.

The neural network works as a **feature extractor**. The SSD uses a VGG-16 network, which is a CNN of superior quality. However, it does not use the output layers of this CNN, which are used for classification in the image classification process.

  
The convolutional layers work as **object detectors**. They locate bounding boxes and classify the objects present in an image. These layers reduce the size of images as they pass through them, thus allowing the network to detect objects at different scales.

  
Now, we will try to understand the working of this algorithm step by step:

1.  First, the feature extractor, VGG-16, provides the feature maps of the input image.  
     
2.  Next, the convolutional layers detect objects at different scales and provide **four predictions per cell.**  
     
3.  Each prediction comprises:
    1.  The boundary box coordinates,
    2.  _'c'_ class scores,  
        where c is the number of classes ie., 21 for this example, and
    3.  An extra class for no object being detected.  
         
4.  The class with the highest score is said to be the class of the object being bound.  
     
5.  This technique of making multiple predictions for each object is called **multibox**.

The image below shows the working of multibox techniques. 

![Multibox Techniques](https://i.ibb.co/9h14qyW/Multibox-Techniques.png)

Now, based on your understanding of the SSD, answer this question.

#### SSD

Qn: Which of these statements about the SSD is incorrect?

- It is also known as a multibox detector.

- It detects an object only at one scale in any given image.

- It detects both the class and the bounding box coordinates in a single pass.

- It uses the VGG-16 CNN.

Ans: B. *SSD detects objects at multiple different scales.*

So, now that you have a basic understanding of the algorithm, in the next segment, you will learn about the working and the architecture of the SSD algorithm in depth.
