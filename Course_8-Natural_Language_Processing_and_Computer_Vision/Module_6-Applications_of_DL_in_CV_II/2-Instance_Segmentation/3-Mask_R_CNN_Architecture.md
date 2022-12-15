# Mask R-CNN: Architecture

The previous segment helped with the basic understanding of the Mask R-CNN architecture. As mentioned before, the Mask R-CNN architecture comprises two stages. This segment will focus on different networks present in these two stages:

-   Backbone
-   Region Proposal Network (RPN)
-   Region of Interest
-   Segmentation Masks

## Backbone

Let’s first hear about the networks in the first stage of the architecture. The upcoming video will focus on the backbone network of the architecture.

**VIDEO**

Backbone is a standard convolutional neural network (such as ResNet, VGG, Inception, etc.) that is responsible for extracting the features from the image. The output from this network is the feature maps that are fed to the other networks as input. 

![Convolutional Network outputs Feature Map](https://i.ibb.co/ZJXX3f8/Convolutional-Network-outputs-Feature-Map.jpg)

#### Mask R-CNN: Backbone

Qn: Mention the input and output for the backbone section of the Mask R-CNN framework.

Ans: *Being the first section, the input to the backbone section is the original or resized image. As this is a simple CNN structure, the output is a collection of feature maps that capture the high-level features present in the image.*

The next component that follows the backbone is the Region Proposal Network (RPN) covered in the upcoming video.

**VIDEO**

The video above covered the following components:

-   Region Proposal Network (RPN)
-   Region of Interest (RoI) Classifier and Bounding Box Regressor

## Region Proposal Network (RPN)

RPN scans the image in a sliding window fashion (like filters in CNNs) and proposes the regions of the image which may contain objects. The network uses anchors to scan different parts of the image. They are a set of boxes with predefined sizes and scales relative to the images. The RPN generates two outputs for each anchor:

1.  Anchor class: Foreground or background   
    The foreground class implies that it is likely that an object is present in that anchor box.
2.  Bounding Box Refinement: Spatial displacement and resizing  
    This is an estimation of percentage change in the dimensions and the position of the bounding box (x, y, width, height) to refine the anchor box to fit the object better.

![Region Proposal Network (RPN)](https://i.ibb.co/8xTzYnj/Region-Proposal-Network-RPN.jpg)

In case multiple anchors overlap, the network uses the **IoU score** to select the most optimal anchor box to form the proposed region. You have already learnt this under the concept of Non-max Suppression. The final anchor boxes or the proposal regions are called Regions of Interest (ROIs) which are passed onto the next stage.

## Region of Interest (RoI) Classifier and Bounding Box Regressor

This network is part of the second stage of the architecture. There are two sources of inputs for this network. Backbone network provides the feature maps to classify the objects and the RPN is responsible for delivering the Regions of Interest (ROIs) to locate them in the image. Therefore, this part of the architecture is responsible for generating two outputs for each ROI:

-   **Class**: This is the class of the object in the ROI.
-   **Bounding box refinement**: This is similar to the RPN as it also tries to refine the location and size of the bounding box to encapsulate the object.

![Region of Interest (RoI) Classifier and Bounding Box Regressor](https://i.ibb.co/yWRh0YG/Region-of-Interest-Ro-I-Classifier-and-Bounding-Box-Regressor.jpg)
_(Note: This is not the actual architecture)_

#### Mask R-CNN

Qn: Which of the following statements is/are correct?

- The Region Proposal Network provides the final bounding boxes with labels for the images.

- The RoI classifier is used to generate the bounding boxes for the final output.

- The output from RPN is fed into the RoI classifier and regressor directly.

- The RoI Regressor is used to generate the segmentation masks for the image.

- None of the above.

Ans: D. 

- *RPN is responsible for generating candidate bounding boxes, not the final output.*

- *The role of the classifier is to use the feature maps to generate the labels for the bounding box.*

- *There is an RoI Pooling or RoI Align layer between the two sections which is covered in the next video.*

- *RoI Regressor is responsible for the refinement of bounding boxes.*

However, there is one problem with the process if the output from RPN is fed into the classification layer. The ROIs could be of varied sizes, which can make it difficult for the architecture to classify them under the same class. Let’s see how the architecture copes up with this problem in the upcoming video.

**VIDEO**

## ROI Pooling

The ROI pooling layer helps in standardising the size of the ROIs obtained from the RPN by cropping a part of the feature maps and resizing them to a fixed size. The image below summarises the function of the layer.

The ROIAlign is another way to solve the issue and obtain uniform ROIs. In this method, the feature map at different points can be sampled, and bilinear interpolation (upsampling) is applied on top of it to generate uniform sizes.

![ROI Pooling](https://i.ibb.co/bRXT17r/ROI-Pooling.jpg)

All the components discussed above form the Faster R-CNN architecture. Let’s now listen to Georgios about the segmentation mask network which differentiates Mask R-CNN from Faster R-CNN.

**VIDEO**

## Segmentation Mask

The mask network is the addition to the Faster R-CNN that the Mask R-CNN paper introduced. This convolution network takes the output from the ROIAlign layer (or ROI Pooling) and is responsible for generating the segmentation masks for the regions identified by the ROI Regressor. The masks generated by this network are smaller in size (28 x 28 pixels) which helps in keeping the computation time in check. However, these masks are upsampled during model inference to fit the size of the ROI obtained from the previous layers. The image below summarises the entire architecture.

![Segmentation Mask](https://i.ibb.co/qx7cYg3/Segmentation-Mask.jpg)

#### Mask R-CNN

Qn: Which of the following components is responsible for the generation of bounding boxes in the Mask R-CNN architecture?

- Region Proposal Network

- RoI Pooling

- Regressor

- Segmentation mask

Ans: C. *The regressor helps in generating the final bounding box in the output.*

Now, you must have a clear understanding of the Mask R-CNN architecture. You will now use this framework to work on a case study for oil tanker segmentation.