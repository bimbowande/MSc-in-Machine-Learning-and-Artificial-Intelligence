# Introduction to Transfer Learning

So far, we have discussed multiple CNN networks that were trained on millions of images of numerous classes. The ImageNet data set itself has about 1.2 million images of 1,000 classes.

However, what these models have 'learnt' is not confined to the ImageNet data set (or a classification problem). In an earlier session, we discussed that CNNs are essentially feature-extractors, that is, the convolutional layers learn a representation of an image, which can then be used for any task such as classification or object detection. The dense layers at the end of the architecture can be trained based on this required task.

This implies that the models trained on the ImageNet challenge have learnt to extract features from a wide range of images. Can we then transfer this knowledge to solve some other problems as well? 

Let’s try to intuitively understand this with a few basic examples.

**VIDEO**

Thus, **transfer learning** is the practice of reusing the skills learnt from solving one problem to learn to solve a new, related problem. This is a generic concept but is highly leveraged in CNNs.

![**Transfer Learning** is the practice of reusing the skills learnt from solving one problem to learn to solve a new, related problem](https://i.ibb.co/B4KHhQy/Transfer-Learning-is-the-practice-of-reusing-the-skills-learnt-from-solving-one-problem-to-learn-to.jpg)

Before diving into how to do transfer learning, let's first take a look at some practical reasons to do transfer learning.

**VIDEO**

To summarise, some practical reasons to use transfer learning are as follows:

-   Data abundance in one task and data crunch in another related task
    
-   Enough data available for training, but lack of computational resources
    

The example of image captioning helps to understand the first point well.

![Transfer Learning Example Image Captioning](https://i.ibb.co/sg5FThB/Transfer-Learning-Example-Image-Captioning.jpg)

Another example of the first case could be the development of self-driving models in different areas. Suppose you want to build a model (to be used in a driverless car to be driven in India) to classify 'objects' such as a pedestrian, a tree, a traffic signal, etc. Now, let's say you do not have enough labelled training data from Indian roads, but you can find a similar data set from an American city. You can try training the model on the American data set, take those learnt weights, and then train further on the smaller Indian data set. 

Examples of the second use case are more common. Suppose you want to train a model to classify 1,000 classes, but do not have the infrastructure required. You can simply pick up a trained VGGNet or ResNet and train it a little more on your limited infrastructure. You will implement such a task using the Keras library shortly.

In the next segment, you will learn how transfer learning can be executed in the context of CNNs.