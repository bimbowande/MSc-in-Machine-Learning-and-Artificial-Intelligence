# Object Localisation

As you learnt in the previous segments, object detection performs two tasks: (i) Detecting an object’s class and (ii) identifying the object’s location through ‘bounding boxes’. In the forthcoming video, you will learn more about object detection and the concept of **localisation**.

**VIDEO**

So, in the video, you saw how classification and localisation work in parallel in object detection algorithms. The image below provides a summary of the working of object detection algorithms.

![Summary of the Working of Object Detection Algorithms](https://i.ibb.co/f8tJGdR/Summary-of-the-Working-of-Object-Detection-Algorithms.png)

You will now learn about each of these elements that we have discussed so far. **Object localisation** refers to determining the locations of the objects present in an image. The location is given by the coordinates of the **bounding boxes**. The **bounding box vector** consists of four elements:

1.  The _x_ coordinates of the centroid, 
2.  The _y_ coordinates of the centroid,
3.  The height of the bounding box and
4.  The width of the bounding box.

This is shown in the vector below.
$$\large{\begin{bmatrix}b_x\\b_y\\b_h\\b_w\end{bmatrix}}$$

Now, since the output of an object detection model is primarily a bounding box, you need some method to be able to evaluate how well the model has localised an object and predicted its bounding box. The standard industry metric that you need to consider for this purpose is **intersection over union (IoU)**. This metric evaluates the accuracy of your model’s prediction of the bounding box by comparing it with the ‘**ground truth**’ bounding box present in the training set. Take a look at this image, which shows the predicted and ground truth bounding boxes.

![Predicted and Ground Truth Bounding Boxes](https://i.ibb.co/X3zKDRm/Predicted-and-Ground-Truth-Bounding-Boxes.png)

Recall that this is similar to the actual and predicted outputs, which you have been comparing in the case of ML and DL algorithms so far. However, instead of having a single value of the outputs, in the case of object detection algorithms, you will have a vector. 

The IoU is measured by taking the intersection of the two boxes and dividing it by their union. It can be expressed as follows:

$$\large{\text{IoU}=\dfrac{\text{Area of intersection}}{\text{Area of union}}}$$

Note that IoU lies between 0 to 1 since it is a fraction.  The image below depicts the numerator and denominator of this formula.

![Numerator and Denominator of IoU](https://i.ibb.co/pPcL2Pq/Numerator-and-Denominator-of-Io-U.png)

Now, based on your learning so far, try answering these questions.

#### IoU

Qn: You have learnt that IoU is used as an evaluation metric for object detection tasks. You also saw the formula for IoU. Now, based on your understanding, select the correct option(s), which justify(ies) how IoU is a good choice as an evaluation metric.

- A higher IoU ensures good results.

- IoU acts as a good metric as it allows us to analyse how close the predicted location is to the actual one.

- A lower IoU ensures good results.

Ans: A & C. *IoU is the evaluation metric, which predicts how good a prediction is by comparing the predicted bounding box to the ground truth bounding box. IoU is given by this formula: IoU = Area of intersection / Area of union. An IoU closer to 1 ensures better results as it means that the area of intersection between the ground truth and predicted bounding boxes is almost equal to their union. Hence, a higher IoU means better results. *

#### Area of Intersection

Qn: Compute the area of intersection for this image.

![IoU Example](https://i.ibb.co/mGpsxbc/Io-U-Example.png)

- 12

- 15

- 8

- 16

Ans: A. *The area of intersection for this image will be the area of the smaller, maroon box, which can be computed as shown below:  $L=8-2=6$ ; $W=4-2=2$. Therefore, $area=6*2=12$.*

#### Area of Union

Qn: Compute the area of union for this image.

![IoU Example](https://i.ibb.co/mGpsxbc/Io-U-Example.png)

- 50

- 10

- 100

- 20

Ans: C. *The area of union for this image will be the area of the bigger, black box, which can be calculated as shown below:  $L=10-0=10$; $W=10-0=10$. Therefore, $area=10*10=100$.*

#### IoU

Qn: Compute the IoU for this image.

![IoU Example](https://i.ibb.co/mGpsxbc/Io-U-Example.png)

- 12%

- 15%

- 10%

- 20%

Ans: A. *The IoU for this image can be computed as shown below: $IoU=\dfrac{\text{Area of intersection}}{\text{Area of union}}$. Therefore, $IoU = \dfrac{12}{100}=0.12$, or $12\%$.*

Now, you might wonder how to calculate the loss for such a vector? In the forthcoming video, you will learn about the loss functions for object detection algorithms. 

**VIDEO**

Object detection algorithms will have two losses:

1.  Classification or softmax loss, and
2.  Regression losses – L1 and L2 losses.

You are already familiar with these losses, but let us revisit the L1 and L2 losses for object detection. **L1 loss** is employed to minimise the error that is defined as the sum of all the absolute deviations between the true and projected values. Here is the formula for L1 loss.
$$\large{\sum^n_{i=1}|y_{true}−y_{predicted}|}$$

**L2 loss** is used to minimise the error that is defined as the total of all the squared discrepancies between the true and predicted values. Here is the formula for L2 loss.
$$\large{\sum^n_{i=1}\left(y_{true}−y_{predicted}\right)^2}$$

As you already know, L2 loss is the more preferred option in the case of outliers in data.

So, by now, you must have formed a good understanding of how to compute the IoU and loss functions for object detection. In real-world applications, you will not be required to compute them manually. This exercise of calculating the metrics was meant to provide you with a good understanding of the concept.

Moving ahead, in the next segment, you will be summarising the session.