# Implementing The YOLO Pretrained Model - I

So far in this module, we have covered the different aspects of the YOLO algorithm from a theoretical perspective. Now, in this segment, you will learn how to solve an object detection problem using a YOLO pretrained model. For this implementation, you will be solving this real-world problem related to traffic surveillance.

**Problem Statement:** Build an object detector to detect the presence of bicycles, people and other objects that are present in an image.

Download the test image given below:

Download [People Bicycles](People_Bicycles.jpg)

Let us get started and watch the first video of this implementation task.

**VIDEO**

So, as you saw in the video, the very first step in this task will be to import the required libraries and read the data, which, in this case, will be the test image. Since the model is pretrained, you can load the test image directly and evaluate the results against the data that was used originally to train the model. 

  
Take a look at this code snippet and write the code in your own notebook as you continue with the implementation.

```python
# import the relevant libraries
import numpy as np
import cv2 # openCV

# check the opencv version
print(cv2.__version__)

# if the openCV version is < 4.4.0 update to the latest otherwise skip this step
!pip install opencv-python==4.5.2.52
```

Please check the version of OpenCV. If it is lower than 4.4.0, then run the last line of the code above and restart your runtime to implement the changes. Re-run the first two steps before proceeding ahead.

  
The next step will be to fetch the pretrained model on which you will be testing your image to detect the objects. You can do this by writing the following code.

```python
# first create a directory to store the model
%mkdir model

# enter the directory and download the necessary files 
%cd model
!wget https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights
!wget https://raw.githubusercontent.com/AlexeyAB/darknet/master/cfg/yolov4.cfg
!wget https://raw.githubusercontent.com/AlexeyAB/darknet/master/data/coco.names
%cd ..
```

Once your model is loaded into the notebook, you can read the test/input image and take a look at what your input data looks like.

Note: Before implementing the code, make sure that you download the test image given at the beginning of this segment and upload it on your drive. Otherwise, you can directly download the test image from the web using the GitHub link as shown in option1 in the code snippet below.

You can do so by implementing either of these two methods.

```python
# option 1: download a test image from the web
!wget https://github.com/georgiosouzounis/object-detection-yolov4/raw/main/data/pretrained/people_bicycles.jpg
 
# option 2: mount your Google Drive and select the image of your own
from google.colab import drive
drive.mount('/content/drive')

# copy a test file locally or use it directly from the mounted drive 
# customize this example for your drive structure
%cp drive/MyDrive/object_detection/people_bicycles.jpg .

# read file
test_img = cv2.imread('people_bicycles.jpg')

# display test image
# import the cv2_imshow as a replacement of cv2.imshow to prevent errors
from google.colab.patches import cv2_imshow
cv2_imshow(test_img)
```

If you are uploading the image to your drive and reading it, make sure to edit the path by copying it as shown in the image below:

![](https://images.upgrad.com/8a864c22-96d3-4a4f-bc5b-afbacac27fd4-dsBuffer.jpg)

Now, take a look at this test image and answer the question that follows.

![people bicycles](https://i.ibb.co/tcxjHdP/People-Bicycles.jpg)

#### Detecting Objects

Qn: List all possible object classes that you can see in the image above.

Ans: *Car, bike, humans, mask, backpack, etc.*

Once you have read and viewed your test image, you will next have to process it to a format that the pretrained model will accept and then adjust/customise the YOLO model according to the requirements of the task. Let us watch the next video and learn how to do so from Georgios.

**VIDEO**

First, you need to convert the test image to a **BLOB**. BLOB stands for a binary large object, which is a binary string of varying length. You can convert the image to a BLOB using the OpenCV built-in **dnn.blobFromImage()** method to ensure model compatibility. This method will have the following input arguments:

1.  **scalefactor**: It is the multiplication factor for each pixel to rescale its intensity in the range of [0,1]. No contrast stretching is performed. It is set to 1/255.0 = 0.003922.  
     
2.  **new_size**: It refers to the rescaling size for network compatibility. We use (416, 416). Other supported sizes include (320, 320) and (609, 609). The greater the size is, the better will be the prediction accuracy, although at the cost of a higher computational load.  
     
3.  **swapRB:** It is the binary flag that, if set, instructs OpenCV to swap the red and blue channels. That is because OpenCV stores images in a BGR order but YOLO requires them in RGB.  
     
4.  **crop**: It is the binary flag that, if set, instructs OpenCV to crop an image after resizing.

You can convert your image to a BLOB by simply writing these lines of code.

```python
scalefactor = 1.0/255.0
new_size = (416, 416)
blob = cv2.dnn.blobFromImage(test_img, scalefactor, new_size, swapRB=True, crop=False)
```

Once you have converted your image to a BLOB, you can then customise the bounding boxes class colours as per the requirements of the detection task and also add text snippets above the detected bounding boxes to show information. You can do this as shown below.

```python
# define class labels
class_labels_path = "/content/model/coco.names"
class_labels = open(class_labels_path).read().strip().split("\n")
class_labels

# declare repeating bounding box colors for each class 
# 1st: create a list colors as an RGB string array
# Example: Red, Green, Blue, Yellow, Magenda
class_colors = ["255,0,0","0,255,0","0,0,255","255,255,0","255,0, 255"]
 
#2nd: split the array on comma-separated strings and for change each string type to integer
class_colors = [np.array(every_color.split(",")).astype("int") for every_color in class_colors]
 
#3rd: convert the array or arrays to a numpy array
class_colors = np.array(class_colors)
 
#4th: tile this to get 80 class colors, i.e. as many as the classes(16 rows of 5cols each). 
# If you want unique colors for each class you may randomize the color generation or set them manually
class_colors = np.tile(class_colors,(16,1))

def colored(r, g, b, text):
    return "\033[38;2;{};{};{}m{} \033[38;2;255;255;255m".format(r, g, b, text)
 
for i in range(16):
  line = ""
  for j in range(5):
    class_id = i*5 + j
    class_id_str = str(class_id)
    text = "class" + class_id_str
    colored_text = colored(class_colors[class_id][0], class_colors[class_id][1], class_colors[class_id][2], text)
    line += colored_text
  print(line)

# or select the colors randomly
class_colors = np.random.randint(0, 255, size=(len(class_labels), 3), dtype="uint8")
```

Finally, once you have customised the model and converted your image into a BLOB, you can then load your model and compute the results. In the next segment, we will see how this will be done.