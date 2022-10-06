# Transfer Learning With Pre-Trained CNNs

By now, you have a basic understanding of how transfer learning can be helpful in solving different computer vision problems. You now know that a pretrained model, such as AlexNet, VGGNet, GoogleNet or ResNet, can be used to build a model for your specific tasks. However, the elements around ‘how’ are still not clear.

Let’s hear about the implementation of transfer learning in the upcoming video.

**VIDEO**

As mentioned in this video, the initial layers of a CNN architecture extract the basic features, the latter layers extract more abstract features, while the last few layers simply discriminate between images. As the entire process is well separated, the initial layers that are responsible for extracting the features can be simply picked and put to use in another use case. In other words, the initial few layers are able to extract generic representations of an image and, thus, can be used for any general image-based task.

![Feature Vectors](https://i.ibb.co/ftQqvQw/Feature-Vectors.jpg)

Following are two commonly used ways of using pretrained nets for transfer learning:

- **Freeze the (weights of) initial layers and train only a few latter layers**: In this method, you use the same weights and biases that the network has learnt from some other task, remove the few last layers of the pretrained model, add your own new layer(s) at the end and train only the newly added layer(s).

![Freeze the (weights of) initial layers and train only a few latter layers](https://i.ibb.co/g4tXFJC/Freeze-the-weights-of-initial-layers-and-train-only-a-few-latter-layers.jpg)

- **Retrain the entire network (all the weights) initialising from the learnt weights**: Here, all the layers undergo the training process. However, the method uses the weights and biases from the source model for initialising the training process. Since you do not want to unlearn a large fraction of what the pretrained layers have learnt, the learning rate for the initial layers is kept quite low. This is to avoid large jumps during the process of gradient descent.

![Retrain the entire network all the weights initialising from the learnt weights](https://i.ibb.co/Ry8rSDt/Retrain-the-entire-network-all-the-weights-initialising-from-the-learnt-weights.jpg)

Both the methods have their advantages and disadvantages. The first method provides faster results due to reduced operations, but intuitively, the second method is more suited for the task, as it performs additional learning on top of the existing architecture.

When you implement transfer learning practically, you will need to make these decisions, such as how many layers of the pretrained network to throw away and train yourself. Let's see how one can answer these questions. 

**VIDEO**

To summarise:

-   If the task is a lot similar to what the pretrained model had learnt from, you can use most of the layers except the last few layers, which you can retrain.
-   If you think there is less similarity in the tasks, you can use only a few initial trained weights for your task.

![Transfer Learning Model Decisions](https://i.ibb.co/2S2jT1z/Transfer-Learning-Model-Decisions.jpg)

In the next segment, you will go through a demonstration of transfer learning using TensorFlow and Keras.