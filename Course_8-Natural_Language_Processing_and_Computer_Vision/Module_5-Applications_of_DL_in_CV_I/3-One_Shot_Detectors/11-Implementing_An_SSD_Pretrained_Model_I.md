# Implementing An SSD Pretrained Model - I

Now that you are well equipped with the second type of one-shot object detector, SSD, in this segment, we will dive deep into the implementation of the SSD object detector. For this implementation, we will take into consideration another important real-world use case of object detection: Face detection. Here is the problem statement for this detection.

**Problem Statement:** Detect human faces in still images using the SSD configured with the Caffe pretrained model. 

Download the test image given below and upload it on your google drive:

Download [Emmanuel Macron](Emmanuel_Macron.jpeg)

To begin with, we will watch the forthcoming video and understand how to import the important libraries and load the model.

**VIDEO**

First, you need to copy the pretrained model and load the SSD weights from the Github link, as shown below.

```python
# create a directory names model and enter that directory
%mkdir model/
%cd model

# load the pre-trained model and weights
!wget https://raw.githubusercontent.com/georgiosouzounis/face-detection-ssd-caffe/main/model/deploy.prototxt.txt

!wget https://github.com/georgiosouzounis/face-detection-ssd-caffe/raw/main/model/res10_300x300_ssd_iter_140000.caffemodel
 
# move out of the directory once the model is loaded
%cd ../
```

Once you have fetched and loaded the model and pretrained weights, the next step is to import the required libraries, as you have done before. You can do this with the code given below.

```python
# import the relevant libraries
import numpy as np
import cv2 # openCV

# check the opencv version
if cv2.__version__ < '4.5.2':
  print("opencv version: ", cv2.__version__)
  print("please upgrade your opencv installation to the latest")

# if the openCV version is < 4.4.0 update to the latest otherwise skip this step
!pip install opencv-python==4.5.2.52
```

Now, as you did in the YOLO pretrained model implementation, if the model version is below 4.4.0, then you need to run the last step of the code above and restart runtime before proceeding with the implementation. After restarting runtime, re-run the steps performed so far and then proceed ahead.

Now, you can read and initialise the model as shown below.

```python
# load the serialized model from the local copy in model/
model_cfg = "model/deploy.prototxt.txt"
model_weights = "model/res10_300x300_ssd_iter_140000.caffemodel"

# read the model
detector = cv2.dnn.readNetFromCaffe(model_cfg, model_weights)
```

Note: Before reading the image, make sure that you copy the path of the image in your google drive and paste it in the first line in the code snippet below. 

Next, you will read and visualise the test image as shown in this code snippet.

```python
# Upload the test image provided into your drive and copy the path
%cp /content/drive/MyDrive/macron.jpg .

test_img = "macron.jpg"

from google.colab import drive
drive.mount('/content/drive')

# load the test image and create an image blob
image = cv2.imread(test_img)
(h, w) = image.shape[:2]

# display the image 
from google.colab.patches import cv2_imshow
cv2_imshow(image)
```

Once you have implemented the code above, you will be able to visualise the test image as shown below.

![Emmanuel Macron](https://i.ibb.co/2dV4fHw/Emmanuel-Macron.jpg)

So, now that you have imported the libraries, set up the environment and read the test image, you can now deploy the pretrained model and test the input image for the objects detected. You will learn how to do this in the next segment.