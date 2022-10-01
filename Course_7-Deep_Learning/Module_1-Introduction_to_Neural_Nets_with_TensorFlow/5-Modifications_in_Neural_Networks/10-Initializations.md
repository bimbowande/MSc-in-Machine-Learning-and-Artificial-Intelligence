# Initializations

**Initializations** is one of the first steps in training a neural network. The starting point in neural networks is not as important as in other algorithms like the genetic algorithm. It is true that different starting points will help you in reaching the global minimum but at the same time, it becomes computationally intensive to train a lot of neural networks. Even more, with the different optimizers available, it is highly likely that you'll be able to reach the global minimum or a good local minimum.

In this segment, you will be introduced to the different ways we can initialize a neural network. Let us get started with the upcoming video.

**VIDEO**

As you saw in the above video, initializations are done such that there is symmetry breaking which was also the reason for dropouts and other techniques. There are different ways to initialize the parameters, let us look at the three common techniques:

1.  **Zero Initializations:** In this method, you initialize the parameters(weights and biases) to zero. This can be done as follows:
    
```python
# n[l] = layer_size[l], n[l-1] = layer_size[l-1]
w = np.zeros(n[l], n[l-1])*0.01
b = np.zeros(n[l], 1)*0.01
```

To understand this method, take a look at the points below:
    1. This technique is not useful while initializing weights as it makes all the weights zero and the derivatives of these weights will be the same for each iteration. This forms a symmetry pattern in the network and the model does not learn from the data.  
    2. However, you can use this to initialize biases as you have seen in the MNIST implementation in the previous sessions. Initializing biases to zero does not create a symmetry in the model.  

2.  **Random Initializations:** One of the commonly used techniques for initializing the parameters is random initialization. While doing performing this technique, remember, the initialization should not be so small that the weights quickly fall down to zero and the learning stops. Hence, the initializations are done from a Gaussian distribution as shown below:
    
```python
w=np.random.randn(n[l],n[l-1])*0.01
b=np.random.randn(n[l],1)*0.01
```
This technique helps in symmetry breaking but might give rise to the problem of vanishing and exploding gradients if the parameters are too small or large respectively.  
     
    
3.  **He-et-al Initialization:** This technique initializes the weights with respect to the previous layer's size. This can be done the following:
    
```python
w=np.random.randn(n[l],n[l-1])*np.sqrt(2/layer_size[l-1])
w=np.random.randn(n[l],n[l-1])*np.sqrt(2/n[l-1])
w=np.random.randn(n[l],n[l-1])*(np.sqrt(6/(n[l-1]))+(np.sqrt(6/n[l])))
```

This brings you to the end of the session. Let us summarise the learnings of this session in the next segment.