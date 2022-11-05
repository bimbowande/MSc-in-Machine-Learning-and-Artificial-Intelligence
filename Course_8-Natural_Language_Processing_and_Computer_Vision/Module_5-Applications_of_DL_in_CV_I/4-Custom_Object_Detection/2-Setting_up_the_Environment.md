# Setting up the Environment

In this segment, you will get started with the process of creating a custom object detector. So far, you have worked with pre-trained algorithms, which means that your model was already trained on a data set and all you were required to do was to provide the test data set and evaluate the results of the model on that unseen data.

However, not all models will be available to you in a pre-trained form. While working on a new problem or task that has not been solved yet, you will be required to create a custom model catering to your problem statement from scratch. Let’s quickly take a look at the problem statement before proceeding further. 

**Problem statement**  
Build an object detector to predict the presence of face masks on the faces of individuals in images.

Let’s watch the next video to get started with the first step of building the model.

**VIDEO**

As you saw in the video above, the first step is to change the runtime type, which can be done as follows:

Runtime > Change Runtime Type > GPU

The next step is the same as the one you performed for pre-trained models. Take a look at the following code snippet and implement it in your own notebook:

```python
# import the relevant libraries
import numpy as np
import cv2 # openCV

# check the opencv version
print(cv2.__version__)

# if the openCV version is < 4.4.0 update to the latest otherwise skip this step
!pip install opencv-python==4.5.2.52
```

As you did earlier, after updating the version of OpenCV, restart the runtime, import the required libraries and check the OpenCV version to verify that it is properly installed. If the version is greater than 4.4.0, you need not run the last step shown in the code snippet given above, again.

After importing the libraries, the next step is to customise the YOLO algorithm using the **DarkNet Project**. In order to do so, complete the following steps:

```python
# clone the darknet project
!git clone https://github.com/AlexeyAB/darknet.git
 
# enter the darknet directory
%cd darknet
 
# 1st: change settings in the Makefile to enable GPU processing, CUDA and OpenCV
!sed -i 's/GPU=0/GPU=1/g' Makefile
!sed -i 's/CUDNN=0/CUDNN=1/g' Makefile
!sed -i 's/OPENCV=0/OPENCV=1/g' Makefile
 
# verify the changes
!head Makefile
```

Next, open the Makefile by double-clicking on it from the list of files on the left. Scroll down to the 20th line and delete following the lines in bold: 

ARCH = **-gencode arch=compute_35,code=sm_35   
                 -gencode arch=compute_50,code=[sm_50,compute_50]**  
                 -gencode arch=compute_52,code=[sm_52,compute_52]  
                 -gencode arch=compute_61,code=[sm_61,compute_61]

This is done because CUDA no longer supports these GPU architectures. The resultant text block will be as follows:

ARCH= -gencode arch=compute_52,code=[sm_52,compute_52]   
                -gencode arch=compute_61,code=[sm_61,compute_61]

Save the changes that you have made and close the Makefile. Before proceeding to the next step, ensure that you have mounted your Google Drive by clicking on the drive icon, as shown below.

![Colab Connect Google Drive](https://i.ibb.co/QP3xTVj/Colab-Connect-Google-Drive.png)

You can also do this by running the following command:

```python
from google.colab import drive
drive.mount('/content/drive')
```

Once your Google Drive is mounted, you can create a new directory to store all the files that you will be working on, in the upcoming segments. Let’s create this directory using the following code:

```python
# create a my_model directory in google drive
%mkdir ../drive/MyDrive/my_model/
 
# save a copy of Makefile in that directory
%cp Makefile ../drive/MyDrive/my_model/
```

Try answering the question given below:

#### Custom Model

Qn: Before getting started with the code, you set the runtime type to GPU. Which of the following statements is not true regarding GPU?

- GPU is the abbreviation for graphics processing unit.

- GPU allows parallel processing.

- GPU cannot work along with the CPU.

Ans: C. *GPU is highly compatible with CPU. Therefore, they can both work together.*

Now that you have set up the environment required for building the custom model, let’s proceed to the next segment to learn about the next step.