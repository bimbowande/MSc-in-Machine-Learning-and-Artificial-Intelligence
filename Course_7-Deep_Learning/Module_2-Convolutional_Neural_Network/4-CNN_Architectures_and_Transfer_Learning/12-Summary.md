# Summary

Let’s recap the concepts covered in this session in the upcoming video.

**VIDEO**

In this session, you compared the architectures of some popular networks that have achieved state-of-the-art results in ImageNet: AlexNet, VGGNet, GoogleNet and ResNet.

Until VGGNet, most of the major innovations had appeared in the form of increased depth, smaller filters, etc. In 2014, GoogleNet introduced an unconventional idea in the form of the **Inception module**, which performs multiple parallel convolutions (1 x 1, 3 x 3, 5 x 5, pooling etc.) on the input. This enabled GoogleNet to increase both the depth and the 'width' of the network (it has 22 layers with multiple inception modules stacked one over another). 

In the quest for training deeper networks, the ResNet team introduced another novel idea, **skip connections**, which enabled training extremely deep networks by 'bypassing the additional layers if they do not learn anything useful, else keeping them'.   

Since these models have already been trained on millions of images and are, therefore, good at extracting generic features, they are well-suited to solve other computer vision problems (with no or little retraining). This is the main idea behind **transfer learning**.

In transfer learning, a pretrained network can be repurposed for a new task depending on how much the new task differs from the original one. We conducted multiple experiments to develop an understanding of how one can alter the values in order to achieve higher accuracy for the network.

Finally, we compared various popular CNN architectures in terms of metrics (other than accuracy), which are important considerations for deployment (inference time, memory requirements, etc.). We compared the architectures along metrics such as the number of parameters (proportional to memory), operations involved in a feed-forward (proportional to inference time), accuracy, power consumption, etc.

-   Some of the oldest architectures (AlexNet) are not suited for most tasks due to low accuracies.
-   Some of them are extremely accurate but have very high memory footprints (VGGNet).
-   There are some clear trade-offs between accuracy and efficiency (computational time and memory).