# Graded Questions

The following questions are graded.

## **Comprehension - A Three-Class Classification CNN**

Let's consider a CNN-based architecture designed to classify an image into one of the three classes: a pedestrian, a tree or a traffic signal. Each input image is of size (512, 512, 3) (RGB).

The network contains the following 11 layers in order. Note that we will address the input layer as the first layer, the next convolution layer as the second layer, and so on (i.e., according to the numbers).

1. Input image (512,512,3)

2. Convolution: 32  5x5 filters, stride **'s1'**, padding **'p1'**

3. Convolution: 32  3x3 filters, stride 1, padding 1

4, Max Pooling: 2x2 filter, stride 2

5. Convolution: 64  3x3 filters, stride 1, padding 1

6. Convolution: 64  3x3 filters, stride 1, padding 1

7. Max Pooling: 2x2 filter, stride 2

8. Layer **'l'**

9. Fully-connected: 4096 neurons

10. Fully-connected: 512 neurons

11. Fully-connected: **'F'** neurons

#### Comprehension

Qn: If the spatial dimensions (width and height) of the output going into the third layer are the same as the input from the previous layer, what can be the possible values of stride 's1' and padding 'p1'?

- stride 1, padding 1

- stride 2, padding 2

- stride 1, padding 2

- stride 2, padding 1

Ans: C. *Calculate the output using ((n+2p-k)/s +1). With s=1, p=2, the output is (512 + 4 - 5)/1 + 1 = 512.*

Qn: The 8th layer is named layer 'l'. Which of the following types could be the layer 'l'?

- Convolution

- Pooling

- Flatten

- Fully connected

Ans: C. *The 'Flatten' layer connects the convolutional layer to the fully connected layer by flattening the multidimensional tensor output from the conv layer to a long vector.*

Qn: What is the output from the last max pooling layer (layer 7) assuming that the width and the height do not change after the convolution operation in step-2?

- 256x256x32

- 128x128x64

Ans: B. *After two pooling operations (starting from the starting 512 x 512), the width and the height will reduce 2 times, i.e. from 512 to 256 (in the first max pooling layer) and from 256 to 128 (in the second max pooling layer).*

Qn: What is the value of 'F' in the last layer?

- 1000

- 3

Ans: B. *Since we are classifying an image into 3 classes, it has to have 3 neurons.*

Qn: Calculate the total number of trainable parameters in layer-3 (the conv layer with 32 3x3 filters)?

- 9248

- 10,272

- 9216

- 320

Ans: A. *The output from the previous layer is (512, 512, 32), so each filter is of size (3, 3, 32). The number of parameters is thus 32 filters *3*3*32 (weights) + 32 (biases) = 9248.*
