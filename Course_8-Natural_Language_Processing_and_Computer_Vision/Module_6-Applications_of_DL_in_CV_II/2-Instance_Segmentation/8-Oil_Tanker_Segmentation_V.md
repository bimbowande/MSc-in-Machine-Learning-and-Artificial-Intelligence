# Oil Tanker Segmentation - V

The previous segments focused on preparing the data for the task of oil tanker segmentation. Now, you will modify the parameters associated with the model using the config file.

Georgios will walk you through each parameter and help in making the required changes in the upcoming video.

**VIDEO**

The model is now tuned to perform the task of oil tanker segmentation. Some of the key model parameters are listed below:

-   Backbone (ResNet50, ResNet101, etc.)
-   Number of classes
-   Computational parameters like the size of the GPU, batch size, etc.

You can refer to the results of the above code for more parameters that can be configured. Finally, they are stored in the variable ‘config’ which will be used to define the model in the next video.

**VIDEO**

The final model is now ready for training. The config class is used to set the model parameters. Moreover, the model is also initialised with the weights from the COCO dataset. The model summary highlights that the architecture runs very deep and there are approximately 44.66 million parameters to be learnt during the training process. Let’s now proceed with training the model.

As part of the case study, the training process will be implemented multiple times after altering a few parameters like learning rate, trainable layers, etc. to obtain an optimal model.  Let’s hear about these experiments before you proceed ahead.

**VIDEO**

The following three experiments will be conducted as part of the case study:

-   Training the initial layers with a higher learning rate.
-   Training all the layers with a higher number of epochs.
-   Training all the layers with a higher number of epochs and decreasing learning rate.

Now that you are aware of all the experiments, the next segment will cover them in detail.