# Oil Tanker Segmentation - VI

This segment will help you train the Mask R-CNN architecture for oil tanker segmentation. As mentioned in the previous segment, you will run different versions of the model to obtain the most optimal model.

The upcoming video will cover the first model, that is, training the initial layers with a higher learning rate.

**VIDEO**

## Experiment 1  

The model was trained using the following parameters:

-   Learning rate: 0.0002
-   Epochs: 6
-   Layers: Head (FC layers were not trained)

The loss for the training set reduces with the increase in the number of epochs, however, in the case of the validation set, the loss tends to rise after a particular point. Therefore, the model needs modifications to improve its performance.

Let’s move to the next experiment where the learning rate has been decreased and the number of epochs has increased.

**VIDEO**

The above video covered two different experiments.  
 
## Experiment 2

The model was trained using the following parameters:

-   Learning rate: 0.0001
-   Epochs: 12
-   Layers: All

This experiment shows similar results as experiment 1. The loss function has reduced but increases after a particular point. In the next experiment, the learning rate is reduced for further epochs on top oof the previous model.

## Experiment 3

The model was trained using the following parameters:

-   Learning rate: 0.00002
-   Epochs: 24
-   Layers: All

The model is not able to achieve the targeted loss of 0.2. However, the model has shown improvement from its predecessors. The model can further be improved by altering different parameters like learning rate,  dropout layers, normalization layers, etc. which can be explored at your end. 

Lastly, let’s try to understand the performance of the model through the plots.

**VIDEO**

As you can see, the loss curve for training and validation sets follow a similar pattern. However, the model seems to be stagnant at a particular point and would need further adjustments in the model parameters in order to improve further.

Now that you have the results of three different experiments, the next segment will help you with the process of model implementation and inference.