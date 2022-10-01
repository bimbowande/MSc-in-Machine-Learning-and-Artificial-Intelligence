# CIFAR-10 Classification With TensorFlow - IV

In this segment, you will learn how to build a simple CNN architecture for classification over the CIFAR-10 data set.

Let’s start by first defining the model in the upcoming video.

**VIDEO**

The following CNN architecture will be used in the demonstration for classifying the images.

![CIFAR CNN Architecture](https://i.ibb.co/281sT32/CIFAR-CNN-Architecture.jpg)

The architecture has two convolution blocks, followed by a fully connected layer and a Softmax layer for classification. The following elements are defined along the process:

-   Convolution layer (layers.Conv2D):
    -   Number of filters (32 in the first block and 64 in the second block)
    -   Shape of the filter (3\*3 = 9 weights per filter)
    -   Stride (Default: 1)
    -   Padding type (Same padding: Input and output size remains the same)
    -   Activation function (ReLU)
    -   Input shape (32\*32\*3; only for the first layer of the architecture)


```python
# General Syntax
# tf.keras.layers.Conv2D(filters, kernel_size, strides=(1, 1), padding='valid', activation=None)
```

- Pooling layer
    - Patch size for pooling (2\*2)
    - Stride ((Default: 1)
    - Padding

```python
# General Syntax
# tf.keras.layers.MaxPool2D(pool_size=(2, 2), strides=None, padding='valid')
```

Given below is the summary of the convolution blocks in the model used for the demonstration.

![CIFAR10 CNN Model Summary](https://i.ibb.co/T1Tmp0j/CIFAR10-CNN-Model-Summary.png)

As you can see, the input layer results in a 32\*32\*32 output. This means that there will be 32 different feature maps at the end of the first layer. As each filter is of size 3\*3\*3 (height*width*channel), the number of parameters for this layer could be calculated as follows:

- Weights
    - 32 filters
    - 27 (3\*3\*3) weights per filter
    - Total parameters due to weights = 32\*27 = 864 parameters
- Bias
    - 32 filters
    - 1 bias per filter
    - Total parameters due to bias = 32\*1 = 32 parameters
- Total parameters = Weights + Biases
    - 864 + 32 = 896 parameters (as specified in the image above)

You can now use the same process to verify the number of parameters in the second layer of the architecture.

Moving forward, you can see that the two convolutional layers are followed by a pooling layer that reduces the size of the layer to half. The entire process is repeated to complete the feature extraction part of the architecture.

Now, you will learn how to add the dense layers on top of this in the upcoming video.

**VIDEO**

As mentioned in the video, the dense layer will take the 3D tensor from the pooling layer and convert it into a flat 1D array. After the first dense layer, the second dense layer is a Softmax layer used for the purpose of classification. As there are ten different classes, the size of this layer is kept as ten. Note that the number of architecture parameters explodes due to these dense layers, as the neurons in these layers are connected with one another.

This completes our network. You are now ready to fit and train the model in the next segment.