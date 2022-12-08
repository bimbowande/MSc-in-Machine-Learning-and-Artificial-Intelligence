# Introduction to Object Detection

Before we get started with object detection, we will take a quick look at image classification, with which you are already familiar. In the forthcoming video, you will learn how image classification and object detection differ.

**VIDEO**

Given an image, **image classification** will be able to categorise the objects inside it into different classes. However, **object detection** algorithms would not only be able to classify the objects, but also provide you with their locations in the image. Let’s take this image as an example to understand the difference better.

![Object Detection](https://i.ibb.co/0M9HT7z/Object-Detection.jpg)

Let us try and understand the difference between the outputs of the two algorithms in the context of the image above:

1.  Image classification algorithms analyse images and the objects present inside them, and then divide them into different classes: 
    1.  A binary classifier, as the name suggests, will be able to categorise the objects in the above image into two classes, vehicle or not, and so on.
    2.  A multiclass classifier, on the other hand, will be able to categorise objects into multiple classes and tell whether the object present is a car, bus, bike, etc.  
2.  The output in the case of object detection will include these classes along with the locations of the car, bus and bike, as shown below.
    
    ![Object Detection Boxed](https://i.ibb.co/9wDKQ5W/Object-Detection-Boxed.png)
    
The image that you see above shows **traffic surveillance**, which is a common application of object detection. Object detection covers a wide range of applications some of which are mentioned below.

1.  **Medical imaging**: Object detection is a commonly used technique that detects the presence of unwanted, harmful cells by analysing images of the human brain, lungs, etc. It is also shown to detect the presence of moles as shown below,
  ![Medical Imaging](https://i.ibb.co/hLzKqV1/Medical-Imaging.png)
    
2.  **Remote sensing**: This refers to detecting objects from the images captured by satellites. The image below shows one such example, where an oil tanker is being detected from a satellite image.

    ![Remote Sensing](https://i.ibb.co/VQ5G1J8/Remote-Sensing.png)
    
3.  **Self-driving cars**: One of the actively discussed and newest innovations in technology, self-driving cars, use object detection algorithms to detect obstacles on roads. The image below shows the dashboard of a self-driving car, which uses this technology.
    
    ![Self-Driving Cars](https://i.ibb.co/1MDBYPs/Self-Driving-Cars.jpg)
    
4.  **Face recognition**: Another common application of object detection is detecting human faces. The image below depicts this application.
    
    ![Face Recognition](https://i.ibb.co/ryGLmML/Face-Recognition.jpg)
    
5.  **Traffic monitoring**: Traffic monitoring is one of the widely used applications of object detection. You already saw, at the beginning of this segment, how object detection detects the presence of different vehicles, along with their classes.
    
    ![Traffic Monitoring](https://i.ibb.co/9wDKQ5W/Object-Detection-Boxed.png)
    

The coloured boxes that you see around the objects in this image are called **bounding boxes**. These boxes provide the coordinates of the objects detected inside an image. You will learn about them in detail in the upcoming segment where you will learn about the concept of **object localisation**.