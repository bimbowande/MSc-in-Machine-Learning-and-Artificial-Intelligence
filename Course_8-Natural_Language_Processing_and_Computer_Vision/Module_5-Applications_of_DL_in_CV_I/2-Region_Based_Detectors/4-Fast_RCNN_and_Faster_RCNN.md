# Fast RCNN and Faster RCNN

In the previous segment, you learnt about RCNN and how having 2,000 region proposals makes the algorithm slow. This problem can be solved by using Fast RCNN, which is a modified version of the RCNN algorithm. Let’s watch the next video to learn more about this new technique.

**VIDEO**

As you learnt in the video above, the Fast RCNN algorithm feeds the entire image as the input to the feature extractor, instead of feeding 2,000 region proposals. The feature extractor, CNN, then produces a feature map for the image from where the algorithm identifies the region proposals. This is done using a selective search method, similar to the one in RCNN.

Each region proposed for a single image is of different shapes and sizes, therefore, there is a need to convert them to the same shape. Each of these region proposals is then wrapped into squares and transformed into the same shape using a **region of interest (RoI) pooling layer**.

Finally, the output of the pooling layer is fed to the **fully connected layer**, which predicts the classes using the **softmax layer** and provides the bounding box coordinates for the object detected, as illustrated below.

![Fast RCNN](https://i.ibb.co/zSGpthY/Fast-RCNN.png)

This solves the problem of having a large number of region proposals, which in turn saves a lot of time. However, in Fast RCNN, you are still using the selective search method, which does not learn and might light up incorrect region proposals, as in the case of RNN. Additionally, the selective search method slows down detection as it requires a lot of time. Even though the Fast-RCNN is faster than RCNN but it is not suitable for real-time applications due to its slow speed. This is one of the main limitations of the Fast RCNN technique.

#### Fast RCNN

Qn: Which of the following are part of the Fast RCNN architecture?

- Pooling layer

- Classification layer

- ConvNet or CNN

- Region proposal network

Ans: A, B & C. *The Fast RCNN algorithm consists of a region of the interest pooling layer. The Fast RCNN algorithm consists of the classification layer at the end, which helps predict the class of the objects detected. The Fast RCNN algorithm consists of a CNN, which extracts the required features.*

Qn: Which of the following is true regarding Fast RCNN however incorrect in the case of the RCNN algorithm?

- 2,000 region proposals

- SVM

- A softmax layer

Ans: C. *The Fast RCNN algorithm uses a softmax layer as a classifier.*

This limitation can be solved using **Faster RCNN**. Instead of using selective search to propose regions, Faster RCNN uses a **region proposal network (RPN)** to select regions from the given image. 

The working of this algorithm is similar to that of the Fast RCNN algorithm. Additionally, Faster RCNN has one layer, which is the RPN. The feature map produced by the CNN is fed to the RPN. The RPN provides region proposals that are reshaped and fed into the RoI pooling layer. The last step is the same as it was in Fast RCNN, the output of the pooling layer is classified along with the bounding box vector. This solves the problems caused by using selective search techniques.

The architecture of Faster RCNN is illustrated below.

![Faster RCNN](https://i.ibb.co/WccCw6d/Faster-RCNN.png)

Try solving the following questions:

#### Faster RCNN

Qn: Which of the following statements is correct regarding the Faster RCNN model?

- It uses a region-proposal network.

- It is slower than the RCNN and Fast RCNN models.

- It uses SVM as a classifier.

- It uses the selective search algorithm.

Ans: A. *The Faster RCNN algorithm uses a region-proposal network instead of the selective search algorithm.*

Even though the Faster RCNN algorithm solves the problem of using selective search, it still cannot be used for some real-time applications due to certain limitations. Let’s watch the next video to learn about these limitations.

**VIDEO**

As you learnt in the video above, region-based techniques have the following properties:

1.  These algorithms work on a two-stage approach:
    1.  Proposing different regions
    2.  Processing these regions  
         
2.  The proposed regions, which have a high probability of the presence of the object, are processed. The object is then localised inside the image.
  
Even after various advancements from RCNN to Faster RCNN, these methods are still not fast enough to deal with real-time problems. Hence, they are not used actively in the industry today. 

#### Region-Based Detectors

Qn: Which of the following region-based detectors use selective search?

- RCNN

- Fast-RCNN

- Faster-RCNN

Ans: A & B. *The RCNN and Fast-RCNN detector uses the selective search technique to generate region proposals. The Faster RCNN detector does not use the selective search technique to generate region proposals. Instead, it uses a region proposal network.*

This brings us to the end of this session. Let’s proceed to the next segment to revisit your learnings regarding the region-based methods for object detection.

If you feel that you have not gained an in-depth understanding of the region-based class of algorithms, it is completely fine. The aim of this section was to provide you with a very high-level overview of this class of algorithms so that you can understand how object detection algorithms evolved before moving to the next class of algorithms, i.e. the one-shot detectors in the next session.

## Additional Reading

Curious students can utilise the following links to learn more about region-based detectors.

1.  You can read more about the RCNN family [here](https://lilianweng.github.io/lil-log/2017/12/31/object-recognition-for-dummies-part-3.html).
    
2.  Read more on the RoI pooling layer [here](https://towardsdatascience.com/region-of-interest-pooling-f7c637f409af).