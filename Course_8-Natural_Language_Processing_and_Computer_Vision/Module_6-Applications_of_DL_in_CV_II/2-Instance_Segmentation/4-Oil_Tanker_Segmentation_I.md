# Oil Tanker Segmentation - I

After learning about the basics of Mask R-CNN, it is now time to use the architecture in a practical demonstration. As part of this case study, you will learn how to build a Mask R-CNN model to segment oil tankers present in satellite images. As mentioned before, asset mapping is one of the key applications of image segmentation and this case study will help you implement it for mapping oil tankers present in the input image.

You will be working with Google Colab as part of this demonstration. The notebook used here can be downloaded from the following link.

Download [Mask R-CNN_Oil Tanker](Mask_RCNN_Oiltanks.ipynb)

Instructions:

-   Note that the runtime must be changed to ‘GPU’ for the purpose of this demonstration.
-   You must run the code along with Georgios for a complete understanding of the concepts. However, you can skip the training process as it will take hours to complete. 

Let’s get started with the process by defining the Colab environment in the upcoming video.

**VIDEO**

As mentioned in the video, you must change the runtime to GPU before you proceed with the case study. Moreover, the code for Mask R-CNN works well with the specific versions of the mentioned libraries. Therefore, you must run the provided commands before proceeding ahead.

Once you have installed the required libraries, the next step is to get the data set in the Colab environment. The upcoming video covers the steps to perform this task.

**VIDEO**

Since you will be working with a Kaggle data set, the above video uses the Kaggle API to download the data set directly into the Colab environment. The data is downloaded as a zip file which is later extracted in the ‘dataset’ folder. Lastly, the path of the folder is stored in a variable for future reference.

Once you have the required data, the next step is to prepare the data for the preferred architecture. In our case, it is the Mask R-CNN framework. Georgios will walk you through the required steps in the video below.

**VIDEO**

As highlighted in the video, you must perform the following general steps before proceeding with model building:

-   **General tasks (These tasks are required for every case.)**
    -   The images must be resized for the architecture to process them faster. However, this must be done without sacrificing spatial resolution.
    -   The data set must be split into training and validation sets for model training and evaluation purposes.
    -   The annotation file associated with the training and the validation set must be in the designated format. As part of this case study, the MS COCO format must be followed as the pre-trained architecture is based on the same.
-   **Specific to the problem**
    -   The provided data set contains the raw images and the data associated with the class labels and the bounding boxes. It doesn’t store the pixel masks for the input images. So, the case study will also equip you with the steps to generate the masks from the bounding box to perform image segmentation.

#### Mask R-CNN

Qn: Which of the following components are essential for **training** an instance segmentation model using the Mask R-CNN architecture?

- Training set

- Validation set

- Annotated masks

Ans: A & C. *Training set is essential in the training process as the model will definitely need images. The model will need information about the classes, bounding box and segmentation masks in order to train the model.*

After the required steps have been completed, all the files must be stored properly in the designated folders. The video highlights the directory structure that must be followed. One key point is that the annotation file must be stored along with the raw images in both the training and the validation sets, which will be split in the ratio of 9:1 for this exercise.

You will now learn how to implement these steps in the upcoming segments.
