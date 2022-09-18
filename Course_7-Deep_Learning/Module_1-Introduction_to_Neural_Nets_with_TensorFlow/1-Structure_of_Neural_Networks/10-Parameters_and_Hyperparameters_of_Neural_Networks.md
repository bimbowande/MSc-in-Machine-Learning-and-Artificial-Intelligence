# Parameters and Hyperparameters of Neural Networks

Neural networks require rigorous training. But, what does it mean to train neural networks? What are the parameters that the network learns during training, and what are the hyperparameters that you (as the network is designed) need to specify beforehand?

Recall that models such as linear regression and logistic regression are trained on their coefficients, i.e., the task is to find the optimal values of the coefficients to minimise some cost function.

Neural networks are no different - they are trained on **weights and biases**.

In this segment, you will understand the parameters that are learnt during neural network training. You will also get a broad understanding of how the learning algorithm is trained. Let us get started by taking a look at the upcoming video:

**VIDEO**

During training, the neural network learning algorithm fits various models to the training data and selects the best prediction model. The learning algorithm is trained with a fixed set of **hyperparameters** associated with network structure:

-   Number of layers
    
-   Number of neurons in the input, hidden and output layers
    
-   Learning rate
    
-   Number of epochs, etc.
    

The purpose of training is to obtain optimum weights and the biases, which form the **parameters** of the network.

Note: You will learn about hyperparameters such as learning rate and number of epochs in the upcoming session. In this session, the focus will be on the number of layers and number neurons in each layer.

Now, let's take a closer look at the parameters and hyperparameters. You will also fix some notations that you will use throughout the upcoming lectures. The notations that you will be going forward with are as follows:

1.  _W_ is for weight matrix
    
2.  _b_ stands for the bias
    
3.  _x_ stands for input
    
4.  _y_ is the ground truth label
    
5.  _p_ is the probability vector of the predicted output
    
6.  _h_ is the output of the hidden layers
    
7.  The superscript stands for layer number. The weight matrix connecting the first layer to the second layer will be denoted as w[1].
    
8.  The subscript stands for the index of the individual neuron. The weight connecting the first neuron of the first layer to the third neuron of the second layer will be denoted as w[1]13.
    

Having understood this, let’s reinforce these notations by answering the following questions.

![Neural Networks Parameters Qn](https://i.ibb.co/Rz1wmhB/Neural-Networks-Parameters-Qn.png)

You might want to look at how the inputs of the first data point x1 are represented. Also, note that the input layer is not represented as a layer at many places. It might be shown as a set of inputs that go into the first hidden layer. Keep this in mind while exploring different blogs and articles. 

 This will help you in answering the following questions.

#### Notations

Qn: How will you represent the element of the weight matrix between layers 1 and 2 represented as x in the figure (do not confuse this with the bias)?

- $w^2_{25}$

- $w^1_{25}$

- $w^1_{52}$

- $w^2_{52}$

Ans: D. *The elements are of the matrix $w^2$.  The fifth neuron of the first layer is connected with the second neuron of the second layer. Hence, $w^2_{52}$*

Qn: On similar lines, how will you represent the element of the weight matrix represented as z?

- $w^3_{33}$

- $w^4_{33}$

Ans: B. *The elements are of the matrix $w^4$. The third neuron of the third layer is connected with the third neuron of the fourth layer. Hence, $w^4_{33}$.*

Qn: How will you represent the bias of the neuron denoted by u?

- $b^3_2$

- $b^2$

Ans: A. *It is the bias of the third layer for the second neuron. Hence, $b^3_2$*

Qn: How will you represent the output of the neuron denoted by y?

- $h^2_5$

- $b^2_5$

Ans: A. *It is the bias of the second layer for the fifth neuron. Hence, $h^2_5$.*

Now that you have a good understanding of deep learning, let’s quickly take a look at when you should use deep learning. Let’s watch the next video.

**VIDEO**

Let’s quickly revisit the following points that you learnt in this video:

1.  Firstly, if you have very large datasets, the performance of deep learning models will be better than that of preliminary machine learning models. Therefore, it is preferable to use deep learning.  
     
    
2.  For cases where the problems are too complex for machine learning algorithms, one can use deep learning to solve them. Deep learning algorithms can efficiently perform complex feature engineering tasks. For example, in the case of self-driving cars and image recognition.  
     
    
3.  Deep learning requires a large number of computational resources and expenses to drive hardware and software for training. If you have the availability of these resources, you should go ahead and train your models using deep learning algorithms.  
     
    
4.  In the case of deep learning algorithms, accuracy is the priority. So, if small performance gains are also extremely critical for your model, you should consider using deep learning algorithms.  
     
    

This brings us to the end of this session. Let’s move on to the next segment where you will quickly walk through the different elements that you learnt throughout this session.