# Summary

With this, you have reached the end of this session. In this session, you implemented a custom YOLO model to predict the presence of face masks in the images of human faces. 

You started by setting up the environment and importing libraries, and fetching weights for training and testing the model. Next, you customised the model and compiled DarkNet. Further, you trained and deployed the model and finally analysed the output of the model. 

In this module on object detection, you learnt how to detect objects using different types of detectors. Let’s watch the next video to summarise your learnings from this module on object detection.

**VIDEO**

First, you were introduced to the concept of **computer vision** and its applications. You then developed an understanding of the fundamentals of object detection, the applications of object detection and the concept of **object localisation**. You learnt about **bounding boxes, IoU and loss computation** in object detection tasks.

Next, you briefly learnt about **region-based object detectors**, i.e., the RCNN family, along with their advantages and disadvantages. You learnt about **one-shot detectors** and YOLO. With regard to the **YOLO algorithm**, you learnt about anchor boxes and non-maximal suppression. You also saw what the YOLO output looks like and the architecture of this detector.

Further, you implemented the pre-trained YOLO model, wherein you detected the presence of objects such as humans, cars and bikes on a real-time image of a road. This is one of the common applications of object detection, i.e., **traffic surveillance**.

Next, you learnt about the SSD detector. You were introduced to the concept of multi-box and default bounding boxes. You explored the architecture of **SSD** and learnt how objects are detected. For SSD, you implemented a pre-trained model to **detect human faces** in a given image. You then compared the different object detection algorithms.

In the last session on object detection, you developed a custom YOLO model to predict the **presence of face masks** in the images of human faces. In this implementation, you learnt how to create a custom model by customising the **DarkNet project** and manually fetching the data and training the model. It took a long time to train this model. Finally, you deployed the model and analysed the predicted bounding box against the ground truth bounding box.

Download the custom_model-training solution notebook below:

Download [Training_solution_notebook.ipynb](object_detection_yolov4_custom_model_train.ipynb)

Download the custom_model-deployment solution notebook below:

Download [Deployment_solution_notebook.ipynb](object_detection_yolov4_custom_model_deploy.ipynb)

You can download the summary document for this module given below:

Download [Lecture Notes]()

In the next part of this module, you will learn about another application of CV ie., **Semantic Segmentation.**