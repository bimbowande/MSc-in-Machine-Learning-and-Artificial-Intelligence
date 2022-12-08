# YOLO - Introduction

The first one-shot object detector that you will learn about in this session is **YOLO - You only look once**. Let us go ahead and watch the forthcoming video, which discusses this object detection algorithm.

**VIDEO**

Now, we will go through the object detection example that you saw in the video and try to develop an understanding of the YOLO algorithm. The input image for this demonstration is given below.

![YOLO Input Image](https://i.ibb.co/37DmrQH/YOLO-Input-Image.png)

**Problem Statement:** Detecting the presence of humans, cars and bikes in the image provided.

Now, using this input image, we will try to understand the working of the YOLO model step by step. The steps in this algorithm are discussed below:

1.  **Preprocessing:** The YOLO model divides the image into a 3X3 grid as shown below.
    
    ![YOLO Grids](https://i.ibb.co/q98hhbJ/YOLO-Preprocessing.png)
    
2.  **Train the network:** The resultant image is then passed through a single convolutional neural network (CNN) as shown in this image.
    
    ![YOLO Grids](https://images.upgrad.com/ffeae350-3f5f-47b7-8914-903216a61ddc-unnamed%20(11).png)
    
3.  **Analysing the output:** The model predicts the output of each grid cell in a single forward pass (feedforward propagation) through the CNN. If the centroid of an object is present in a certain grid cell, the cell containing the object gets labelled such that the same object is not detected again.   
    ![YOLO Analysing the Output](https://i.ibb.co/9VF31Vb/YOLO-Analysing-the-Output.png)
    
      
    The output of the algorithm can be divided into two parts as shown below:
    
    1.  **The output of each grid cell:** The output of each grid cell contains c+5 elements, where c=3 in our case since there are 3 classes. On substituting the value of c, you will get c+5=3+5=8 elements in this case. Take a look at this output vector.   
        $$\large{Y=\begin{bmatrix}p_c\\c_1\\c_2\\c_3\\b_{cx}\\b_{cy}\\b_h\\b_w\end{bmatrix}}$$
          
        Here, pc is the softmax probability of the object present in the image.    
        $c_1$, $c_2$ and $c_3$ are, respectively, the different classes, i.e., humans, cars and bikes.  
         bcx, bcy, bh and bw represent, respectively, the bounding box’s centroid coordinates x and y, height and width.  
          
        NOTE: In this example, there is only 1 object in a grid cell, therefore, only one probability value, $p_c$ will be present. In the upcoming segments, you will also come across examples with more than one object in a grid cell.  
         
    2.  **Overall output:** The overall output of the model is the resultant output of all the grid cells. The output vector contains $s∗s∗(c+5)$ elements, where $s∗s=3X3=9$ (number of grid cells) and c=3 (number of classes). Hence, the output vector in this example will have 72 elements.  
         
All the above steps are summarised in the image below:

![YOLO Steps](https://i.ibb.co/cLn6LC2/YOLO-Steps.png)

Now, answer these questions based on your understanding of this model.

#### Object Detectors

Qn: Choose whether this statement is true or false: *"The YOLO algorithm can classify and localise an image in a single pass, whereas the Faster-RCNN detector does it in two passes."*

- True

- False

Ans: A. *As the name suggests, YOLO is a one-shot detector, and it predicts the class and location of a detected object in a single pass.*

#### YOLO

Qn: How many elements will be present in the cell output vector of the YOLO output if the objects to be detected are - (i) facemasks and, (ii) spectacles on human faces?

- 8

- 7

- 6

Ans: B. *The number of elements in the cell output vector can be given by c + 5, where c is the number of classes. Therefore, the number of elements = c + 5 = 2 + 5 = 7.*

Now, we will look at the overall architecture of the YOLO model, which is shown in this image.

![YOLO Model Architecture](https://i.ibb.co/Mhv7XGT/YOLO-Model-Architecture.jpg)

The YOLO model that is currently being used is YOLOv3. This third iteration of the YOLO model is a variant of the DarkNet project, which you will be using to train your YOLO model in the upcoming segments. This version of the YOLO model offers greater accuracy than the previous versions, although it takes longer due to the increased number of convolutional layers.  
 

As you can see in the above image, the input image with a $3X3$ grid is passed through a series of convolutional downsampling networks such that the $416X416$ image is downsampled to a $13X13X512$ feature vector. 

This vector is then passed through a dense network, followed by a pooling layer, after which the objects are detected in the last step of the process. The output of the bounding box and class is given as the output of the network.

Note: This module will not cover the YOLO architecture in depth as it is out of the scope of the syllabus. However, you can explore more about the same using the links given in the additional reading part of this segment.

#### YOLO

Qn: Which of these options is not a part of the YOLO model architecture?

- Pooling layer

- Convolutional layer

- Fully connected layer

- Region proposal network

Ans:D. *The YOLO model does not follow the region-based approach, and, hence, it does not consist of a region proposal network.*

Now that you have been introduced to the YOLO detector, you will learn how the model works in the upcoming segment.

## Additional Reading:

1.  Learn more about the YOLO model [here](https://www.geeksforgeeks.org/yolo-you-only-look-once-real-time-object-detection/).
2.  You can explore more about the YOLO architecture [here](https://medium.com/adventures-with-deep-learning/yolo-v1-part-1-cfb47135f81f).
3.  Dig deeper into the YOLO model [here](https://www.section.io/engineering-education/introduction-to-yolo-algorithm-for-object-detection/).