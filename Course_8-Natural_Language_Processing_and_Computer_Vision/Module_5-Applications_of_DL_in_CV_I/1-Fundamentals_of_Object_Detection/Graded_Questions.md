# Graded Questions

The questions below are graded. All the best!

Earlier you solved a comprehension where you were provided with the bounding box vertices and you were required to compute the IoU, loss, etc. In the upcoming questions, you will be given the bounding box vector from which you will first compute the vertices of the bounding box. Recall that a bounding box vector is given by:
$$\large{\begin{bmatrix}b_x\\b_y\\b_h\\b_w\end{bmatrix}}$$

where -

1.  $b_x$ = The _x_ coordinate of the centroid, 
2.  $b_y$ = The _y_ coordinate of the centroid,
3.  $b_h$ = The height of the bounding box and
4.  $b_w$ = The width of the bounding box.

## Comprehension

Let us take this simple example, where you are provided with the ground truth and predicted bounding boxes:

Predicted bounding box $=\begin{bmatrix}b_x\\b_y\\270\\325\end{bmatrix}$
 

Ground truth bounding box $=\begin{bmatrix}b_x\\b_y\\267\\320\end{bmatrix}$

Let us denote the vertices of the predicted bounding box with this notation.

![IoU Graded Question](https://i.ibb.co/qRwbFym/Io-U-Graded-Question.png)

You are also provided with the coordinates of the first point for both the predicted and the ground truth bounding box as mentioned below:

-   Predicted bounding box - A1 coordinates: (200, 255)
-   Ground truth bounding box - A2 coordinates: (207, 250)

Similarly, for the ground truth box, the notation will be A2, B2, C2 and D2, in the same order. This notation will be applied while answering the following questions, which are based on this comprehension.

#### Coordinates of The Bounding Box

Qn: Select the correct coordinates of B2 for the ground truth bounding box? Note: B2 is a part of the notation used for the coordinates of the ground truth bounding box.

- (517, 207)

- (200, 525)

- (207, 517)

- (527, 250)

Ans: C. *We have the following information: $A2=(207,250)$, $b_h=267$ and $b_w=320$. You can visualise this information in the picture given below:*

![Coordinates of the Bounding Box](https://images.upgrad.com/7d139223-80f2-4215-8a9e-c8a8df358e43-pc.PNG)

The starting point, A2, will be (207, 250). Now, B2 has the same x-coordinates as A2, and its y-coordinates can be given as $y(A2)+b_h=250+267=517$. Therefore, $B2=(207, 517)$.

Qn: Select the correct coordinates from the options given below. Hint: More than one options may be correct.

- C1 = (525, 525)

- C1 = (525, 255)

- D1 = (525, 255)

- D2 = (527, 250)

Ans: A, C & D. 

- You can compute the coordinates of C1 as shown below:  $C1=(x(A1)+b_w, y(A1)+b_h)=(200+325,255+270)=(525,525)$

- You can compute the coordinates of D1 using the formula shown below:  
$D1=(x(A1)+b_w,b_y)=(200+325,255)=(525,255)$

- You can compute the coordinates of D2 using the formula shown below:  
$D2=(x(A2)+b_w,b_y)=(207+320,250)=(527,250)$

#### Centroid of Predicted Bounding Box

Compute the coordinates for the centroid $(b_{cx}, b_{cy})$ of the predicted bounding box.

Hint: The centroid of a rectangle can be computed by using the following formula:
$$(b_{cx},~b_{cy})=\left(\dfrac{(x_1+x_2}{2},~\dfrac{y_1+y_2}{2}\right)$$
Where $(x_1,~y_1)$ and $(x_2,~y_2)$ are the opposite points of the bounding box as shown below:

![Centroid of Predicted Bounding Box](https://i.ibb.co/zh38j2C/Centroid-of-Predicted-Bounding-Box.png)

- (362.5, 389)

- (365, 390)

- (362.5, 390)

- (362, 389)

Ans: C. You can compute the coordinates of the centroid of the predicted bounding box by using the formula given below:  
$b_{cx}=\dfrac{x(A1)+x(C1)}{2}\text{ or }\dfrac{x(B1)+x(D1)}{2}$

$b_{cy}=\dfrac{y(A1)+y(C1)}{2}\text{ or }\dfrac{y(B1)+y(D1)}{2}$

You will obtain the same results on using any of the two opposite vertices ie., A and C or B and D.  
$b_{cx}=\dfrac{x(A1)+x(C1)}{2}=\dfrac{200+525}{2}=362.5$  
$b_{cy}=\dfrac{y(A1)+y(C1)}{2}=\dfrac{255+525}{2}=390$

#### Bounding Box Vector

Qn: Compute the coordinates of the centroid of the ground truth bounding box and then select the correct ground truth bounding box vector based on your calculations.

- $\begin{bmatrix}367\\383.5\\267\\320\end{bmatrix}$

- $\begin{bmatrix}383.5\\367\\267\\320\end{bmatrix}$

- $\begin{bmatrix}367\\383.5\\320\\267\end{bmatrix}$

- $\begin{bmatrix}383.5\\367\\320\\267\end{bmatrix}$

Ans: A. *Given:* 

$A2:~(207,~250)$

$b_h: 267$

$b_w:~320$

You have already computed $C2:~(527,~517)$

You can compute the centroid coordinates as follows:   
$b_{cx}=\dfrac{x(A2)+x(C2)}{2}=\dfrac{207+527}{2}=367$  
$b_{cy}={y(A2)+y(C2)}{2}=\dfrac{250+517}{2}=383.5$

Therefore, the bounding box vector will be:

$\begin{bmatrix}b_{cx}\\b_{cy}\\b_h\\b_w\end{bmatrix}=\begin{bmatrix}367\\383.5\\267\\320\end{bmatrix}$

#### Bounding Box

Select the correct predicted and ground truth bounding boxes from the options given below.

Note: Black denotes the predicted bounding box and red denotes the ground truth bounding box.

- ![Bounding Box Qn 1](https://i.ibb.co/znBzD0C/Bounding-Box-Qn-1.png)

- ![Bounding Box Qn 2](https://i.ibb.co/zxXVL7W/Bounding-Box-Qn-2.png)

- ![Bounding Box Qn 3](https://i.ibb.co/7kjN4tq/Bounding-Box-Qn-3.png)

Ans: A. *This is the correct representation of the two bounding boxes.*

#### IoU

Qn: Compute the IoU for the bounding boxes in this comprehension. Use the correct bounding box representation from the previous question for reference. Hint: First, compute the coordinates of the intersection box and the union box and then compute the area of the two boxes to compute the IoU. Round off your answer to the nearest one's place. For example, 57.8% will become 58%.

- 85%

- 59%

- 100%

- 93%

Ans: D. Let us understand the computation of the IoU step by step:  

- **Step 1**: Compute the coordinates of the intersection box from the predicted and ground truth bounding boxes, as shown below:

![Bounding Box Ans 1](https://i.ibb.co/s9hbXnw/Bounding-Box-Ans-1.png)

- **Step 2**: The coordinates of the intersection box are highlighted in the image above. Use these coordinates to compute the area of intersection, as shown below:  
$L=517-255=262$ and $B=525-207=318$

Therefore, $area=L*B=262*318=83316$.

- **Step 3**: Now, we will compute the area of union of the predicted and ground truth boxes. It can be computed by adding the area covered by the predicted and ground truth boxes and subtracting the area of intersection from the result. 

The area of intersection is subtracted as it will be added twice since it is present in the area of both the boxes separately. Use the coordinates of the two boxes, as shown below.

![Bounding Box Ans 2](https://i.ibb.co/znBzD0C/Bounding-Box-Qn-1.png)

Now, we will perform the required calculations.

Area of the predicted bounding box $=270*325=87750$  
Area of the ground truth bounding box $=267*320=85440$

Area of union $=87750+85440-83316=89874$

- **Step 4**: Compute the IoU  
IoU = Area of intersection / Area of union $=\dfrac{83316}{89874}=0.927$, or 93%