# Summary

Let’s hear about the concepts covered in this session in the upcoming video.

**VIDEO**

In this session, you were first introduced to the concept of image segmentation. It also highlighted that it differs from object detection as you segment every pixel of the image into a class as part of this algorithm. 

After the basic understanding, the session focused on different types of image segmentation. Semantic segmentation is used to segment different classes present in the image, however, instance segmentation takes this one step further by segmenting each instance of the class separately.

![Types of Image Segmentation](https://i.ibb.co/hMp2ZwX/Types-of-Image-Segmentation.png)

Source: PASCAL VOC, [Harshall Lamba - Towards Data Science](https://towardsdatascience.com/understanding-semantic-segmentation-with-unet-6be4f42d4b47)

Next, you were introduced to different industrial applications of image segmentation. You saw how it can help in surveillance, autonomous driving, medical imaging, analysing satellite imagery and image processing.

![Downsampling Upsampling](https://i.ibb.co/z4s4Zrm/Downsampling-Upsampling.png)

The session then moved to semantic segmentation and covered the encoder-decoder architecture in detail. The two key processes involved in this framework are downsampling and upsampling. The U-Net architecture also follows the same framework but uses skip connections to connect the encoder and decoder sections of the architecture. Skip connections are extremely helpful in the reconstruction of the image during upsampling. One of the techniques used for upsampling is transposed convolution which was explored in the session.

![U-Net Model Skip Connections](https://i.ibb.co/DLvpR7W/Skip-Connections.png)

After the model is ready, you can use the dice coefficient to evaluate the performance. The higher value of the dice coefficient suggests that the model is performing well on the underlying data set. 

Lastly, the session focused on a simple demonstration of lung segmentation using the U-Net architecture. You worked with the existing code repository to build, train and evaluate the model. Now, the next session will focus on the second type of image segmentation - instance segmentation.
