# Skip Connections

The previous segment helped you with the understanding of the encoder-decoder architecture used to implement the image segmentation algorithm. It also introduced you to the U-Net framework which differs from the basic structure as it uses skip connections. 

Let's try to revisit the concept before moving deeper into the U-net architecture in the next video.

**VIDEO**

As the name suggests, skip connections help in establishing the connection by skipping the adjacent layers. 

![Skip Connection Basic Model](https://i.ibb.co/vvHXf7f/Skip-Connection-Basic-Model.png)

Skip connections were first introduced in the ResNet framework to overcome the problem of vanishing gradient. To describe in simple terms, as the network becomes deeper, the initial layers tend to lose their importance in the process of backpropagation. Hence, skip connections helped in overcoming this problem by offering an alternate path for the architecture to optimise the loss function.

![Loss Surfaces of ResNet56 without (left) and with (right) Skip Connections](https://i.ibb.co/yfh3qVV/Loss-Surfaces-of-Res-Net56-Without-left-and-with-right-Skip-Connections.png)

The loss surfaces of ResNet56 without (left) and with (right) skip connections.  
_Source: [Visualizing the Loss Landscape of Neural Nets](https://arxiv.org/abs/1712.09913)_

#### Skip connections

Qn: Which of the following statements is true for skip connections?

- Skip connections make the network more complex for the architecture to learn more from the image.

- Skip connection combines the learning from all the connections together in the single branch.

- Skip connections help in the simplification of the architecture by skipping the redundant connections during the training process.

Ans: C. *This is the true objective of skip connections.*

Now, you must have a clear understanding of the purpose of the skip connections in a deep network. However, in the case of U-Net, its application is not limited to optimising the architecture in terms of the loss function. The coming segments will discuss the U-Net architecture in detail and help in unfolding the other purpose of using the skip connections.