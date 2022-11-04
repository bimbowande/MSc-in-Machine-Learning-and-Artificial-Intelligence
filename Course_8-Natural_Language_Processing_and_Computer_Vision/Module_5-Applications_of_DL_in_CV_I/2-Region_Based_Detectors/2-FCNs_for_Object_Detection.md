# FCNs for Object Detection

You learnt about fully connected convolutional neural networks (FCNs) in one of the previous modules, wherein you used them to classify images. Let’s quickly refresh your knowledge of FCNs by answering the following questions.

#### FCNs

Qn: Which of the following statement(s) is/are correct regarding FCNs?

- All the neurons of one layer are connected to all the neurons of the next layer.

- Much like CNNs, FCNs also have assumptions regarding the input image that are taken into consideration.

- FCNs are prone to overfitting.

Ans: A & C. *FCNs, as the name suggests, are fully connected convolutional networks, wherein each node of one layer is connected to all the nodes of the next layer. FCNs learn rigorously on the training data. The dense connections and the learning pattern may lead to overfitting.*

Qn: FCNs use sliding windows to analyse the input image. These sliding windows move in strides. What is the stride of the sliding window in FCNs?

- 1

- 2

- It is customisable and can be adjusted.

Ans: A. *The sliding window stride in FCNs is one.*

But can you perform the task of detecting objects using FCNs? Well, no, you cannot. 

FCNs cannot be used as object detection algorithms because some of their properties act as limitations in the case of object detection tasks. Let’s watch the next video to understand why FCNs are not suitable for object detection. 

**VIDEO**

As you learnt in the video above, FCNs cannot be used for object detection due to certain reasons, which are as follows:

1.  The length of the output layer in object detection tasks is variable, as the number of objects/occurrences is unknown and varies. This unknown length of the output layer cannot be handled using FCNs.  
     
2.  FCNs use sliding windows, with a stride of one, which will end up slowing down the operation.  
    **Sliding windows** slide through the image in rectangular steps of equal size to extract different areas from the entire image. This windowed image is then fed to feature extractors and classifiers in the case of FCNs. Using sliding windows to extract a subset of images that have to be fed to the feature extractor will give you thousands of such images in that subset.  
     
3.  Having thousands of these images being fed to the classifier will increase the time and memory requirement of the model, which is counterproductive. 

Therefore, using FCNs is not the most effective way to deal with object detection problems. 

  
One alternative to deal with the limitations of FCNs is to divide the input image into smaller images and then feed them to the CNN, i.e., the classifier. This technique of slicing the input image into smaller images has its own disadvantages, which are as follows:

1.  The objects that are of importance may have different spatial locations within the image.  
     
2.  The objects of interest will have different aspect ratios in the smaller images.  
     
3.  This technique requires you to feed a very large number of smaller images of overlapping regions, which, even though reduces the time required for computation as compared to FCNs, still requires large computational resources.

Therefore, either using FCNs or feeding multiple sub-images of the input image to the CNN is not suitable for real-time object detection problems. In the upcoming segment, you will learn about region-based object detection techniques, which can be used to solve some of the problems that you have encountered so far.