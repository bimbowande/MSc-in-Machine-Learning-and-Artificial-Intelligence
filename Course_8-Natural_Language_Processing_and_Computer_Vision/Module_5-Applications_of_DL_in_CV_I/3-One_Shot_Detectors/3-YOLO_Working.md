# YOLO - Working

So far you have learnt about the basics and architecture of the YOLO detector. Now, let's dig deeper and understand how objects are detected in images that are fed to this detector. This is the process that an image goes through during the training step in the YOLOv3 model. Now, in the next video, we will look at the deployment process.

**VIDEO**

So, as you saw in the video, the input image, when divided into a $3X3$ grid, goes through the network, and each block that has no object is skipped from the object search process. This is depicted in this image.

![YOLO Blocks Skipped](https://i.ibb.co/TrLMT4n/YOLO-Blocks-Skipped.png)

For each of these grid cells, the probability of an object belonging to any class is 0, i.e., $p_c=0$. Therefore, the bounding box coordinates and class do not matter, and, hence, they will not be computed. Now, we will focus on the grid cell that contains the centroid of the object, as shown in this image.

![YOLO Object Detected](https://i.ibb.co/Z2N3XnV/YOLO-Object-Detected.png)

The probability of an object being detected in this grid cell is 1. The class $c_1=0$, $c_2=1$ and $c_3=0$, where $c_1$, $c_2$ and $c_3$ are, respectively, the classes for humans, cars and bikes. The green box around the object is the bounding box of the detected object.  
 

For this example, let us suppose that the bounding box coordinates that we obtain from the YOLO model are $b_{cx}=0.5$, $b_{cy}=0.6$, $b_h=0.3$ and $b_w=0.3$.

Considering this, the output of the grid well will be as shown below.

$$Y=\begin{bmatrix}p_c\\c_1\\c_2\\c_3\\b_{cx}\\b_{cy}\\b_h\\b_w\end{bmatrix}=\begin{bmatrix}1\\0\\1\\0\\0.5\\0.6\\0.3\\0.3\end{bmatrix}$$

The overall output of the model will consist of 72 elements, i.e., the outputs of all the grid cells as shown below:

![3X3X8](https://i.ibb.co/GRTqMsX/3x3x8.png)
$$3X3X8$$
Remember that as you increase the number of grid cells, the time required for processing would also increase, although doing so would provide greater accuracy as the network would become more sensitive.

Now, answer these questions based on your learning so far.

#### YOLO

Qn: What would be the number of elements in the overall output vector if the objects to be detected are facemasks and spectacles on human faces and the YOLO model divides the image into a $3X3$ grid?

- 72

- 54

- 63

- 81

Ans: C. *The number of elements in the overall output vector can be given as s∗s∗(c+5), where c is the number of classes and s∗s represents the dimensions of the grid. Therefore, you will get $3*3*(2+5)=63$.*

Qn: Suppose you are to detect cats, dogs and rabbits in a given image. The image is divided into a 3X3 grid, and only one of the cells contains an object such that $b_{cx}=0.7$, $b_{cy}=0.5$, $b_h=0.4$ and $b_w=0.1$, and the probability of detection of the object is 1.

From the options below, select the correct output vector for a grid cell if the object detected is a cat where $c_1$ = cat, $c_2$ = dog, $c_3$ = rabbit. 

- $\begin{bmatrix}1\\1\\0\\1\\0.7\\0.5\\0.4\\0.1\end{bmatrix}$

- $\begin{bmatrix}1\\1\\0\\0\\0.7\\0.5\\0.4\\0.1\end{bmatrix}$

- $\begin{bmatrix}1\\1\\1\\0\\0.7\\0.5\\0.1\\0.4\end{bmatrix}$

- $\begin{bmatrix}1\\1\\0\\0\\0.7\\0.5\\0.1\\0.4\end{bmatrix}$

Ans: B. *The cell output can be given as $\begin{bmatrix}p_c\\c_1\\c_2\\c_3\\b_{cx}\\b_{cy}\\b_h\\b_w\end{bmatrix}$,* 
*where $p_c=1$, $c_1=1$ (cat), $c_2=0$ (dog), $c_3=0$ (rabbit), $b_{cx}=0.7$, $b_{cy}=0.5$, $b_h=0.4$ and $b_w=0.1$.*
*Therefore, you will get the following as output: $\begin{bmatrix}1\\1\\0\\0\\0.7\\0.5\\0.4\\0.1\end{bmatrix}$*

#### Coordinates

Qn: Let us consider the image given below:

![Coordinates Qn 1](https://i.ibb.co/37DmrQH/YOLO-Input-Image.png)

The YOLO detector divides the image into a grid. Here, let us consider a 3 X 3 grid as shown below:

![Coordinates Qn 2](https://i.ibb.co/q98hhbJ/YOLO-Preprocessing.png)

If you build a bounding box across the object detected, you will get the image shown below:

![Coordinates Qn 3](https://i.ibb.co/pwBYLTb/Coordinates-Qn-3.png)

The bounding box vector will consist of 4 elements ie., $b_{cx}$, $b_{cy}$, $b_h$ and $b_w$. For this bounding box vector thus obtained, select the correct options:

- The values of $b_{cx}$ and bw are relative to the grid cell and are subject to change if the grid cell dimensions change.

- The values of $b_h$ and $b_w$ are relative to the image dimensions. They will not change even if the grid cell dimensions change.

- The values of $b_w$ and bcy are relative to the image dimensions. They will not change even if the grid cell dimensions change.

- The values of $b_cx$ and $b_cy$ are relative to the grid cell and are subject to change if the grid cell dimensions change.

- The values of $b_{cx}$ and $b_{cy}$ are relative to the image dimensions. They will not change even if the grid cell dimensions change.

Ans: B & D. *The values of $b_h$ and $b_w$ correspond to the object and do not change with the change in grid cell dimensions. The values of $b_{cx}$ and $b_{cy}$ are relative to the grid cell and can change if the grid cell dimensions vary.*

So, this is how the YOLO model works and how the output is predicted. Moving ahead, in the upcoming segment, you learn how to analyse the results of the network and the evaluation metrics of the model.