# Semantic Segmentation

Now, you have a basic understanding of image segmentation and the different industrial areas where it can be applied. Going forward, the session will focus on the concept of semantic segmentation. This segment will focus on the basic architecture used to implement semantic segmentation over an image.

Let’s hear from Georgios about this in the next video.

**VIDEO**

The video covered two different approaches to perform semantic segmentation.

###  Simple CNN framework

As mentioned before, semantic segmentation can be considered as pixel-level classification where each pixel can be segmented into a specific class. A very basic approach to solve the problem through neural networks can be simply stacking multiple convolutional layers to generate a final segmentation map. As the size of the input and the output is the same, you can either use kernels of size 1 x 1 or use padding to maintain the size across layers. With the increase in the number of layers, it takes more operations to obtain the final result. This makes the process computationally expensive as it involves the same sized layers at each level. Hence, this approach is not preferred.

![Simple CNN Framework](https://i.ibb.co/vdZSk8H/Simple-CNN-Framework.png)

### Encoder-decoder framework

Image segmentation uses the encoder-decoder framework to overcome the issues mentioned above. To optimise the computational burden, the encoder-decoder framework tries to systematically reduce the size of the input while learning the features to identify each class (encoder phase), and then reverse the process by upsampling the feature representation into a full-resolution segmentation map (decoder phase) to classify each pixel of the input image.

![Encoder-Decoder Framework](https://i.ibb.co/3rysCKb/Encoder-Decoder-Framework.jpg)

Let us now try to understand the encoder-decoder framework in a bit more detail. The architecture uses the convolutional neural network (CNN) as the base to perform the required functions. The process starts by taking an input image with a specific set of dimensions (for example, an RGB image of size 224 x 224 x 3). In the first part, the image is processed using an **encoder**. This part acts as the feature extractor where all the features are learnt in a hierarchical order using CNN layers. In the process, the image undergoes different operations like convolution, pooling, etc. resulting in spatial reduction which is known as **downsampling**. The extracted features are stored compactly in the form of feature maps. If you try to summarise the output from the encoder phase, the information stored in the entire image is basically encoded in fewer pixels.

![Downsampling Upsampling](https://i.ibb.co/z4s4Zrm/Downsampling-Upsampling.png)

Now, the downsampled feature maps are fed into the decoder (instead of fully connected layers in a basic CNN architecture). The decoder is also a convolutional neural network that takes the features that were extracted by the encoder and attempts to produce the final output. It starts by assigning intermediate class labels to each pixel of the feature map and then upsamples the image to slowly add back the fine-grained details of the original image. This process is repeated until the image is restored to its original input dimensions with respect to the height and width. However, as mentioned before, the depth of the image in the output is equal to the number of classes. In the end, the final predicted image has the final class labels assigned to each pixel. This results in a **pixel-wise labelled map**.

#### Semantic Segmentation

Qn: Which of the following statements is true?

- Semantic segmentation is useful to categorise different instances of a given class in the image.

- Semantic segmentation uses bounding boxes to label different objects present in the image.

- Semantic segmentation can be considered as pixel-wise classification into different classes.

- None of the above.

Ans: C. *As each pixel is classified into a class, the statement is true.*

#### Encoder-Decoder

Qn: Which of the following processes are involved in the encoder-decoder framework for image segmentation?

- Feature extraction

- Mask annotation

- Image resizing

Ans:A & C. *The encoder part of the architecture is responsible for extracting the features from the image. The encoder-decoder framework alters the size of the image at each level. The encoder part is responsible for downsampling, and the decoder reverses this through upsampling.*

Qn: Which of the following statements is **not** correct?

- The encoder section of the architecture extracts different features from the image.

- The decoder section generates the pixel segmentation map at the end of the process.

- The encoder and decoder sections can be independent of each other and configured individually.

- None of the above

Ans: D. 

- The encoder part of the architecture is similar to a simple convolutional neural network that extracts different features while downsampling the image.

- The decoder section uses the features extracted by the encoder to classify each pixel at the end of the architecture.

- If there is no connection between the two sections, they can be configured as independent convolutional neural networks.

In a simple encoder-decoder framework, the encoder and the decoder are independent and different image segmentation architectures use different ways of combining and connecting these layers. One example of a simple encoder-decoder framework is **SegNet**. However, in the more recent architectures, the encoder and decoder sections are interconnected to provide better performance. One such example is **U-Net**. It was proposed in 2015 by Olaf Ronneberger, Philip Fischer and Thomas Brox in the paper - [_U-Net convolutional networks for biomedical image segmentation_](https://arxiv.org/abs/1505.04597). The architecture derives its name from the shape as it resembles the alphabet 'U'.

Let’s try to understand how this architecture differs from the simple encoder-decoder framework.

**VIDEO**

As mentioned in the video, U-Net is similar to the encoder-decoder architecture but doesn’t follow the conventional framework as **skip connections** are used to connect the encoder and decoder. The image below highlights these connections.

![Skip Connections](https://i.ibb.co/DLvpR7W/Skip-Connections.png)

The next segment will help you revisit the concept of skip connections for better clarity ahead.

## Additional Reading

-   [SegNet: A Deep Convolutional Encoder-Decoder Architecture for Image Segmentation](https://arxiv.org/abs/1511.00561)
