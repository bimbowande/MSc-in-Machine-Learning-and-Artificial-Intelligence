# Lung Segmentation using U-Net - I

Till now, the session was focused on the theoretical understanding of the U-Net algorithm. Now, you will learn how to use the framework to perform semantic segmentation over a collection of chest X-ray images. As discussed before, semantic segmentation finds great application in the field of medical imaging. Moreover, the U-Net architecture was developed by Olaf Ronneberger, Philipp Fischer, Thomas Brox for the purpose of biomedical image segmentation. 

You will be working with Google Colab as part of this demonstration. The notebook used here can be downloaded from the following link.

Download [U-Net_Lung_Segmentation](UNet_Lung_seg.ipynb)

Instructions:

-   Note that the runtime must be changed to ‘GPU’ for the purpose of this demonstration.
-   The code developed as part of this exercise is only for demonstration purposes.
-   You must run the code along with Georgios for a complete understanding of the concepts.  
     

The final objective of this demonstration is to build a semantic segmentation model that can segment the lungs in a chest X-ray image. Let’s get started with the process of loading the data into the Colab environment in the upcoming video.

**VIDEO**

The above video covered the following steps:

1.  Installing the Kaggle API to download the data set.
2.  Defining the directories to store the data.

Kaggle API allows you to download and load the data set directly into the Google Colab notebook. Once you have established the connection with the Kaggle API, you can use the following code to download the data set: 

```python
!kaggle datasets download '<user_name>/<data_set_name>'
```

_**Note**: The user_name above corresponds to the account which holds the dataset._

As you have learnt before, you will need the following items to perform the segmentation task:

-   Raw images (training and testing set)
-   Annotation masks for each image

Therefore, the next step is defining the directories to store each element separately. Moreover, a temporary directory is also created to ease the process ahead.

Now, you have the data and the directories ready. Let’s try to extract and explore the data in the upcoming video.

**VIDEO**

As mentioned in the video, the zip file contains the raw images and the information of the masks associated with each of them. Therefore, the files are moved into the required directories for further processing.

_Note: The zip file is deleted to optimize the use of the limited storage provided under Google Colab. Kindly ensure that this step is followed correctly._ 

#### Lung Segmentation

Qn: Suppose you are segmenting the left and right sections of the lungs separately. How many values will you require to map each pixel into the required classes?

- 2

- 3

- 4

Ans: B. *There are three classes (left lung, right lung and background) so you will need three values to represent each class.*

At this stage, you have the data set present in the required directories. However, the data set obtained from Kaggle is raw and must be prepared according to the requirements of the algorithm. The next segment will help in performing the same.