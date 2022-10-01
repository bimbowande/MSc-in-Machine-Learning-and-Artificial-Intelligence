# Feedforward Implementation in NumPy - III

After fulfilling all the preprocessing and initialization requirements, we will now implement the feedforward model for this problem. In the next video, we will propagate one layer forward.

**VIDEO**

You can propagate one layer forward using the code provided below.

```python
def layer_forward(H_prev, W, b, activation = 'relu'):
 
# H_prev is of shape (size of previous layer, number of examples)
# W is weights matrix of shape (size of current layer, size of the previous layer)
# b is bias vector of shape (size of the current layer, 1)
# activation is the activation to be used for forward propagation: "softmax", "relu", "sigmoid".
    
    if activation == "sigmoid":
        Z = np.dot(W, H_prev) + b 
        linear_memory = (H_prev, W, b)
        H , activation_memory = sigmoid(Z)
 
    elif activation == "softmax":
        Z = np.dot(W, H_prev) + b 
        linear_memory = (H_prev, W, b)
        H, activation_memory = softmax(Z)
    
    elif activation == "relu":
        Z = np.dot(W, H_prev) + b
        linear_memory = (H_prev, W, b)
        H, activation_memory = relu(Z)
 
# H is the output of the activation function 
# memory is a python dictionary containing "linear_memory" and "activation_memory"
        
    assert (H.shape == (W.shape[0], H_prev.shape[1]))
    memory = (linear_memory, activation_memory)
 
    return H, memory
```

As this will be a lengthy code, you cannot afford to make an error and realise it much later in the process; therefore, after each step, you will take a set of dummy variables and test each code snippet to ensure that errors are resolved on time. Take a look at the code snippet given below and verify your function.

```python
# l-1 has two neurons, l has three, m = 5
# H_prev is (l-1, m)
# W is (l, l-1)
# b is (l, 1)
# H should be (l, m)
H_prev = np.array([[1,0, 5, 10, 2], [2, 5, 3, 10, 2]])
W_sample = np.array([[10, 5], [2, 0], [1, 0]])
b_sample = np.array([10, 5, 0]).reshape((3, 1))
 
H = layer_forward(H_prev, W_sample, b_sample, activation="sigmoid")[0]
H
```

Try solving this question:

#### Number of layers

Qn: Given that you have a parameters dictionary, how will compute the number of layers of the model?

- Number of layers = len(parameters) // 2  

- Number of layers = len(parameters) 

Ans:A. *The parameter dictionary consists of weights and biases for all the layers. This means that the length of the dictionary will be double the number of layers. Hence, Number of layers = len(parameters) // 2 .*

So far you have seen the code for propagating a single layer forward using the layer_forward method. Now, you will be writing the code for forward propagation of all the layers of the neural network using the previously written function. Let us understand how to implement it in the upcoming video:

**VIDEO**

You can propagate the L layers forward using the code given below.

```python
def L_layer_forward(X, parameters):
# X is input data of shape (input size, number of examples)
# parameters is output of initialize_parameters()
 
# memories is the list of memory containing(for a relu activation, for example):
# - every memory of relu forward (there are L-1 of them, indexed from 1 to L-1), 
# - the memory of softmax forward (there is one, indexed L) 
 
    memories = []
    H = X
    L = len(parameters) // 2        # number of layers in the neural network
    
# Implement relu layer (L-1) times as the Lth layer is the softmax layer
    for l in range(1, L):
        H_prev = H 
        
        H, memory = layer_forward(H_prev, 
                                 parameters["W" + str(l)], 
                                 parameters["b" + str(l)], 
                                 activation='relu')
        memories.append(memory)
    
    # Implement the final softmax layer
    # HL here is the final prediction P as specified in the lectures
    HL, memory = layer_forward(H,
                              parameters["W" + str(L)], 
                              parameters["b" + str(L)], 
                              activation='softmax')
    memories.append(memory)
 
    assert(HL.shape == (10, X.shape[1]))
            
    return HL, memories
```

Here, let us look into the concept of memories and memory mentioned in the code snippet above.

-   'memories' is a list that stores all the values that are computed during feedforward propagation such that they can be used again during the backpropagation.  
     
-   'memory' refers to the memory of that current computation. For example, for the output layer, memory stores the values for softmax computation during feedforward propagation.  
     
-   memories.append(memory): This function adds the memory of the most recent layer to the existing memory list of the previous layers.

Note that the values of the different parameters as well as the inputs & outputs of the layers are being stored in memory so that it accessed later on for backpropagation. This might not be completely clear but as you go through the next session, you should be able to understand this better.

Don't forget to verify this function using the code given below.

```python
# X is (784, 10)
# parameters is a dictionary
# HL should be (10, 10)
x_sample = train_set_x[:, 10:20]
print(x_sample.shape)
HL = L_layer_forward(x_sample, parameters=parameters)[0]
print(HL[:, :5])
```

In this segment, you completed the feedforward implementation of the neural network model. In the next segment, you will learn about loss computation and backpropagation and implement them on the same data set using the parameters computed so far. 

  
With this, you have reached the end of this session. In the next segment, let’s summarise your learnings and the outcomes of this session.