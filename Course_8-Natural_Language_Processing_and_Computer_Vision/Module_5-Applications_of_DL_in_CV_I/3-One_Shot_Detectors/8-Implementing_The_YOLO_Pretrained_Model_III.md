# Implementing The YOLO Pretrained Model - III

So far in the implementation, you have computed the predicted output of the model and visualised how each object was accompanied by multiple bounding boxes. However, you do not require all these boxes as many of them are either overlapping or partially correct. 

This issue can be resolved with **non-maximal suppression (NMS)**.

#### NMS

Qn: Take a look at the image given below:

![People Bicyles Multiple Bounding Boxes](https://i.ibb.co/ZBvwTFq/People-Bicyles-Multiple-Bounding-Boxes.png)

The above image shows all the possible bounding box predictions to detect the man. After performing NMS, which of the following bounding boxes - red, green, blue and pink will be the output bounding box? Given that the threshold IoU is 70%.

- Red

- Green

- Blue

- Pink

Ans: C. *The green bounding box has IoU greater than the threshold. However, it cannot directly be selected as the blue bounding box also has an IoU greater than the threshold. Therefore, the probabilities(pc) of both boxes will be compared. The blue box has a higher probability(pc) than the green box. Hence, it is selected.*

You will learn how to perform NMS in code from Georgios in the forthcoming video.

**VIDEO**

NMS will suppress the bounding boxes with partial or overlapping coordinates and give you the coordinates of one bounding box coordinates as output. Here are the main steps to do this:

1.  Declare lists for the arguments of interest – classID, bbox info and detection confidences – as shown below.
    
```python
class_ids_list = []
boxes_list = []
confidences_list = []
```
    
2.  Populate those lists from the detections as shown below.
    
```python
def object_detection_attributes(test_image, obj_detections_in_layers, confidence_threshold):
      # get the image dimensions  
      img_height = test_img.shape[0]
      img_width = test_img.shape[1]
      
      # loop over each output layer 
      for object_detections_in_single_layer in obj_detections_in_layers:
        # loop over the detections in each layer
        for object_detection in object_detections_in_single_layer:  
          # get the confidence scores of all objects detected with the bounding box
          prediction_scores = object_detection[5:]
          # consider the highest score being associated with the winning class
          # get the class ID from the index of the highest score 
          predicted_class_id = np.argmax(prediction_scores)
          # get the prediction confidence
          prediction_confidence = prediction_scores[predicted_class_id]
          
          # consider object detections with confidence score higher than threshold
          if prediction_confidence > confidence_threshold:
            # get the predicted label
            predicted_class_label = class_labels[predicted_class_id]
            # compute the bounding box coordinates scaled for the input image
            bounding_box = object_detection[0:4] * np.array([img_width, img_height, img_width, img_height])
            (box_center_x_pt, box_center_y_pt, box_width, box_height) = bounding_box.astype("int")
            start_x_pt = max(0, int(box_center_x_pt - (box_width / 2)))
            start_y_pt = max(0, int(box_center_y_pt - (box_height / 2)))
            
            # update the 3 lists for nms processing
            # - confidence is needed as a float 
            # - the bbox info has the openCV Rect format
            class_ids_list.append(predicted_class_id)
            confidences_list.append(float(prediction_confidence))
            boxes_list.append([int(start_x_pt), int(start_y_pt), int(box_width), int(box_height)])
```
    
3.  Define the score threshold and call the object detection function as shown below.
    
```python
score_threshold = 0.5
    object_detection_attributes(test_img, obj_detections_in_layers, score_threshold)
```
    
4.  Perform NMS as shown below.
    
```python
# NMS for a set of overlapping bboxes returns the ID of the one with highest 
    # confidence score while suppressing all others (non maxima)
    # - score_threshold: a threshold used to filter boxes by score 
    # - nms_threshold: a threshold used in non maximum suppression. 
     
    score_threshold = 0.5
    nms_threshold = 0.4
    winner_ids = cv2.dnn.NMSBoxes(boxes_list, confidences_list, score_threshold, nms_threshold)
    
    # loop through the final set of detections remaining after NMS and draw bounding box and write text
    for winner_id in winner_ids:
        max_class_id = winner_id[0]
        box = boxes_list[max_class_id]
        start_x_pt = box[0]
        start_y_pt = box[1]
        box_width = box[2]
        box_height = box[3]
        
        #get the predicted class id and label
        predicted_class_id = class_ids_list[max_class_id]
        predicted_class_label = class_labels[predicted_class_id]
        prediction_confidence = confidences_list[max_class_id]
     
        #obtain the bounding box end coordinates
        end_x_pt = start_x_pt + box_width
        end_y_pt = start_y_pt + box_height
        
        #get a random mask color from the numpy array of colors
        box_color = class_colors[predicted_class_id]
        
        #convert the color numpy array as a list and apply to text and box
        box_color = [int(c) for c in box_color]
        
        # print the prediction in console
        predicted_class_label = "{}: {:.2f}%".format(predicted_class_label, prediction_confidence * 100)
        print("predicted object {}".format(predicted_class_label))
        
        # draw rectangle and text in the image
        cv2.rectangle(test_img, (start_x_pt, start_y_pt), (end_x_pt, end_y_pt), box_color, 1)
        cv2.putText(test_img, predicted_class_label, (start_x_pt, start_y_pt-5), cv2.FONT_HERSHEY_SIMPLEX, 0.5, box_color, 1)
```
    
5.  Finally, you can visualise the output image as shown below.
    
```python
cv2_imshow(test_img)
```
    

Upon visualising the output image, you will see that each object is accompanied by a single bounding box, as shown here.

![People Bicyles Final Bounding Boxes](https://i.ibb.co/MM7b0p8/People-Bicyles-Final-Bounding-Boxes.png)

So far, you saw how to detect objects in images using the YOLO pretrained model. Similar to this you can explore how object detection is performed in videos using the notebook and file given below.

Download [YOLO_pretrained_model_video_object_detection.ipynb](object_detection_yolov4_pretrained_video.ipynb)

Download [Object_detection_functions.py](object_detection_functions.py)

This is how you can perform any object detection task using YOLO pretrained models. Moving ahead, in the next segment, you will learn about the second one-shot object detector: **SSD**.