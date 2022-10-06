# CIFAR-10 Classification With TensorFlow - III

You explored the images from the CIFAR-10 data set in the previous segment. Now, you will learn how to build a classification model on top of it.

Before jumping into the CNN architecture, you will first build a simple ANN architecture for this purpose. We will later use this to compare how a simple CNN framework performs over the data set with respect to the ANN framework. So let’s get started with the upcoming video.

**VIDEO**

A basic ANN architecture was used to build the classification model. Following are the details:

-   Input layer: 3072 neurons (Image size: 32x32x3)
-   Hidden layer: 1 dense layer with 2^10 (1024) neurons accompanied by ReLU activation
-   Output layer: Dense layer with 10 neurons (10 output classes)

As summarised in the image given below, this simple ANN model did not perform well on the CIFAR-10 data set. The model showed slight improvement when the number of iterations, or the epoch value, was increased. However, even after 10 epochs, the final accuracy of the model was 48%, which was not satisfactory at all. Moreover, the time taken to complete the training process was also quite large, as all the layers had dense connections.

![CIFAR10 ANN Accuracy vs Epochs](https://i.ibb.co/SvJBQtX/CIFAR10-ANN-Accuracy-vs-Epochs.png)
The simple ANN framework did not perform well over the CIFAR-10 data set. In the next segment, you will learn how to build a CNN model for the same.