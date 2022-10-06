# Transfer Learning Using TensorFlow - II

In this segment, you will be conducting the following experiments to improve the performance of the model:

-   Retraining the frozen layers for adaptation
-   Altering the epochs or the learning rate
-   Adding more layers in the architecture

There are other ways as well to improve the performance, but we will visit only the ones mentioned above. Let’s now proceed with the steps for the same.

**VIDEO**

The video covered two experiments, which have been summarised below:

#### Experiment 2: Retraining the frozen layers for adaptation
The accuracy of the model over the training and the testing data has significantly improved after retraining the initial layers. This helps the architecture to adapt to the new data set and extract the required features for better performance.

#### Experiment 3: Altering the learning rate (with retraining)
As the model was developed for a similar task, we should use a small learning rate. This is because we do not expect the weights to change drastically (we expect them to have learnt some generic patterns and want to tune them only a little to accommodate for the new task).

![Altering the learning rate (with retraining)](https://i.ibb.co/qMtwSfB/Altering-the-learning-rate-with-retraining.jpg)

Next, we will try and see if adding more dense layers helps in improving the model performance.

**VIDEO**

#### Experiment 4: Adding more trainable dense layers (freezing initial layers)  
The simple addition of dense layers does not result in the betterment of the model with a small number of epochs. You can increase the epochs and experiment to see whether the model shows improvement or not. 

![Adding more trainable dense layers (freezing initial layers)](https://i.ibb.co/tHwms32/Adding-more-trainable-dense-layers-freezing-initial-layers.jpg)

So far, you have experimented with the VGG19 architecture. The model trained on the ImageNet challenge provided good results when the initial layers were retrained. In our final experiment, we will explore another network, ResNet, and check its performance over the CIFAR-10 data set.

**VIDEO**

#### Experiment 5: ResNet50
In the last experiment, we froze all the layers in the functional block (i.e., used the pretrained ResNet weights) and trained the rest of the layers. The model performed poorly on the data set and, hence, will require a lot of experimentation to reach an optimal level.

![ResNet50](https://i.ibb.co/TPnxjQ6/ResNet50.jpg)

These experiments form the essential part of the process and should be conducted diligently to arrive at the best model for the task at hand. In case we were not satisfied with the results, we could modify the network further (add an FC layer, modify the learning rate, replace the global average pooling layer with max pool, etc.) to reach the desired level.

In the next segment, you will go through an interesting paper that compares various CNN architectures from an efficiency and deployment point of view.