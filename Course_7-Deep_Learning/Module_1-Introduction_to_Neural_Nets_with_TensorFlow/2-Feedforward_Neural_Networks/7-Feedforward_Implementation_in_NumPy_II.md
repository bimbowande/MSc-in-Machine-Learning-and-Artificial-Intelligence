# Feedforward Implementation in NumPy - II

So far, you have loaded and explored your data set. Next, you also wrote a one hot encoding function. Now, you will apply this function to all the three data buckets. In the next video, you will learn how you can achieve this.

**VIDEO**

#### Input features

Qn: Why do you need to transpose the image data while loading?

- The input vector should be of the shape (784, number of data points)

- The input vector should be of the shape  (number of data points, 784).

Ans: A. *If you observe the shape of training data, it is (50000,784). The input vector consists of 28*28 images which are flattened to create an input vector of 784 elements. To input into the neural network, we need the shape of the input to be (784, number of data points) = (784, 50000) for the training data.*

You can create a data_wrapper() function that applies one-hot encoding on all three buckets of data as follows.

```python
def data_wrapper():
    tr_d, va_d, te_d = load_data()
    
# Training data:
    training_inputs = np.array(tr_d[0][:]).T
    training_results = np.array(tr_d[1][:])
    train_set_y = one_hot(training_results)
    
# Validation data:
    validation_inputs = np.array(va_d[0][:]).T
    validation_results = np.array(va_d[1][:])
    validation_set_y = one_hot(validation_results)
    
# Test data:
    test_inputs = np.array(te_d[0][:]).T
    test_results = np.array(te_d[1][:])
    test_set_y = one_hot(test_results)
    
    return (training_inputs, train_set_y, test_inputs, test_set_y)

train_set_x, train_set_y, test_set_x, test_set_y = data_wrapper()
 
# Print shapes of the encoded data:
print ("train_set_x shape: " + str(train_set_x.shape))
print ("train_set_y shape: " + str(train_set_y.shape))
print ("test_set_x shape: " + str(test_set_x.shape))
print ("test_set_y shape: " + str(test_set_y.shape))
 
# Convert the encoded data to a dataframe and visualise it:
y = pd.DataFrame(train_set_y)
print("The target dataset is:" + str(training_data[1]))
print("The one hot encoding dataset is:")
y

# Visualise a certain image from the training set:
index  = 1000
k = train_set_x[:,index]
k = k.reshape((28, 28))
plt.title('Label is {label}'.format(label= training_data[1][index]))
plt.imshow(k, cmap='gray')
```

Now that you have explored and visualised the data, data preparation is complete. Next, let’s get started with the feedforward model building process. The first step is to define the activation functions that you will be using to build the model. In the next video, you will learn how to write the activation functions.

**VIDEO**

You have already learnt about the commonly used activation functions. Now, let’s start by writing the sigmoid activation function. You can recall that the sigmoid activation function is given by $\large{h^{[l]}=\dfrac{1}{1+e^{−z^{[l]}}}}$.

You can convert this formula to a NumPy code as follows.

```python
def sigmoid(Z):   
# Z is NumPy array of shape (n, m) where n is the number of neurons in the layer and m is the number of samples
    H = 1/(1+np.exp(-Z))
    sigmoid_memory = Z

# sigmoid_memory is stored as it is used later on in backpropagation 
    return H, sigmoid_memory

Z = np.arange(8).reshape(4, 2)
print ("sigmoid(Z) = \n" + str(sigmoid(Z)))
```

Similarly, the ReLu activation function is given by this equation.
$$\begin{cases}Output=x;~for~x≥0\\\\Output=0;~otherwise\end{cases}$$

You can convert this formula to the NumPy code as follows.

```python
def relu(Z):
# Z is NumPy array of shape (n, m) where n is the number of neurons in the layer and m is the number of samples 
    H = np.maximum(0, Z)
    
    assert(H.shape == Z.shape)
    
    relu_memory = Z 

# relu_memory is stored as it is used later on in backpropagation
    return H, relu_memory
 
Z = np.array([1, 3, -1, -4, -5, 7, 9, 18]).reshape(4, 2)
print ("relu(Z) = " + str(relu(Z)))
```

