# Two Architectures: 3D Convs and CNN-RNN Stack

After understanding and acquiring the dataset, the next step is to try out different architectures to solve this problem. 

For analysing videos using neural networks, **two types of architectures** are used commonly. One is the standard **CNN + RNN architecture** in which you pass the images of a video through a CNN which extracts a feature vector for each image, and then pass the sequence of these feature vectors through an RNN. This is something you are already familiar with (in theory).

The other popular architecture used to process videos is a natural extension of CNNs - a **3D convolutional network**. In this project, you will try both these architectures.

To understand further let's look at their architecture to understand how do they work. 

## Convolutions + RNN

The video can be imagined as a sequence of frames that is fed through a CNN network to extract features from each of the frames. The number of feature vectors from the CNN model is analogous to the number of frames present in the sequence. The resulting sequence of feature vectors is then passed to an RNN-based network. The final hidden representations from the RNN model is passed to a softmax layer for the gesture classification

![CNN-RNN architecture](https://i.ibb.co/XYZBwpD/CNN-RNN-Architecture.png)

Note: For a sequential based problem RNN is the natural choice however in comparison to a CNN model which has the parameter sharing property, RNN based model has more parameters.

## 3D Convolutional Network, or Conv3D

3D convolutions are a natural extension to the 2D convolutions you are already familiar with. Just like in 2D conv, you move the filter in two directions (x and y i.e length and width of the image respectively), in 3D conv, you move the filter in three directions (x, y and z) where z is the channel of the image.

![Conv3D](https://i.ibb.co/D9qmdD5/Conv3D.png)

For example, the input to a 3D Conv is a video (which is a sequence of 30 RGB images). If we assume that the shape of each image is **100x100x3**, the video becomes a **4-D tensor of shape** **100x100x3x30** which can be written as **(100x100x30)x3** where 3 is the number of channels. Hence, deriving the analogy from 2-D convolutions where a 2-D kernel/filter (a square filter) is represented as (fxf)xc where f is filter size and c is the number of channels, a 3-D kernel/filter (a 'cubic' filter) is represented as (fxfxf)xc (here c = 3 since the input images have three channels). This cubic filter will now '3D-convolve' on each of the three channels of the (100x100x30) tensor.

![3DCNN](https://i.ibb.co/CtcvdKc/3DCNN.png)

Since the filter slides through a 3D space, the output numbers from the 3D CNN are arranged in a 3D space as well. The output feature vector is then a 3D data.

![Oputput Feature Vector 3D](https://i.ibb.co/hDYhnbH/Oputput-Feature-Vector-3-D.png)

The 3D filter moves across the input data in all 3-directions (height, width, channel of the image) to calculate the low level feature representations.

As an example, let's calculate the output shape and the number of parameters in a Conv3D with an example of a video having 7 frames. Each image is an RGB image of dimension 100x100x3. Here, the number of channels is 3.

The input (video) is then 7 images stacked on top of each other, so the shape of the input is (100x100x7)x3, i.e (length x width x number of images) x number of channels. Now, let's use a 3-D filter of size 2x2x2. This is represented as (2x2x2)x3 since the filter has the same number of channels as the input (exactly like in 2D convs).

Now let's perform a 3D convolution using a (2x2x2) filter on a (100x100x7) matrix (without any padding and stride = 1). You know that the **output size after convolution** is given by: 

$$new\_dimension=\dfrac{old\_dimension−filter\_size+2∗padding}{stride}+1$$

In 3D convolutions, the filter convolves in three directions (exactly like it does in two dimensions in 2D convs), so you can extend this formula to the third dimension as well. You get the output shape as:

$$\left(\dfrac{100−2}{1}+1,\dfrac{100−2}{1}+1,\dfrac{7−2}{1}+1\right) = (99,99,6)$$

Thus, the output shape after performing a 3D conv with one filter is (99x99x6). Now, if we do (say) 24 such 3D convolutions, the output shape will become (99x99x6)x24. Hence, the new number of channels for the next Conv3D layer becomes 24. This is very similar to what happens in conv2D.

Now let's calculate **the number of trainable parameters** if the input shape is (100x100x7)x3 and it is convolved with 24 3D filters of size (2x2x2) each, expressed as (2x2x2)x3 to give an output of shape (99x99x6)x24. Each filter will have 2x2x2 = 8 trainable parameters for **each** **of the 3 channels**. Also, here we consider that there is **one** **bias per filter**. Hence, each filter has 8x3 + 1  = 25 trainable parameters. For 24 such filters, we get 25x24 = 600 trainable parameters.

Please **note** here that the order in which the dimensions are specified is different in the starter code provided to you which can be figured out by looking at the custom generator code (you will study that on the next page).

Now that you have understood 3D convolutions, Snehansu will walk you through some basic concepts (most of which you already know) of the second type of architecture you will try: conv2D + RNNs.

**VIDEO**

There are a few key things to note about the conv-RNN architecture:

1.  You can use **transfer learning** in the 2D CNN layer rather than training your own CNN 
2.  GRU can be a better choice than an LSTM since it has lesser number of gates (and thus parameters)

In the next segment, you'll learn how to set up the **data ingestion pipeline**.