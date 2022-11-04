# RCNN

As you learnt in the previous segment, FCNNs cannot be used as object detectors because they require you to divide the input image into a subset of multiple smaller images, which, when fed to the classifier, require a lot of processing time.

One way to solve this problem would be to partition the input image into **several regions** and to use a CNN to classify the presence of the object within each region. This is essentially the principle behind region-based methods, which will be covered in this session.

As the name suggests, a **region-based approach** works with a **region proposal** that extracts the important areas/regions from the image and performs **feature extraction** and **classification** on them. There are three types of region-based methods, which are as follows:

1.  RCNN
2.  Fast RCNN
3.  Faster RCNN

As you learnt earlier, using sliding windows to extract a subset of images that have to be fed to the classifier will give you thousands of images. Do you require all of these images? 

Let’s watch the next video to learn how to deal with this problem using the RCNN algorithm.

**VIDEO**

Instead of having thousands of input images fed into the feature extractor, RCNNs use **region proposals**. These regions are proposed using the selective search technique to extract 2,000 different regions from the given image. 

The process of extracting region proposals occurs in three steps, which are as follows:

1.  The algorithm calculates an initial picture sub-segmentation. This results in a large number of possible regions.  
     
2.  The algorithm recursively combines comparable sections into larger ones using the **greedy approach**.  
     
3.  The algorithm proposes the final potential regions using these larger regions.

Note: Understanding this approach is a bit complicated and irrelavant from the industry perspective and hence is kept out of scope of the syllabus. But curious students can read more about the selective search technique and greedy approach in RCNN [here](https://learnopencv.com/selective-search-for-object-detection-cpp-python/).

Try to answer this simple question based on your understanding of the selective search technique and greedy approach.

#### Region Proposals

Qn: You were introduced to the concept region proposals in RCNN. Which of the following statements is/are correct regarding selecting region proposals using the selective search technique and greedy approach?

- The selective search technique divides the given image into different regions based on the classes of the objects.

- The model selects similar regions and combines them into one large region using the greedy approach.

- The selective search technique divides the input image into different regions based on the pixels of the image.

- The greedy approach breaks down one large region into smaller similar regions.

Ans: B & C. *The greedy approach combines smaller similar regions into one larger region. The selective search algorithm divides the input image into different regions based on the pixels of the image.*

These regions obtained are then warped and squared and finally fed into a CNN, which functions as a feature extractor. Once the features are extracted, they are fed into an SVM to verify the presence of objects in them. Additionally, the values of the bounding box vector are given as an output by this algorithm, as shown in the image below.

![RCNN](https://i.ibb.co/9v78nrm/RCNN.png)

However, this method has certain limitations due to which it is not actively used in the industry today. Let’s watch the next video to learn about these limitations.

**VIDEO**

As you learnt in the video above, the RCNN algorithm for object detection has certain limitations, some of which are as follows:

1.  Having 2,000 region proposals per image being fed into the feature extractor requires a lot of time and resources, thereby making the process extremely slow.  
     
2.  Even deployment is quite slow, which makes it difficult for one to use the algorithm for real-world applications.  
     
3.  The selective search algorithm does not learn, which can lead to the generation of bad proposals.  
     
4.  SVM used as classifiers do not produce highly accurate results.

Answer the following questions to reinforce your understanding of the topic covered in this segment.

#### RCNN

Qn: Which of the following is a disadvantage of the RCNN model?

- A large number of region proposals increases the training time of the model.

- Usage of the selective search algorithm.

- The predictions made by SVM might not be of high accuracy.

- All of the above

Ans: D. *All these options are the disadvantages of the RCNN model.*

Some of the issues associated with the RCNN model can be handled using the Fast RCNN method. In the next segment, you will learn about **Fast RCNN**.

## Additional Links

If you wish to dive deeper into this algorithm, you can go through the links provided below.

1.  You can learn more about RCNN and the other algorithms of the region-based family [here](https://d2l.ai/chapter_computer-vision/rcnn.html).
2.  You can read more about region proposals in RCNN [here](https://pallawi-ds.medium.com/step-by-step-understand-the-architecture-of-region-proposal-network-r-cnn-695a14a060a7).