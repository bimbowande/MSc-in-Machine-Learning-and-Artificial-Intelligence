# An Analysis of Deep Learning Models

In the past few years, the performance of CNN-based architectures such as AlexNet, VGGNet and ResNet has been steadily improving. But while deploying deep learning models in practice, you usually need to consider multiple other factors besides accuracy. 

For example, suppose you have built a mobile app that uses a convolution network for real-time face detection. Since it will be deployed on smartphones, some of which may have low memory, etc., you might be more worried about it working 'fast enough' rather than the accuracy.  

In this segment, we will discuss a paper that appeared in 2017, '_[An Analysis of Deep Neural Network Models for Practical Applications](https://arxiv.org/pdf/1605.07678.pdf)_'. This paper compares the popular architectures on multiple metrics related to resource utilisation, such as accuracy, memory footprint, number of parameters, operations count, inference time and power consumption. So, let’s get started.

**VIDEO**

The video highlighted the relationship between the following elements associated with the models: 

-   **Accuracy**: This highlights the performance of the model on the validation set.
-   **Number of parameters**: This value highlights the volume of weights and biases associated with the architecture. For example, if you have a simple 3x3x3 filter to convolve an image, the number of parameters will be 28 (27 weights and 1 bias).
-   **Number of operations in a feedforward cycle**: This element highlights the number of operations performed by the architecture to classify one image. The architecture convolves the image using multiple filters across different layers, which involves multiple operations, such as multiplication and addition. Moreover, it also undergoes other operations such as pooling and normalisation. This value is a collective measure of all such operations performed to arrive at the final result.

An important point to note here is that although VGGNet (VGG-16 and VGG-19) is widey used, it is by far the most expensive architecture, in terms of the number of operations (and thus computational time) as well as the number of parameters (and thus memory requirement). 

![Model Comparision](https://i.ibb.co/59Pq5p1/Model-Comparision.jpg)

Let’s continue with some other results derived from the paper, in the upcoming video. 

**VIDEO**

To summarise, some key points that we discussed are as follows:

-   Architectures in a particular cluster, such as GoogleNet, ResNet-18 and ENet, are attractive, as they have small footprints (both memory and time) as well as pretty good accuracies. Because of low-memory footprints, they can be used on mobile devices, and because the number of operations is small, they can also be used in real-time inference.
-   In some ResNet variants (ResNet-34,50,101,152) and Inception models (Inception-v3,v4), there is a trade-off between model accuracy and efficiency, i.e., the inference time and memory requirement. 

In the next video, you will explore different parameters such as power consumption and batch size.

**VIDEO**

The video highlighted the following results:

-   There is a marginal decrease in the (forward) inference time per image with an increase in the batch size. Thus, it might not be a bad idea to use a large batch size if you need to. 

![Forward Time and Memory Utilization](https://i.ibb.co/sqRvS1K/Forward-Time-and-Memory-Utilization.jpg)

-   Up to a certain batch size, most architectures use constant memory, after which the consumption increases linearly with the batch size.
-   Power consumption is independent of the batch size and architecture. 
-   The number of operations in a network model can effectively estimate inference time. As it can be seen from the graph provided below, an increase in operations results in a proportional increase in inference time as well.

![Operation vs FeedForward](https://i.ibb.co/kBBpZSy/Operation-vs-Feed-Forward.jpg)

-   The research also tried to evaluate the models in terms of parameter space utilisation. They called this **information density** or **accuracy per parameter**. ENet stood out as the best architecture, as it was able to achieve accurate results with a very small number of parameters.

## Additional reading

-   Please go through this link for the paper on _[An Analysis of Deep Neural Network Models for Practical Applications](https://arxiv.org/pdf/1605.07678.pdf)._