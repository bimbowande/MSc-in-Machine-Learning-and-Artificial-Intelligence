# Implementing The YOLO Pretrained Model - II

So far, you have prepared your test image and model to ensure they are compatible with each other as well as with the object detection task. Now, the next step is to load and run the YOLO model. We will write the code to implement the same in the forthcoming video.

**VIDEO**

So, as you saw in the video, you can load your YOLO model from **DarkNet**. The DarkNet project is an open-source project written in C or CUDA. It is a fast and effective neural network framework, which we can use to customise our YOLO model.

You can load your model from DarkNet as shown below.

```python
# Load the pre-trained model 
yolo_model = cv2.dnn.readNetFromDarknet('model/yolov4.cfg','model/yolov4.weights')
```

Once you have loaded your model from DarkNet, you can then fetch the different layers of the YOLO model as shown below.

```python
# Read the network layers/components. The YOLO V4 neural network has 379 components. They consist of convolutional layers (conv), rectifier linear units (relu) etc.:
model_layers = yolo_model.getLayerNames()
print("number of network components: " + str(len(model_layers))) 
print(model_layers)

# extract the output layers in the code that follows:
# - model_layer[0]: returns the index of each output layer in the range of 1 to 379
# - model_layer[0] - 1: corrects  this to the range of 0 to 378
# - model_layers[model_layer[0] - 1]: returns the indexed layer name 
output_layers = [model_layers[model_layer[0] - 1] for model_layer in yolo_model.getUnconnectedOutLayers()]
 
# YOLOv4 deploys the same YOLO head as YOLOv3 for detection with the anchor based detection steps, and three levels of detection granularity. 
print(output_layers)
```

Now, try implementing the code on your own and answer this question.

#### YOLO Pretrained Model

Qn: From the options below, select the output layers that you will have in this pretrained model.

- yolo_139

- yolo_161

- yolo_142

- yolo_150

Ans: A, B & C. *You will have three output layers, yolo_139, yolo_161 and, yolo_150.*

Once the layers are fetched and visualised, you can then provide the input BLOB and propagate it forward in the network, as shown below.

```python
# input pre-processed blob into the model
yolo_model.setInput(blob)
 
# compute the forward pass for the input, storing the results per output layer in a list
obj_detections_in_layers = yolo_model.forward(output_layers)
 
# verify the number of sets of detections
print("number of sets of detections: " + str(len(obj_detections_in_layers)))
```

Upon executing the code above, you will see that the YOLO architecture produces three detection layers, which generate feature maps of sizes $15X15X255$, $30X30X255$ and $60X60X255$. Each detection layer is tasked with finding objects of a given size range. The architecture of these three layers is shown in this image.

![Dense Predictions](https://i.ibb.co/xhB95ZG/Dense-Predictions.png)

So, up to this point, you have fetched the model and loaded it. You have also provided the input BLOB to the model in the last few steps of the previous code snippet. This brings us to the last step of the code implementation: Analysing the results. We will watch the next video and understand how it can be done.

**VIDEO**

In order to analyse the output of the model, you will be creating a function, which will take these inputs:

1.  The test image
2.  The predicted/feedforward output of the model – ‘obj_detection_in_layers’
3.  The confidence threshold of the network

  
This function will predict the bounding box coordinates for each object detected in the image, along with the probability of the classes to which they belong. You can implement it on your own using this code.

```python
def object_detection_analysis(test_image, obj_detections_in_layers, confidence_threshold): 
 
  # get the image dimensions  
  img_height = test_img.shape[0]
  img_width = test_img.shape[1]
 
  result = test_image.copy()
  
  # loop over each output layer 
  for object_detections_in_single_layer in obj_detections_in_layers:
    # loop over the detections in each layer
      for object_detection in object_detections_in_single_layer:  
        # obj_detection[1]: bbox center pt_x
        # obj_detection[2]: bbox center pt_y
        # obj_detection[3]: bbox width
        # obj_detection[4]: bbox height
        # obj_detection[5]: confidence scores for all detections within the bbox 
 
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
            # scaling is a multiplication of the float coordinate with the appropriate  image dimension
            bounding_box = object_detection[0:4] * np.array([img_width, img_height, img_width, img_height])
            # get the bounding box centroid (x,y), width and height as integers
            (box_center_x_pt, box_center_y_pt, box_width, box_height) = bounding_box.astype("int")
            # to get the start x and y coordinates we to subtract from the centroid half the width and half the height respectively 
            # for even values of width and height of bboxes adjacent to the  image border
            #  this may generate a -1 which is prevented by the max() operator below  
            start_x_pt = max(0, int(box_center_x_pt - (box_width / 2)))
            start_y_pt = max(0, int(box_center_y_pt - (box_height / 2)))
            end_x_pt = start_x_pt + box_width
            end_y_pt = start_y_pt + box_height
            
            # get a random mask color from the numpy array of colors
            box_color = class_colors[predicted_class_id]
            
            # convert the color numpy array as a list and apply to text and box
            box_color = [int(c) for c in box_color]
            
            # print the prediction in console
            predicted_class_label = "{}: {:.2f}%".format(predicted_class_label, prediction_confidence * 100)
            print("predicted object {}".format(predicted_class_label))
            
            # draw the rectangle and text in the image
            cv2.rectangle(result, (start_x_pt, start_y_pt), (end_x_pt, end_y_pt), box_color, 1)
            cv2.putText(result, predicted_class_label, (start_x_pt, start_y_pt-5), cv2.FONT_HERSHEY_SIMPLEX, 0.5, box_color, 1)
  return result
 
confidence_threshold = 0.2
result_raw = object_detection_analysis(test_img, obj_detections_in_layers, confidence_threshold)
 
cv2_imshow(result_raw)
```

The objective of the code above is to get each object detection from each output layer and evaluate the algorithm’s confidence score against a threshold. For highest confidence detections, we extract the class ID and the bounding box information, as you can observe in the code above. 

Upon implementing the code, the output that you obtain would look like this.

![](https://images.upgrad.com/d14f51d2-599e-4a53-8eb8-851bc751f22d-download%20(1).png)

As you can see, each object is accompanied by multiple bounding boxes. You cannot compute the exact location of an object in the image in this way. So, how will you be able to determine the best bounding box?

Well, you can do this using **non-maximal suppression**, which is the next step of this implementation. You will learn about it in the upcoming segment.