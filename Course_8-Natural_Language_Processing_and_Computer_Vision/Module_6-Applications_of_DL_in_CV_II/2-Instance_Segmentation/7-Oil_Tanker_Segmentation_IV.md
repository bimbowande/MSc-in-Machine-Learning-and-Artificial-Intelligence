# Oil Tanker Segmentation - IV

Now you have the raw images and the annotation file ready for the purpose of model training. As part of the case study, you will be working with an existing repository built for Mask R-CNN architecture, which will be modified for the task of oil tanker segmentation.

Let’s see how to download the code in the upcoming video.

**VIDEO**

There are two steps implemented in the video above.

1.  The first step clones the code for Mask R-CNN into the Colab environment. This template will now be altered to suit the requirements of the case study.
2.  Next, the second step helps in downloading the weights of the model trained on the COCO data set for the process of transfer learning. These parameters will be the initial weights during the training process.

  
With the model and the initial weights, you can now start with the process of model training. However, you must note that you are working with a pre-written code to train the Mask R-CNN model. This is the general template to perform the task of instance segmentation. Therefore, the process will require you to make some adjustments to make the code suitable for your use case. The following conditions must be met before the training process starts:

-   The data set format must be consistent with the template code used to read and process the images.
-   The model parameters (like input size, classes, number of classes, etc.) must be tuned to suit the requirements of the final objective.

These steps are mandatory if you are working with a pre-written code. So, let’s see how to do this in the video below.

**VIDEO**

_Note: The code covered in the video above is used for demonstration purposes only as the further discussion is out of the scope of this module._

The data set has now been transformed into the required format. You can even obtain the chips and the associated masks using the user-defined functions. Both the training and the validation sets are now ready for model training. However, as an additional step, you can also implement data augmentation to prevent overfitting. Data augmentation creates separate copies of the image after introducing variations in scale, position, rotation, etc. Let’s see this in the upcoming video.

**VIDEO**

After implementing data augmentation, the model will have multiple copies of the same image to aid the training process. Now, the next segment will deal with the steps for configuring the model for oil tanker segmentation.