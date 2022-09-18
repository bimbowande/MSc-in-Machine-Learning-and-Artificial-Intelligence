# Inputs and Outputs of Neural Networks

In the previous segment, you learnt that the number of neurons in the input layer is determined by the input given to the network and that the number of neurons in the output layer is equal to the number of classes (for a classification task) and equal to one (for regression tasks). Now, let’s take a look at some example use cases to understand the inputs and outputs of ANNs better.

Let’s get started by understanding the inputs and outputs of an ANN from Rohit in the upcoming video.

**VIDEO**

The most important thing to notice is that the inputs can only be numeric. For different types of input data, you use different ways to convert the inputs to a numeric form. There are three common types of inputs as mentioned below:

1.  **Text data:** For text data, you can use a **one-hot vector** or **word embeddings** corresponding to a certain word. For example, if the vocabulary size is |V|, then you can represent the word wn as a one-hot vector of size |V| with a '1' at the nth element while all other elements being zero. The one-hot encoded array of the digits zero to nine will look like the image shown below:   
    
    ![One Hot Encoded Array](https://i.ibb.co/7NdVkxz/One-Hot-Encoded-Array.png)
    
      
    The problem with one-hot representation is that, usually, the vocabulary size |V| is huge, in tens of thousands at least; hence, it is often better to use word embeddings that are a lower-dimensional representation of each word.  
    
2.  **Images:** Images are naturally represented as arrays of numbers and can thus be fed to the network directly. These numbers are the **raw pixels of the image**. ‘Pixel’ is short for picture element. In images, pixels are arranged in rows and columns (an array of pixel elements). The figure given below shows an image of a handwritten 'zero' in the MNIST dataset (black and white) and its corresponding representation in NumPy as an array of numbers. The pixel values are high where the intensity is high, i.e., the colour is bright, while the values are low in the black regions as shown below:  
    
    ![Raw Pixels of ZERO](https://i.ibb.co/Q9PXT2F/Raw-Pixels-of-ZERO.png)
    
      
      
    In a neural network, each **pixel** of the input image is a **feature**. For example, the image provided above is an 18 x 18 array. Hence, it will be fed as a **vector of size 324** to the network.  
      
    Note that the image given above is **black and white** (also called grayscale image), and thus, each pixel has only one ‘**channel**’. If it were a **coloured image** (called an RGB image - Red, Green, Blue), each pixel would have **three channels** - one each for red, blue and green as shown below. Hence, the number of neurons in the input layer would be 18 x 18 x 3 = 972. The three channels of a RGB image are shown below:
    
![RGB](https://i.ibb.co/4Jhs64r/RGB.png)

3.  **Speech:** In the case of speech/voice input, the basic input unit is in the form of **phonemes.** These are the distinct units of speech in any particular language. The speech signal is in the form of waves, and to convert these waves into numeric inputs, you can use Fourier transforms. Take a look at the formula of the discrete Fourier transform given below.  
    $$\large{x[k]=\sum^{N−1}_{n=0}x[n]e−j2πknN}$$
Now that you are well equipped with the knowledge of inputs in a neural network, try answering the following questions:

#### Inputs

Qn: Fill in the blank. "In a classification problem with 12 attributes and 3 class labels, the number of neurons in the input and output layers will be \_\_\_\_\_".

- 12, 2

- 12, 3

- 2, 12

- 1,12

Ans: B. *The input layer has 12 neurons corresponding to 12 attributes, and the output layer has 3 neurons corresponding to the probability of class labels 1, 2 and 3.*

Qn: Fill in the blank. "Neural networks are quite popular in image recognition problems. The task is to classify a given grayscale image (say, a Google image) into categories such as nature, animal and sports. An image is simply a collection of pixels. 

Let us take the example of a 720 x 1080 image. There are 720 pixels along the vertical of the image and 1080 pixels along the horizontal. Each pixel acts as an attribute and contains a ‘value’ that may represent the colour, shade, etc., at that point on the image.

To classify an image into the three categories mentioned above, the number of neurons in the input and output layers are \_\_\_\_\_ and \_\_\_\_\_, respectively.  

- 720, 1080 

- 720 X 1080, 1 

- 720 X 1080, 3 

- 1080, 720

Ans: C. *The 720 x 1080 pixels each act as an attribute. The three output neurons contain the probability of an image being from nature, animal or sports category.*

Qn: What would be the number of neurons in the input layer if the above 720 x 1080 image was coloured (RGB channels) instead of grayscale?

- 720 x 1080 

- 720 x 1080 x3

Ans: B. *As RGB has three channels, it is 720 x 1080 x3.*

Now that you have looked at how to feed input vectors to neural networks, let’s understand how the output layers are specified.

Depending on the nature of the task, the outputs of neural networks can either be in the form of classes (if it is a classification problem) or numeric (if it is a regression problem). One of the commonly used output functions is the softmax function. Take a look at the graphical representation of the softmax function shown below.

![Graphical Softmax](https://i.ibb.co/xhDk0zs/Graphical-Softmax.png)

A softmax output is a multiclass logistic function commonly used to compute the probability of an input belonging to one of the multiple classes. It is given by the following formula: 
$$\large{p_i=\dfrac{e^{w_i*x'}}{\sum^{c−1}_{t=0}e^{w_t*x'}}}$$
Where, c is the number of neurons in the output layer, x’ is the input to the network and wi’s are the weights associated with the inputs.

Let us consider the case where the output layer has three neurons and all of them have the same input x′ (coming from the previous layers in the network). The weights associated with them are represented as w0, w1 and w2. In such a case the probability of the input belonging to class 0 is:
$$\large{p_0=\dfrac{e^{w_0*x'}}{e^{w_0*x'}+e^{w_1*x'}+e^{w_2*x'}}}$$
Now, try answering the following questions.

#### Softmax Output

In the equation given above, what will be the expression for p1?

- $\dfrac{e^{w_0*x'}}{e^{w_0*x'}+e^{w_1*x'}+e^{w_2*x'}}$

- $\dfrac{e^{w_1*x'}}{e^{w_0*x'}+e^{w_1*x'}+e^{w_2*x'}}$

- $\dfrac{e^{w_2*x'}}{e^{w_0*x'}+e^{w_1*x'}+e^{w_2*x'}}$

Ans: B. *Given $i=1$ and $c=3$. Therefore . you get $\dfrac{e^{w_1*x'}}{e^{w_0*x'}+e^{w_1*x'}+e^{w_2*x'}}$*

Also, it is evident from the above expression that the sum $p_0+p_1+p_2=1$ and that $p_0, p_1, p_2 \in (0, 1)$. 

#### Range of Softmax

Qn: In the softmax output layer given above, if $p_0=0.5$, then what is the range of $p_1$?

- 0 to 1

- 0 to 0.5

- 0 to 0.25

- 0.5 to 1

Ans: B. *Maximum value that p1 can have is $1-0.5=0.5$. Minimum value is 0 when $p_2=0.5$*

The softmax function stated above is a general case for multiclass classification. It is a commonly used output layer activation function. Many such activation functions are applied to the output and hidden layers, which you will learn in the next segment.