The softmax activation function is given by this equation $\large{p_i=\dfrac{ewi.x'}{\sum^{c−1}_{t=0}e^{w_t*x'}}}$. Where, c is the number of neurons in the output layer, $x'$ is the input to the network and $w_i$  are the weights associated with the inputs.

You can convert this formula to the NumPy code as follows.

```python
def softmax(Z):
# Z is NumPy array of shape (n, m) where n is the number of neurons in the layer and m is the number of samples 
    Z_exp = np.exp(Z)
 
    Z_sum = np.sum(Z_exp,axis = 0, keepdims = True)
    
    H = Z_exp/Z_sum  #normalising step
    softmax_memory = Z

# softmax_memory is stored as it is used later on in backpropagation
    return H, softmax_memory

#Z = np.array(np.arange(30)).reshape(10,3)
H, softmax_memory = softmax(Z)
print(H)

print(softmax_memory)
```

Now that your activation functions are in place, let's create a function, initialize_parameters(), that initialises the weights and biases of various layers. Parameters can be initialized in various ways. Now, you will learn about two of them:

-   One way to initialise is to set all the parameters to 0. This is not considered to be a good strategy, as all the neurons will behave in the same way and will defeat the purpose of deep networks. 
-   Another way to initialize the weights is by giving them random values which can be very small values but not zeros. The biases are initialized to 0. 

Note that the initialize_parameters function initializes the parameters for all the layers in one for-loop. In the last session of this module, you will learn more about different initialization techniques. 

In the next video, you will learn how to initialize the parameters.

**VIDEO**

You can initialize the model parameters using the code given below.

```python
def initialize_parameters(dimensions):
# dimensions is a list containing the number of neuron in each layer in the network
# It returns parameters which is a python dictionary containing the parameters "W1", "b1", ..., "WL", "bL":
 
    np.random.seed(2)
    parameters = {}
    L = len(dimensions)            # number of layers in the network + 1
 
    for l in range(1, L): 
        parameters['W'+str(l)]=np.random.randn(dimensions[l],dimensions[l-1])*0.1
        parameters['b' + str(l)]=np.zeros((dimensions[l], 1)) 
        
        assert(parameters['W' + str(l)].shape==(dimensions[l],dimensions[l-1]))
        assert(parameters['b' + str(l)].shape == (dimensions[l], 1))
        
    return parameters
```

The input to this function is a list named **dimensions**. 

-   The length of the list is the number of layers in the network + 1 (1 is for the input layer; the rest are hidden + output). 
-   The first element of this list is the dimensionality or the length of the input (784 for the MNIST data set). 
-   The rest of the list contains the number of neurons in the corresponding (hidden and output) layers.

For example, the dimensions = \[784, 3, 7, 10] specify a network for the MNIST data set with two hidden layers and a 10-dimensional softmax output. Here, 784 is the number of inputs = 28 x 28 as the image is of the dimension (28,28). Also, notice that the parameters are returned in a dictionary. This will help you in implementing feedforward through the layer and the backpropagation through the layer at once. We have randomly initialised to a small value as you can start the training algorithm from any point.

Next, you can print and observe the nature of different matrices using the code given below.

```python
# Declare the dimensions:
dimensions  = [784, 3, 7, 10]
 
# Run the initialize_parameters() function:
parameters = initialize_parameters(dimensions)
 
# Print the resultant weights and biases:
print("W1 = " + str(parameters["W1"]))
print("b1 = " + str(parameters["b1"]))
print("W2 = " + str(parameters["W2"]))
print("b2 = " + str(parameters["b2"]))
```

In this segment, you have successfully applied one-hot encoding on all the data, followed by writing function blocks for all the activation functions. Next, you also initialised the parameters of your model. In the upcoming segment, you will write the code for the feedforward block of this implementation.