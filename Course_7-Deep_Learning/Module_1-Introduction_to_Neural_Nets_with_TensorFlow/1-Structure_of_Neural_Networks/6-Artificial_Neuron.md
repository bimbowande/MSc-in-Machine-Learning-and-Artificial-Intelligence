# Artificial Neuron

With an understanding of perceptrons, you are now equipped to study the design of Artificial Neural Networks (ANNs). 

Neural networks are a collection of artificial neurons arranged in a particular structure. In this segment, you will understand how an artificial neuron works, i.e., how it converts inputs into outputs. You will also understand the topology or the structure of large neural networks. Let’s get started by understanding the basic structure of an artificial neuron in the upcoming video.

**VIDEO**

In the video above, you understood that a neuron is very similar to a perceptron. However, in perceptrons, the commonly used activation/output function is linear, i.e., the step function or the sign function, whereas, in the case of ANNs, the activation functions are non-linear.

Note: You will learn about these activation functions in detail in the upcoming segments.

Take a look at the structure of an artificial neuron in the image given below.

![Structure of Artificial Neuron](https://i.ibb.co/WBb33F1/Structure-of-Artificial-Neuron.png)

Where, ‘a’ represents the inputs, ‘w’ represents the weights associated with the inputs and ‘b’ represents the bias of the neuron.

In the next video, you will understand how large neural networks are designed using multiple individual neurons.

**VIDEO**

Multiple artificial neurons in a neural network are arranged in different layers. The first layer is known as the input layer, and the last layer is called the output layer. The layers in between these two are the hidden layers. The number of neurons in the input layer is equal to the number of attributes in the dataset, and those in the output layer are equal to several classes of the target variable (for a classification problem). For a regression problem, the number of neurons in the output layer would be 1 (a numeric variable). Take a look at the image given below to understand the topology of neural networks in the case of classification and regression problems.

![Neural Networks for Classification vs Regression](https://i.ibb.co/DtShBqc/Neural-Networks-Classification-Regression.png)

So far, you have understood the basic structure of neural networks. To summarise, there are six main things that must be specified for any neural network, which are as follows:

1.  Input layer
    
2.  Output layer
    
3.  Hidden layers
    
4.  Network topology (determines the nature of connections between the layers of the model)
    
5.  Weights and biases
    
6.  Activation functions
    

You might have some questions such as ‘How to decide the number of neurons in a layer?’ and ‘How are weights and biases specified?’. You will be able to answer these questions in the next few segments where you will be learning about each of these specifications in detail.