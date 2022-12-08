# Summary

The upcoming video summarises the learning from this session.

**VIDEO**

The session focused on instance segmentation and explained the concepts of Mask R-CNN. Mask R-CNN architecture is an extension of the Faster R-CNN and provides the following elements as output:

-   Bounding box
-   Segmentation mask
-   Class label with a confidence score

![Mask R-CNN](https://i.ibb.co/WkW0JBC/Mask-R-CNN.jpg)

The session covered the following components of the architecture:

-   Backbone
-   Regional Proposal Network (RPN)
-   Region of Interest (RoI)
-   Classifier and Regressor
-   Segmentation mask

Post the theoretical understanding, the session covered the oil tanker segmentation over the satellite images using Mask R-CNN. The process involves two different sets of operations:

-   Data preparation
-   Model preparation

As part of data preparation, you learnt how to generate the annotation for the masks in an image segmentation task. Moreover, the session covered the different requirements to be fulfilled before training the model. Next, you cloned the required code repository for the Mask R-CNN model where the configuration file was updated to suit the requirements of the expected task.

Once the required preparations were done, the model was put under training with three different experiments. Finally, the best weights were selected in order to implement the model on the unseen images.