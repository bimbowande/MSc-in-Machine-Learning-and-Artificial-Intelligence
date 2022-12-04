# Graded Questions

The questions below are graded. All the best!

#### Image Segmentation

Qn: Which of the following statements is incorrect?

- Image segmentation involves the generation of a segmentation mask that classifies each pixel in the image.

- Instance segmentation is used to explore different instances of a class.

- Semantic segmentation uses bounding boxes to draw segmentation masks over the images.

- Image segmentation can be leveraged in autonomous driving, satellite imagery, medical imaging, etc.

Ans: C. *This is not true as seen in the U-Net model. The pixel map is generated over the entire image.*

#### Semantic Segmentation

Qn: Which of the following outputs are generated under semantic segmentation implemented using the U-Net framework?

- Object class

- Bounding box

- Segmentation mask

Ans: A & C. *Object class helps in differentiating the different segments of the output. This is the key output from any segmentation-based model.*

Qn: Which of the following statements is true?

- A simple CNN architecture cannot be used to implement the task of semantic segmentation.

- Encoder-decoder architecture maintains the size of the image throughout the network to generate same-sized images like the input.

- A simple CNN architecture can be configured as both - encoder and decoder.

Ans: C. *A simple encoder-decoder framework is built using CNN layers only. So, they can be configured to build the encoder and the decoder sections.*

#### U-Net

Qn: Which of the following element distinguishes the U-Net framework from an encoder-decoder framework?

- Convolutional layers

- Skip connections

- FC layers

- Pooling layers

Ans: B. *This is the differentiating element between the U-Net and the encoder-decoder framework as it connects the layers from the encoder section to the decoder.*

#### Dice Coefficient

Qn: Compute the Dice coefficient for the image prediction provided in the image below. Note that black denotes the predicted bounding box and red denotes the ground truth bounding box.

![Bounding Box Qn](https://i.ibb.co/7kjN4tq/Bounding-Box-Qn-3.png)

Round off your answer to the nearest one's place. For example, 57.8% will become 58%.

- 76%

- 84%

- 91%

- 96%

Ans: D. *Let us understand the computation step by step:* 

- *Step 1: Compute the coordinates of the intersection box from the predicted and ground truth bounding boxes, as shown below:*

![Bounding Box](https://i.ibb.co/s9hbXnw/Bounding-Box-Ans-1.png)

- *Step 2: The coordinates of the intersection box are highlighted in the image above. Use these coordinates to compute the area of intersection, as shown below:  L = 517 - 255 = 262 and B = 525 - 207 = 318. Therefore, area = L \* B = 262 \* 318 = 83316.*

- *Step 3: Now, we will compute the area of the predicted and ground truth boxes to add them together. The area of the black box is (525-200)*(525-255) = 87750. The area of the red box is (527-207)*(517-250) = 85440.*

![Bounding Box Qn](https://i.ibb.co/7kjN4tq/Bounding-Box-Qn-3.png)

*Now, we will perform the required calculations.*

- Step 4: Compute the Dice Coefficient  
$DC=\dfrac{2*\text{Area of intersection}}{\text{Combined area}}=\dfrac{2* 83316}{(87750+85440)}=0.962$, or 96%