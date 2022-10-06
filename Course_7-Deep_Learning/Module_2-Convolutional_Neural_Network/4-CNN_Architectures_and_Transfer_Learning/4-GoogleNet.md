# GoogleNet

After VGGNet, the next big innovation was GoogleNet, which had won the ILSVRC’14 challenge with an error rate of about 6.7%.

Unlike the previous innovations, which had tried to increase the model capacity by adding more layers, reducing the filter size, etc. (such as from AlexNet to VGGNet), GoogleNet had increased the depth using a new type of convolution technique using the **Inception module**.

The module derives its name from a previous paper by Lin et al. and this popular meme in the deep learning community.   

![We need to deeper](https://i.ibb.co/4SNg2Nv/We-need-to-deeper.jpg)

Let's study the key features of the GoogleNet architecture.

**VIDEO**

The image given below summarises the GoogleNet framework.

![GoogleNet Framework](https://i.ibb.co/WVZMp0k/Google-Net-Framework.jpg)

To summarise, some important features of the GoogleNet architecture are as follows:

-   There are a total of 22 layers in the architecture, stacked on top of each other.
-   The architecture introduced two new concepts:
    -   **Auxiliary classifier**: Helps in improving the performance by evaluating the output at intermediate levels
    -   **Inception module**: Parallel convolutions by multiple filters (1x1, 3x3, 5x5) to extract features at different levels, accompanied by a pooling operation of size (3x3)
-   The architecture has no FC layers, except for the last Softmax layer for classification. This helps in keeping the trainable parameters in check, as the number of parameters has reduced from 60 million (AlexNet) to 4 million.

The details on why the GoogleNet and the inception module work well are beyond the scope of this course; however, you are encouraged to read the [GoogleNet paper](https://arxiv.org/pdf/1409.4842.pdf). 

In the next segment, you will look at another CNN architecture, that is, residual network.

## Additional reading

1.  Please go through the paper on GoogleNet: [The GoogleNet, Christian Szegedy et al](https://arxiv.org/pdf/1409.4842.pdf).