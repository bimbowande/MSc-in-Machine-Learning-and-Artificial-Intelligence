# Transfer Learning Using TensorFlow - I

In this segment, you will learn how to implement transfer learning using Keras in Tensorflow. For this, you will be using the same CIFAR-10 data set. However, instead of working with a basic CNN architecture, you will be using pretrained networks to classify the objects.

Let’s hear about it from Ajay in the upcoming video.

**VIDEO**

You will be using the pretrained VGGNet and ResNet architectures trained on the ImageNet challenge to classify the different images present in the CIFAR-10 data set. This is possible because the tasks performed here are quite similar in nature. During the entire demonstration, we will conduct multiple experiments by altering different elements of the architecture. So let’s get started.

**VIDEO**

So, you will be first using the VGG19 architecture (pretrained on the ImageNet challenge) to classify the images of the CIFAR-10 data set.

**Experiment 1: Freezing the initial layers**

The screenshot given below summarises the model used for this experiment.

![Freezing the Initial Layers Model Summary](https://i.ibb.co/714QBqc/Freezing-the-Initial-Layers-Model-Summary.jpg)

As mentioned, we have removed the previously trained dense layers from the original VGG19 architecture and added our own fully connected and a Softmax layer for classification purposes. Moreover, the parameters of the functional block are frozen, and the total number of trainable parameters include only the new dense layers that have been added on top.

Now that the model is ready, you will follow the same steps to train the model in the next video.

**VIDEO**

The graph provided below summarises the performance of the model.

![Model Performance](https://i.ibb.co/YjZgPhS/Model-Performance.jpg)

As you can see, the model does not seem to perform very well on the CIFAR-10 data set. Both the train and the test accuracies are quite low. There could be numerous reasons for this, such as the following:

-   Variation in image size: The original architecture was designed for 224x224 images. However, the model is now provided with 32x32 images.
-   Fewer trainable layers and epochs: The present model has only one trainable layer, which is trained over five iterations. Therefore, the network might not be able to adapt to the provided data set.

Since we are not satisfied with the model, we will try to alter different elements of the architecture to improve its performance, in the next segment.