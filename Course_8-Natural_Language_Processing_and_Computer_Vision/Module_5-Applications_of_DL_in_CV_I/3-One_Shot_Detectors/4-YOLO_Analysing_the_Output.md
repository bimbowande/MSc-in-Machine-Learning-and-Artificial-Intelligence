# YOLO - Analysing The Output

So far, you have learnt how to train and deploy a model using the YOLOv3 algorithm. You also learnt how to compute the model output. Now, if you recall, in machine learning models, you computed accuracy, the F1 score, precision and recall, etc. in order to determine how good a prediction was. In the case of object detectors, we calculate intersection over union (IoU), which serves as an evaluation metric for model prediction, i.e., the bounding box predicted by the model. 

You have already learnt about IoU in one of the previous sessions. Now, we will quickly recall the concept of IoU and discuss another interesting technique, non-maximal suppression (NMS), in the forthcoming video. 

**VIDEO**

So, as you learnt in the video, the evaluation metric IoU can be used to compare bounding boxes to determine which is the most accurate for a given object. 

You will already be given a threshold value (th) against which you can compare the IoU. If the value of IoU is above the threshold value, then the prediction is considered good. Remember, the higher the value of IoU, the better will be the prediction. In general, an IoU of 60% or above is considered to be acceptable.

#### IoU

Qn: You have already learnt about the IoU metric. Now, recall the correct formula for computing IoU and select the correct answer from the options given below.

- Area of intersection/ Area of union

- Area of union/Area of intersection

Ans: A. *As the name suggests, intersection over union can be given as Area of intersection/Area of union.*

Qn: Which of these cases will have the best IoU value?

- ![IoU Sample Qn 1](https://i.ibb.co/17gHMLf/IOU-Sample-Qn-1.png)

- ![IoU Sample Qn 2](https://i.ibb.co/0rJSNDb/IOU-Sample-Qn-2.png)

- ![IoU Sample Qn 3](https://i.ibb.co/mbCGZDJ/IOU-Sample-Qn-3.png)

Ans: A. *This case will have the best IoU as the area of intersection is the largest amongst the three.*

In the assessments above, you saw one object accompanied by a single bounding box; this might not be the case every time you train the network. While working with complex images, you can get multiple bounding boxes for the same object, but you do not require all of them. So, how will you select the most accurate bounding box? 

Take a look at this image and try to predict which of the two bounding boxes is more accurate for the given object.

![NMS Bounding Boxes 1](https://i.ibb.co/KVP7q6q/NMS-Bounding-Boxes-1.png)

Each bounding box in the image above is accompanied by the probability of the object belonging to a particular class. In such cases, where you have multiple bounding boxes, you can check the IoU values. If the IoU value is less than the threshold value, then the corresponding bounding box can be rejected.

But if there are more than one bounding box with IoU values greater than the threshold value, then you can make the decision using the technique of NMS. This method selects the bounding box with the higher probability (pc) and rejects the others. So, for the image above, the better prediction will be the white bounding box as $p_c=0.7$ is greater than 0.6.

The output image after performing NMS will look like this.

![NMS Bounding Boxes 2](https://i.ibb.co/GMgcJRh/NMS-Bounding-Boxes-2.png)

  
Now, before proceeding further, answer these questions based on your learning so far.

#### NMS

Qn: The image below is accompanied by three bounding box predictions i.e., red, green and yellow and the ground truth bounding box represented in the blue color. Compare the predictions to the ground truth and answer the following question based on your analysis.

Which of these will be the final predicted bounding box for this image?

![NMS Bounding Boxes 3](https://i.ibb.co/zhX7JSm/NMS-Bounding-Boxes-3.png)

Note: Assume the IoU threshold to be 60.

- Red

- Green

- Yellow

Ans: A. *The IoU of the red bounding box is greater than the threshold and it has the highest Pc, therefore, it will be selected as the final bounding box,*

In this segment, you understood the concept of non-maximal suppression and how to select the most accurate bounding box out of the many predicted ones. In the next segment, you will be answering a very interesting question and learning about a new concept known as **anchor boxes.**
