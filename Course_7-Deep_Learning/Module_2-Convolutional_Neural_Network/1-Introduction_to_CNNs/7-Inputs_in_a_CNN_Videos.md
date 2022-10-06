# Inputs in a CNN - Videos

In this segment, you will understand the process of video analysis using CNNs. A video is basically a sequence of frames where each frame is an image. You already know that CNNs can be used to extract features from an image. Let's now see how CNNs can be used to process a series of images (i.e., videos).

**VIDEO**

Let's summarise the process of video analysis using a CNN + RNN, or recurrent neural network, stack. At this point, you only need to understand that RNNs are good at processing sequential information such as videos (a sequence of images) and text (a sequence of words or sentences). You will study RNN in the next module. 

For a **video classification** task, here's what we can do. Suppose the videos are of length one minute each. If we extract frames from each video at the rate of two **frames per second (FPS)**, we will have 120 frames (or images) per video. These images are then pushed into a convolutional neural network to extract different features from the image. All this information is stored in terms of **feature vectors**. Thus, we have 120 feature vectors representing each video at the end of the CNN framework. 

![Video Classification Task](https://i.ibb.co/KbzS6vh/Video-Classification-Task.jpg)

These 120 feature vectors, representing a video as a sequence of images, can now be fed sequentially into an RNN which classifies the videos into one of the categories. The main point here is that a CNN acts as a feature extractor for images and, thus, can be used in a variety of ways to process images.

#### Video Analysis

Qn: Which of the following network is primarily used for processing sequential information?

- CNN

- RNN

Ans: B. *Recurrent Neural Networks are designed to process sequential information, such as videos (sequence of images), text (sequence of words or sentences), etc.*

In the next few segments, you will study the architecture of CNNs in detail.