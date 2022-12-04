# Implementing An SSD Pretrained Model - II

The next step in this implementation is to deploy the model and analyse the results. You will learn how to do this from Georgios in the forthcoming video:

**VIDEO**

So, as you saw in the video, you can deploy the model as shown below.

```python
# set the intensity scaling factor; 1 in this case, i.e. original image intensities
scalefactor = 1.0
 
# set the new dimensions for image resizing to match the network requirements
new_size = (300, 300)
 
# create a blob using OpenCV's DNN functionality and by performing mean subtraction 
# to normalize the input
blob = cv2.dnn.blobFromImage(image, scalefactor, new_size, (127.5, 127.5, 127.5), swapRB=True, crop=False)

# set the blob as input to the network
detector.setInput(blob)
# compute the forward pass - detect faces if any
detections = detector.forward()
detections.shape
```

Once the model is deployed, you can then analyse its outcome as shown below.

```python
# Declare an array
detections[0][0][0]
 
# compute the length of the array
len(detections[0][0])

# set the confidence threshold
confidence_threshold = 0.5

# loop over the detections
for i in range(0, detections.shape[2]):
  # extract the confidence (i.e., probability) associated with the prediction
  confidence = detections[0, 0, i, 2]
  # ignore weak detections
  if confidence > confidence_threshold:
    # compute the (x, y)-coordinates of the bounding box for the detected object
    box = detections[0, 0, i, 3:7] * np.array([w, h, w, h])
    (startX, startY, endX, endY) = box.astype("int")
    # draw the bounding box of the detected face
    cv2.rectangle(image, (startX, startY), (endX, endY), (0, 0, 255), 2)
    # print the probability of this detection
    text = "confidence: {:.2f}%".format(confidence * 100)
    y = startY - 10 if startY - 10 > 10 else startY + 10
    cv2.putText(image, text, (startX, y), cv2.FONT_HERSHEY_SIMPLEX, 0.45, (0, 0, 255), 2)

# show the output image
cv2_imshow(image)
```

Finally, you can visualise the model output and the face detected as shown in this image.

![Emmanuel Macron Boxed](https://i.ibb.co/dL0gqxM/Emmanuel-Macron-Boxed.png)

This is how you can detect objects using the SSD in a few simple steps. So, now that you have implemented both the YOLO and SSD models, we will next look at a quick comparison between the different object detectors in the next video.

**VIDEO**

So, in the video, you saw a brief comparison between the different object detectors. Here is a summary of the points of comparison:

1.  The Faster-RCNN model has a very high mean average performance (mAP). However, due to its slow speed, this model cannot be used for real-time applications.  
     
2.  Fast YOLO is the fastest algorithm and is used if speed is the highest priority. Nevertheless, this algorithm does not guarantee the highest accuracy.  
     
3.  SSD is the best choice if you want an algorithm that provides a good balance of accuracy and speed.

This brings us to the end of this session. The next segment will summarise your learnings from the session.

## Additional Reading

1.  You can go [here](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf1_detection_zoo.md) to learn more about the comparison between different object detectors.