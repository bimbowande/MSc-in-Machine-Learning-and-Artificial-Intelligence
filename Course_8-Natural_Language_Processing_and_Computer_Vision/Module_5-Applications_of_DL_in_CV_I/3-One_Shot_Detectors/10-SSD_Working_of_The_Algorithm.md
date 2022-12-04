# SSD - Working of The Algorithm

In the previous segment, you were introduced to the SSD algorithm and learnt about its basics. Now, in this segment, we will dive deep into this algorithm and discuss the architecture of the model. We will discuss all of this in the forthcoming video.

**VIDEO**

So, as you saw in the video, the architecture of the SSD model looks like this.

![SSD Model Architecture](https://i.ibb.co/sFKj6Xp/SSD-Model-Architecture.png)

So, as you can see in this image, the SSD comprises a total of six convolution layers, which are of different sizes and provide different scales of the same image. This allows the model to detect objects at multiple scales.

The initial layers have a small receptive field, i.e., they cover a low spatial region. These layers detect the smaller objects in an image. However, the later layers have a large receptive field and detect the bigger objects.

In the YOLO model, you saw anchor boxes, which helped detect multiple overlapping objects. The SSD uses **default bounding boxes**, which serve the same purpose. There are 4 or 6 default bounding boxes, which are defined with one prediction per box. 

This serves as a starting point for the algorithm by giving the model an idea about how the objects look and where they might be located. The SSD then uses feature maps to detect objects at different scales. Now, you might wonder how the SSD selects the final bounding box out of the 4 or 6 default boxes.

This technique of selecting the final bounding box is referred to as the **matching strategy** in the SSD. Take a look at this image.

![SSD Sample Image](https://i.ibb.co/0CLz5Gw/SSD-Sample-Image.png)

Let us draw four default bounding boxes for this image. The objects in the image include the human and the bike. The default bounding boxes for this image are shown below.

![SSD Sample Image Default Bounding Boxes](https://i.ibb.co/gd0FYBf/SSD-Sample-Image-Default-Bounding-Boxes.png)

The conv4_3 layer divides the image into a $38X38$ grid and predicts four boxes per cell. Therefore, the overall predictions made by the conv4_3 layer become $38X38X4$. As you already know, each prediction has the bounding box coordinates and 21 scores, and the highest score denotes the class of the object detected.

Of the four boxes, box 4 contains only one object, the human, whereas the others have both the human and the bike. Therefore, we will take boxes 1, 2 and 3 into consideration to understand this concept. The resultant image is shown below.

![SSD Sample Image Boxed](https://i.ibb.co/hdJ8dk3/SSD-Sample-Image-Boxed-2.png)

The ground truth box is shown in red in this image.

![SSD Sample Image Ground Truth](https://i.ibb.co/4gKPD6n/SSD-Sample-Image-Ground-Truth.png)

Now, these three predictions (excluding the ground truth) are segregated into positive or negative based on whether their IoU is lower or higher than the ground truth, i.e., 50%. If the value of IoU is less than 50%, then it is said to be a **negative match** and is rejected. If the value is more than 50%, then it is said to be a **positive match** and is accepted. 

In this example, box 1 has an IoU less than 50%, which means it is a negative match; it will, thus, be rejected. On the other hand, boxes 2 and 3 have IoU values greater than 50%, i.e., a positive match.

The losses for this prediction are of two types:

1.  **Confidence loss**: It refers to the loss incurred in the prediction of the class, which is calculated using the categorical cross-entropy loss, which you have learnt already in the previous modules:
    1.  In the case of a positive match, the loss is penalised according to the confidence score of the corresponding class.   
         
    2.  In the case of negative match predictions, the loss is penalised according to the confidence score of the class “0”.  
         
2.  **Location loss:** It refers to the loss incurred while calculating the bounding box coordinates. It is calculated using the L1 or L2 loss formula, which you learnt about and implemented previously. 

The total loss can be calculated using this formula:

$$\large{\text{Multibox or SSD loss}=\text{Confidence loss}+\alpha*\text{Location loss}}$$

Here, $\alpha$ is a parameter that is used to balance the overall loss.

Now, answer these questions based on your learning so far.

#### SSD

Qn: What does class “0” in the SSD algorithm mean?

- No object is detected.

- It is the class number given to a certain object.

- None of the above

Ans: A. *"0" indicates that no object has been detected in an area.*

Qn: What are default bounding boxes?

- They are the final output boxes of the objects detected using the SSD.

- They are the initial boxes of the objects detected, which are later refined.

Ans: B. *Default bounding boxes are the initial values of localisation provided by the SSD, which are later refined and corrected to increase accuracy.*

#### Feature Maps

Qn: You know that SSD uses feature maps to detect objects at different scales. Take a look at the image given below:

![SSD Feature Map Qn](https://i.ibb.co/y8Rwfgb/SSD-Feature-Map-Qn.jpg)

Based on your understanding of the working of the single-shot multibox detector, select the correct option.

- The 4x4 feature map will detect the jug.

- The 4x4 feature map will detect the yellow tomatoes.

- The 8x8 feature map will detect the yellow tomatoes.

- The 8x8 feature map will detect the jug.

Ans: A & C. *The 4X4 feature map will detect the larger objects i.e, jug in this image. The 8X8 feature map will detect the smaller objects i.e, yellow tomatoes in this image.*

So, now that you have learnt about the SSD algorithm, in the next segment, we will study a real-world use case and solve a problem statement using an SSD pretrained model.
