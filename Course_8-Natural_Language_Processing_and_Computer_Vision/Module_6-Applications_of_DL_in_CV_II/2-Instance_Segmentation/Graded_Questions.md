# Graded Questions

The questions below are graded. All the best!

#### Instance segmentation

Qn: Which of the following statements are true for instance segmentation?

- Instance segmentation uses convolutional layers to extract different features from the image.

- Each instance of an object is segmented as a different entity in instance segmentation.

- You can only analyse one object class at a time through instance segmentation.

Ans: A & B. *Every computer vision framework is generally built on top of CNN layers which is true for instance segmentation as well. Instance segmentation treats each instance of an object class as an individual entity.*

#### Mask R-CNN

Qn: Which of the following techniques does the Mask R-CNN use to generate the anchor boxes?

- Selective search

- Region proposal network

Ans: B. *The Mask R-CNN framework is built on top of Faster R-CNN which uses the Region proposal network to generate the candidate bounding boxes.*

Qn: Which of the following outputs are generated by the Mask R-CNN architecture?

- Object labels

- Bounding box

- Segmentation mask

Ans: All of the above. *Object class helps in differentiating the different segments of the output. Mask R-CNN framework also generates the bounding boxes for identified objects in the image. Segmentation mask is the key output from any segmentation-based model.*

Qn: Which of the following statements are correct with respect to the Mask R-CNN framework?

- The architecture is built on top of the Faster R-CNN framework.

- The backbone network is responsible for the generation of anchor boxes to search for the desired object class.

- RoI Pooling layer normalises the shape of the anchor boxes for the architecture for further processing.

- The first stage of the architecture comprises the backbone and the region proposal network.

Ans: A, C & D. *The module for the segmentation mask is added to the Faster R-CNN framework. The Region Proposal Network. generates bounding boxes of different sizes which are normalised before feeding into the classifier, regressor or segmentation mask. The first phase of the architecture is responsible for the generation of the candidate bounding boxes.*
