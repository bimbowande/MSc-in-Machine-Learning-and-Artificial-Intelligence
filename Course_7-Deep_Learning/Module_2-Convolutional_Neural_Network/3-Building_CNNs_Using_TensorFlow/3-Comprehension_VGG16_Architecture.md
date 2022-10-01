# Comprehension - VGG16 Architecture

In this exercise, we will dissect each layer of the VGG-16 architecture. This exercise will help you apply all the concepts learnt so far.

The VGG-16 was trained on the ImageNet challenge (ILSVRC) **1000-class classification** task. The network takes a (224, 224, 3) RBG image as the input. The '16' in its name comes from the fact that the network has 16 layers with trainable weights, **13 convolutional layers** and **3 fully connected** ones (the VGG team had tried many other configurations, such as the VGG-19, which is also quite popular).

The architecture is given in the table provided below (taken [from the original paper](https://arxiv.org/pdf/1409.1556.pdf)). Each column in the table (from A-E) denotes an architecture that the team had experimented with. In this discussion, we will refer to only **column D**, which refers to **VGG-16** (column E is VGG-19).

#### VGG-16
![VGG-16](https://i.ibb.co/C7H53S5/VGGNet-Architecture-Configuration.png)

The convolutional layers are denoted in the table as conv\<size of filter>-\<number of filters>. Thus, conv3-64 means 64 (3, 3) square filters. Note that all the conv layers in VGG-16 use (3, 3) filters and the number of filters increases in powers of two (64, 128, 256, 512). 

In all the convolutional layers, the same **stride length of 1 pixel** is used with a **padding of 1 pixel** on each side, thereby preserving the spatial dimensions (height and width) of the output.

After every set of convolutional layers, there is a **max pooling** layer. All the pooling layers in the network use a **window of 2 x 2 pixels with stride 2**. Finally, the output of the last pooling layer is **flattened** and fed to a **fully connected (FC)** layer with 4,096 neurons, followed by another FC layer of 4,096 neurons, and finally to a 1000-softmax output. The softmax layer uses the usual cross-entropy loss. All layers apart from the softmax use the ReLU activation function.

The number of parameters and the output size from any layer can be calculated as demonstrated in the MNIST Notebook on the previous page. For example, the first convolutional layer takes a (224, 224, 3) image as the input and has 64 filters of size (3, 3, 3). Note that the **depth of a filter** is always **equal to the number of channels** in the input that it convolves. Thus, the first convolutional layer has 64 x 3 x 3 x 3 (weights) + 64 (biases) = 1,792 trainable parameters. Since stride and padding of 1 pixel are used, the output spatial size is preserved, and the output will be (224, 224, 64).

Now answer the following questions (you will need a calculator). Keep track of the number of channels at each layer. Do not forget to add the biases.

#### Conv Layer-2

Qn: The output of the first convolutional layer is (224, 224, 64), i.e. 64 feature maps of size (224, 224). The second conv layer uses 64 filters of size (3, 3, 64). Note that the number of channels in the filters (64) is implicit since the filters have to convolve a tensor of 64 channels. The number of parameters in the second conv layer are: 

- 36864

- 36928

- 1792

Ans: B. *The 64 (3, 3, 64) filters have 64\*3\*3\*64 (weights) + 64 (biases).*

#### Conv Layer-2 Output

Qn: The output of the first convolutional layer is (224, 224, 64) which is fed to the second conv layer with 64 filters of size (3, 3, 64).  The output of the second conv layer is:

- (224, 224)

- (224, 224, 64)

- (224, 224, 128)

Ans: B. *64 filters will produce 64 feature maps. The size of each map will be preserved to (224, 224) since stride and padding of 1 are used.*

#### The Pooling Layer

Qn: The output of the second conv layer, (224, 224, 64), is fed to a max pooling layer. All the pooling layers in the network use a window size of 2 x 2 with stride 2. The output of the pooling layer is:

- (112, 112, 64)

- (112, 112

Ans: A. *The pooling layer simply reduces the spatial size to half and preserves the number of channels.*

#### Conv Layer-3

Qn: The output from the first pooling layer, (112, 112, 64), is fed to the third conv layer. The number of trainable parameters in the third conv layer is:

- 73728

- 73792

- 73856

Ans: C. *Each filter is of size (3, 3, 64). Thus 128 filters have 128*3*3*64 (weights) +128 (biases).*

#### Conv Layer-3 Output

Qn: The output from the first pooling layer, (112, 112, 64), is fed to the third conv layer. The output of the third convolutional layer is:

- (112, 112, 128)

- (112, 112)

- (56, 56, 128)

Ans: A. *Since all the convolutions are with stride 1 and padding 1, the size (height x width) is maintained. The third layer has 128 filters each of which will produce a 112 x 112 feature map.*

#### The First FC Layer

Qn: Let's now come to the latter part of the network. The output from the last (13th) convolutional layer is of size (14, 14, 512) which is fed to a max pooling layer to give a (7, 7, 512) output. The output from the max pooling layer is then fed to a fully connected layer (FC) with 4096 neurons (after flattening).  The number of trainable parameters in this FC layer is:

- 102760448

- 102764544

Ans: B. *The output of the pooling layer, after flattening, will be a vector of length 7\*7\*512. Thus, the FC layer will have 7\*7\*512\*4096 (weights) + 4096 (biases).*

#### Shrinkage in VGG-16

Qn: In the VGG-16 network, the size of the output is shrunk (i.e. the height x width of the input):

- By only the convolutional layers

- By only the pooling layers

- By both convolutional and pooling layers

Ans: B. *Since all the conv layers use a stride and padding of 1 with a (3, 3) filter, the spatial size is preserved in all the convolutional layers (only the depth increases). The height and width is reduced only by the pooling layers.*

The total number of trainable parameters in the VGG-16 is about **138 million** (138,357,544 exactly), which is enormous. In an upcoming session, you will learn how some of the recent architectures (such as ResNet) have achieved much better performance with far fewer parameters.

In the next few segments, you will learn how to build a CNN model and experiment with various hyperparameters using the CIFAR-10 dataset.