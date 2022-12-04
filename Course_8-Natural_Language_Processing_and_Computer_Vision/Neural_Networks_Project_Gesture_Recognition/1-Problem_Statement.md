# Problem Statement

Imagine you are working as a data scientist at a home electronics company that manufactures state of the art **smart televisions**. You want to develop a cool feature in the smart-TV that can **recognise five different gestures** performed by the user which will help users control the TV without using a remote.

The gestures are continuously monitored by the webcam mounted on the TV. Each gesture corresponds to a specific command:

-   Thumbs up:  Increase the volume
-   Thumbs down: Decrease the volume
-   Left swipe: 'Jump' backwards 10 seconds
-   Right swipe: 'Jump' forward 10 seconds  
-   Stop: Pause the movie

In this assignment, you need to create a deep learning-based model which can accurately capture different gestures of the user using the incoming video from the camera. Each video is a sequence of 30 frames (or images). In the next couple of lectures, our subject matter expert Snehansu will walk you through the structure of the dataset.

**VIDEO**

The gestures are continuously monitored by the webcam mounted on the TV. Each gesture corresponds to a specific command:

-   Thumbs up:  Increase the volume
-   Thumbs down: Decrease the volume
-   Left swipe: 'Jump' backwards 10 seconds
-   Right swipe: 'Jump' forward 10 seconds  
-   Stop: Pause the movie

Each video is a sequence of 30 frames (or images). In the next couple of lectures, our subject matter expert Snehansu will walk you through the structure of the dataset.

## **Understanding the Dataset**

The training data consists of a few hundred videos categorised into one of the five classes. Each video (typically 2-3 seconds long) is divided into a **sequence of 30 frames(images)**. These videos have been recorded by various people performing one of the five gestures in front of a webcam - similar to what the smart TV will use. 

In the following lecture, Snehansu will walk you through the problem statement and the dataset in detail.

**VIDEO**

The data is in a zip file. The zip file contains a 'train' and a 'val' folder with two CSV files for the two folders. These folders are in turn divided into subfolders where each subfolder represents a video of a particular gesture. Each subfolder, i.e. a video, contains 30 frames (or images). Note that all images in a particular video subfolder have the same dimensions but different videos may have different dimensions. Specifically, videos have two types of dimensions - either 360x360 or 120x160 (depending on the webcam used to record the videos). Hence, you will need to do some pre-processing to standardise the videos. 

Each row of the CSV file represents one video and contains three main pieces of information - the name of the subfolder containing the 30 images of the video, the name of the gesture and the numeric label (between 0-4) of the video.

Your task is to train a model on the 'train' folder which performs well on the 'val' folder as well (as usually done in ML projects). We have withheld the test folder for evaluation purposes - your final model's performance will be tested on the 'test' set.

To get started with the model building process, you first need to get the data on your storage. 

In order to get the data on the storage, perform the following steps in order

1. Open the terminal
2. g0 down [https://drive.google.com/uc?id=1ehyrYBQ5rbQQe6yL4XbLWe3FMvuVUGiL](https://drive.google.com/uc?id=1ehyrYBQ5rbQQe6yL4XbLWe3FMvuVUGiL)
3. unzip Project_data.zip
    

Now that you have got the data on the storage, let's look at the different choices of architectures you can use.