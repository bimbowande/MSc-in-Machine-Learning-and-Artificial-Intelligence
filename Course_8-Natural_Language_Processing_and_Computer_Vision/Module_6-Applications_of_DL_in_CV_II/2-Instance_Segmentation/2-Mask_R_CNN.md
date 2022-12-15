# Mask R-CNN

As the name suggests, Mask R-CNN is a region-based convolutional neural network (CNN) that specialises in instance segmentation. It is considered as a state-of-the-art model for instance segmentation. This framework was developed by Kaiming He and a team of researchers at Facebook AI Research (FAIR) and is an extension of the Faster R-CNN architecture, which is used for object detection.

Let’s hear about the Mask R-CNN framework from Georgios in the upcoming video.

**VIDEO**

_**Note**: The Mask R-CNN framework is built on top of Faster R-CNN. All the components associated with this framework have been covered before. Therefore, this session will not only provide a quick walkthrough of all the concepts._

Mask R-CNN is also a region-based CNN that is one of the leading architectures for image segmentation. The architecture is built on top of Faster R-CNN. If you recall, the Faster R-CNN provided two outputs for all the objects detected in the image: a class label and a bounding-box offset. Mask R-CNN adds another branch to the framework that is responsible for generating the object mask. Hence, there are three outputs at the end of the Mask R-CNN. However, this additional mask output is distinct from the class and box outputs and requires the extraction of a more refined spatial layout of an object.

![Mask R-CNN](https://i.ibb.co/WkW0JBC/Mask-R-CNN.jpg)

Like the Faster R-CNN, Mask R-CNN also has two stages:

-   The first stage of the architecture is responsible for the generation of the proposals about the regions where the object might be present in the input image. 
-   In the second stage, the architecture uses the region proposals to produce the output by predicting the class of the object, refining the bounding box, and generating a mask at the pixel level of the object.   

![Faster R-CNN](https://i.ibb.co/tqRpyxD/Faster-R-CNN.png)
_Source: [Mask R-CNN (FAIR)](https://arxiv.org/pdf/1703.06870.pdf)_

#### Region-based models

Qn: Which of the following is not a region-based model?

- R-CNN

- Fast R-CNN

- YOLO

- Mask R-CNN

Ans: C. *It is a one-shot detector. Hence, this is the correct answer.*

#### Mask R-CNN

Qn: Select all the components of a Mask R-CNN architecture.

- Backbone

- Region Proposal Network (RPN)

- Region of Interest (RoI) Pooling

- Classifier

- Regressor

- Segmentation Mask

Ans: All of the above.

- *Backbone is the base of the Mask R-CNN framework that is responsible for feature extraction.*

- *Region Proposal Network (RPN) is useful for the generation of anchor boxes which are used to locate the objects in the image.*

- *Region of Interest (RoI) Pooling is responsible for generating same-sized regions for the architecture to run classification, regression and segmentation.*

- *Classifier is used to classify the detected object into a particular class.*

- *Regressor helps in refining the bounding box that encapsulates the identified object.*

- *Segmentation Mask block generates the segmentation mask for the object within the bounding box.*

Now that you have a basic understanding of the Mask R-CNN architecture, the future segments will cover the components of the Mask R-CNN architecture.

**Additional Reading**

-   [Mask R-CNN](https://arxiv.org/abs/1703.06870)