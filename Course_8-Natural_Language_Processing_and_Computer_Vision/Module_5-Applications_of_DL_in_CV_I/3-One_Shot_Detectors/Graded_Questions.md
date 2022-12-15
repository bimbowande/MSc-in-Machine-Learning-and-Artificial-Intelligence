# Graded Questions

The questions below are graded. All the best!

#### Anchor Boxes

Qn: Which of these statements about anchor boxes is true?

- They help detect objects if more than one centroid is present in the same cell of a grid.

- They are bounding boxes used to detect multiple objects in the same area.

- Anchor boxes are used by the SSD to predict the locations of objects.

- Anchor boxes are used by the YOLO model to detect overlapping objects.

Ans: A, B & C. *The YOLO model uses anchor boxes to detect objects if more than one object lies within a single grid cell. Anchor boxes are nothing but bounding boxes used by YOLO to detect multiple overlapping images.*

#### IoU

Qn: Given below are two IoU scores. The bounding box associated with which of them will be rejected?

- 45%

- 70%

Ans: A. *NMS rejects bounding boxes with low IoU scores, and 50% is a very low IoU score.*

#### SSD

Qn: Which of these statements about the SSD is correct?

- It makes four predictions per cell.

- SSD uses two passes out of which one is required to detect the class of the object and the other one to localise the object.

- It is one of the fastest object detectors.

Ans: A. *SSD makes four predictions per cell.*

Qn: You know that the SSD detects objects at different scales, which enables it to detect multiple overlapping objects of different sizes. How does YOLO detect multiple partially overlapping objects?

- Non-maximal suppression

- Default bounding boxes

- Anchor boxes

- Convolutional layers

Ans: C. *Anchor boxes in YOLO predict multiple overlapping objects with their centroids in the same grid cell.*

#### Object Detectors

Qn: OpenCV reads the input image in which of the following formats?

- RGB

- GBR

- BGR

- RBG

Ans: C. *OpenCV reads the input image in the BGR format.*

Qn: Which of the following detectors would you use if you wanted to work on a real-time problem and the task required good accuracy?

- SSD

- Fast-RCNN

- Faster-RCNN

- YOLO

Ans: A. *The SSD provides good accuracy along with good speed.*
