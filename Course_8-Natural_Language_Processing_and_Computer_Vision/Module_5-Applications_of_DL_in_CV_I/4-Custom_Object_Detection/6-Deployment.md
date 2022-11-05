# Deployment

Now that your model is trained using images of human faces with and without masks, let’s deploy the model and check if it is able to correctly predict the output on test images. In order to deploy the model, you need to fetch the pre-trained model that you have previously trained.

This process is similar to the one that you followed for the pre-trained models in the previous sessions. Let’s watch the next video to start by setting up the environment and fetching the pre-trained model.

**VIDEO**

Import the required libraries using the following code snippet:

```python
# import the relevant libraries
import numpy as np
import cv2 # openCV
```

Did you notice the version of OpenCV you have used for the previous implementations? Try selecting the correct answer based on your observation.

#### OpenCV

Qn: What version of OpenCV is being currently used?

- 4.5.2

- 4.1.2

- 3.4.12

- 4.2.0

Ans: A. *The current version of OpenCV, which will be used for implementation, is 4.5.2. If required, you can check the version and update it using the following command:*

```python
# check the OpenCV version
print(cv2.__version__)

# if the openCV version is < 4.4.0 update to the latest otherwise skip this step
!pip install opencv-python==4.5.2.52
```

After setting up the environment, you need to mount your Google Drive and implement the following code to fetch the pre-trained model and analyse the previously saved files:

```python
# let us take a look at the backed-up model configuration files
%ls /content/drive/MyDrive/my_model/

# let us take a look at the backed-up model training files
%ls /content/drive/MyDrive/my_model/backup/
 
# import the cv2_imshow as a replacement of cv2.imshow to prevent errors
# let us analyse the training process
from google.colab.patches import cv2_imshow
chart = cv2.imread("/content/drive/MyDrive/my_model/chart_yolov4-23.png")
cv2_imshow(chart)
 
# first create a directory to store the model
%mkdir model
 
# enter the directory and download the necessary files 
%cd model
%cp /content/drive/MyDrive/my_model/backup/yolov4_best.weights .
%cp /content/drive/MyDrive/my_model/yolov4.cfg .
%cp /content/drive/MyDrive/my_model/face_mask_classes.names .
%cd ..
```

The next step is to obtain the testing data. For this, you need to create a directory and store the testing data you need to fetch. Let’s watch the next video to learn about the steps involved in fetching the testing data.

**VIDEO**

As you learnt in the video above, you need to implement the following steps to fetch the test data:

```python
# create a directory for test data
%mkdir test_data

# copy a test file locally or use it directly from the mounted drive 
# customize this example for your drive structure
%cp /content/drive/MyDrive/object_detection/data/test_gko_rs.jpg test_data/
%cp /content/drive/MyDrive/object_detection/data/test_gko_rs_ground_truth.txt test_data/

# access the test data files from GitHub link:
!wget https://github.com/georgiosouzounis/object-detection-yolov4/raw/main/data/custom/test_gko_rs.jpg -O test_data/
!wget https://raw.githubusercontent.com/georgiosouzounis/object-detection-yolov4/main/data/custom/test_gko_rs_ground_truth.txt -O test_data/
```

  
Let’s now read the test image using the following code snippet:

```python
# read file
test_img = cv2.imread('test_data/test_gko_rs.jpg')

# display test image
cv2_imshow(test_img)
```

On running the above command, you will be able to visualise the test image as shown below:

![Face with mask](https://i.ibb.co/qD5c60G/Face-with-mask.png)

Once you have verified the test data, the next step is to convert the data into a blob using the following command:

```python
scalefactor = 1.0/255.0
new_size = (416, 416)
blob = cv2.dnn.blobFromImage(test_img, scalefactor, new_size, swapRB=True, crop=False)
```

  
Now, it is time to customise the YOLO detector by providing class labels and bounding box colours, as shown below.

```python
# Define the class labels
class_labels_path = "/content/model/face_mask_classes.names"
class_labels = open(class_labels_path).read().strip().split("\n")
class_labels
 
# declare repeating bounding box colors for each class 
# 1st: create a list colors as an RGB string array
# Example: Red, Green,
class_colors = ["255,0,0","0,255,0"]
 
# 2nd: split the array on comma-separated strings and for change each string type to integer
class_colors = [np.array(every_color.split(",")).astype("int") for every_color in class_colors]
 
# 3d: convert the array or arrays to a numpy array
class_colors = np.array(class_colors)


Finally, let’s load and run the model using the following commands:
# Load the pre-trained model 
yolo_model = cv2.dnn.readNetFromDarknet('model/yolov4.cfg','model/yolov4_best.weights')

# Read the network layers/components
model_layers = yolo_model.getLayerNames()

# Extract the output layers
output_layers = [model_layers[model_layer[0] - 1] for model_layer in yolo_model.getUnconnectedOutLayers()]

# input pre-processed blob into the model
yolo_model.setInput(blob)
 
# compute the forward pass for the input, storing the results per output layer in a list
obj_detections_in_layers = yolo_model.forward(output_layers)
 
# verify the number of sets of detections
print("number of sets of detections: " + str(len(obj_detections_in_layers)))
```

This brings us to the last step of the implementation process, which is to analyse the results and print the object detected with the bounding box. Let’s watch the next video go through the code for the same.

**VIDEO**

The objective now is to get each object detection from each output layer and evaluate the algorithm's confidence score against a threshold. For high confidence detections, the model will extract the class ID and the bounding box info and apply non-maximum suppression. This can be done using the following code:

```python
%cp /content/drive/MyDrive/object_detection/object_detection_functions.py .

from object_detection_functions import object_detection_analysis_with_nms

score_threshold = 0.5
nms_threshold = 0.4
result, winner_boxes = object_detection_analysis_with_nms(test_img, class_labels, class_colors, obj_detections_in_layers, score_threshold, nms_threshold)

cv2_imshow(result)
```

Now, in order to analyse the quality of prediction, you need to compute the IoU, as shown below.

```python
import io
 
ground_truth_boxes = []
 
with io.open("test_data/test_gko_rs_ground_truth.txt", mode="r", encoding="utf-8") as f:
  for line in f:
    ground_truth_boxes.append(line.split())
 
for i in range(0, len(ground_truth_boxes)):
  for j in range(0, len(ground_truth_boxes[i])):
    ground_truth_boxes[i][j] = int(ground_truth_boxes[i][j])
```

Finally, let’s visualise the predicted bounding box against the ground truth using the following commands:

```python
from object_detection_functions import object_detection_iou
 
# create a copy of the test image
iou_image = test_img.copy()
 
# print the ground truth and detection bounding boxes, and the IoU value
iou_image, iou_value = object_detection_iou(test_img, winner_boxes[0], ground_truth_boxes[0])

cv2_imshow(iou_image)
```

This output will help you to analyse the predicted bounding box. The bounding box has an IoU of 85% and it lies close to the ground truth. Even though the prediction is not perfect, it is a good one and is acceptable. Obtaining a 100% IoU in real-time tasks is quite difficult; hence, IoU scores above 60% are considered to be quite good.

You can visualise the output by running the code given above, and you will obtain the image given below as output:

![Face with mask detected](https://i.ibb.co/kGjtdLG/Face-with-mask-detected.png)

This is how you can create, train and deploy your own custom object detector. The process is lengthy and time-consuming. Therefore, you need to use pre-trained models for problems in which they are available. 

In the next segment, we will summarise your learnings from this session.