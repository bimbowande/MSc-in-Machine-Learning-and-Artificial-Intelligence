# Lung Segmentation using U-Net - III

The previous segment helped you prepare the data based on the U-Net library requirements. All the images in the data set have a corresponding mask image which also follows the required naming convention. Now, this segment will deal with all the steps associated with model building, training and evaluation.

Let’s start with the process of defining the model. Please note that we will not be building the model from scratch as part of this exercise. The U-Net architecture for this purpose can be loaded from the GitHub repository. The upcoming video will guide you through the process.

**VIDEO**

The following steps were covered in the above video:

1.  Cloning the GitHub repository for U-Net architecture
2.  Resizing the input images for the model
3.  Loading the U-Net architecture from the cloned repository
4.  Importing and instantiating the VGGNet as the base for the U-Net model

#### Lung Segmentation

Qn: The original images in the dataset were resized to smaller dimensions before the process of model training. This is done to:

- Save the storage space of the machine

- Reduce the computation cost of the process

Ans: B. *The architecture has to segment each pixel of the image. The larger number of pixels will require more time to finish the process. Hence, resizing saves the computation costs.*

Qn: You have loaded the VGGNet architecture as the base to build the U-Net model. This means that both the sections (encoder and decoder) use the same architecture. Is it possible that you use a different framework (like ResNet, GoogleNet, etc.) as the decoder, keeping the encoder as VGGNet?

- Yes

- No

Ans: B. *Remember that the two sections in U-Net are interconnected using skip connections. Therefore, you cannot change the sections independently.*

This case study demonstrates the process of transfer learning as you are working with a predefined architecture built by another user. It saves a lot of computation time as you are not expected to define the layers of the architecture and the weights associated with each layer are also loaded along with the architecture.

Let’s try to visualize the model architecture in the video below.

**VIDEO**

As seen in the video, the model uses VGG-16 as the backbone for building the architecture. The visual also highlights the connections between different layers and the parameters associated with them.

Now, you have the model architecture ready for training. During the training process, the network will learn the weights associated with different layers to minimize the loss function. Let’s see how to define the basic parameters to train a model.

**VIDEO**

_Note: The training process will take some time to complete. Please continue with the next video after the training process is complete._

Once the training process is complete, the next step is to perform model evaluation and inference. Let’s see how to perform these steps in the video below.

**VIDEO**

As highlighted in the video, the activity of model evaluation is redundant in this case as the validation set is not defined. The trained model was however used to perform the task of lung segmentation on the test images. As part of the process, you also learnt how to overlay the segmented masks over the original image. The results obtained were satisfactory as the model was able to segment the lungs from the image.

The next segment will summarise your learning from the session.
