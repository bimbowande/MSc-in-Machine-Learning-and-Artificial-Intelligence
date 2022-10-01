# Assumptions for Simplifying Neural Networks

Since large neural networks can potentially have extremely complex structures, certain assumptions are made to simplify the way in which information flows in them. In the next video, Rohit will explain some of the most common assumptions.

**VIDEO**

The image below shows the assumptions you learnt in the video above:

![Assumptions for Neural Networks](https://i.ibb.co/PcfGkYs/Assumptions-for-Neural-Networks.png)

To summarise, commonly used neural network architectures make the following simplifying assumptions:

1.  The neurons in an ANN are **arranged in layers**, and these layers are arranged **sequentially.**
    
2.  The neurons within the same layer **do not interact** with each other.
    
3.  The inputs are fed to the network through the **input layer**, and the outputs are sent out from the **output layer**.
    
4.  Neurons in **consecutive layers** are **densely connected**, i.e., all neurons in layer l are connected to all neurons in layer l+1.
    
5.  Every neuron in the neural network has a **bias** associated with it, and each interconnection has a **weight** associated with it.
    
6.  All neurons in all layers use the **same activation function**.
    

Having specified the basic assumptions in the architecture of ANNs, let's now understand how neural networks are trained and used to make predictions. In the next segment, you will learn about the hyperparameters and parameters of neural networks.