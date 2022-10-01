# Backpropagation Implementation in NumPy - II

In this segment, you will write the code for the backpropagation of L layers. Let’s watch the next video to understand the code.

**VIDEO**

So far, you have computed the gradients for the last layer. Let us see how to write the gradients for the remaining layers in the upcoming video.

**VIDEO**

#### Backpropagation

Qn: Which of the following will be the inputs to the 'update_parameters()' function?

- parameters

- gradients

- memories

- learning rate

Ans: A, B & D. *The  update_parameters() function takes parameters, gradients and learning rate as input parameters to the function.*

You can implement the code for L_layer_backward on your own as follows. Note that you are using the equations of the last layer are a bit different and you are using some from the ones written in layer_backward.

```python
def L_layer_backward(HL, Y, memories):
# Takes the predicted value HL and the true target value Y and the 
# memories calculated by L_layer_forward as input
# returns the gradients calculated for all the layers as a dict
 
    gradients = {}
    L = len(memories) # the number of layers
    m = HL.shape[1]
    Y= Y.reshape(HL.shape) # after this line, Y is the same shape as AL
    
# Perform the backprop for the last layer that is the softmax layer
    current_memory = memories[-1]
    linear_memory, activation_memory = current_memory
    dZ = HL - Y
    H_prev, W, b = linear_memory
    gradients["dH" + str(L-1)] = np.dot(linear_memory[1].T, dZ)
    gradients["dW" + str(L)] = (1. / m) * np.dot(dZ, H_prev.T) 
    gradients["db" + str(L)] = (1. / m) * np.sum(dZ, axis=1, keepdims=True)

# Perform the backpropagation l-1 times

    for l in reversed(range(L-1)):

# Lth layer gradients: "gradients["dH" + str(l + 1)] ", gradients["dW" + str(l + 2)] , gradients["db" + str(l + 2)]
        current_memory = memories[l]
        
        dH_prev_temp, dW_temp, db_temp = layer_backward(gradients["dH" + str(l + 1)], current_memory, activation="relu")
        gradients["dH" + str(l)] = dH_prev_temp
        gradients["dW" + str(l + 1)] = dW_temp
        gradients["db" + str(l + 1)] = db_temp
 
    return gradients
```

Do not forget to verify and print the dummy outputs to avoid any errors in the future, as shown in the following code snippet:

```python
# X is (784, 10)
# parameters is a dict
# HL should be (10, 10)
x_sample = train_set_x[:, 10:20]
y_sample = train_set_y[:, 10:20]
 
HL, memories = L_layer_forward(x_sample, parameters=parameters)
gradients  = L_layer_backward(HL, y_sample, memories)
print('dW3 is \n', gradients['dW3'])
print('db3 is \n', gradients['db3'])
print('dW2 is \n', gradients['dW2'])
print('db2 is \n', gradients['db2'])
```

Now that you have calculated the gradients, it is time to update the parameters, i.e., weights and biases.

```python
def update_parameters(parameters, gradients, learning_rate):
# parameters is the python dictionary containing the parameters W and b for all the layers
# gradients is the python dictionary containing your gradients, output of L_model_backward
# returns updated weights after applying the gradient descent update
 
    L = len(parameters) // 2 # number of layers in the neural network
 
    for l in range(L):
        parameters["W" + str(l+1)] = parameters["W" + str(l+1)] - learning_rate * gradients["dW" + str(l+1)]
        parameters["b" + str(l+1)] = parameters["b" + str(l+1)] - learning_rate * gradients["db" + str(l+1)]
    return parameters
```

The list **'****dimensions'**dimensionsdimensions contains the number of neurons in each layer. For a neural network with 1 hidden layer with 45 neurons, you would specify the dimensions as follows:

```python
dimensions = [784, 45, 10] #  three-layer model
```

With this, you have defined all the composite functions required to build the model, i.e., activation functions, feedforward, loss computation and backpropagation. Now, you need to define a function that will build and run your model.

This is a composite function that takes the training data as input X, ground truth label Y, the dimensions as stated above, **learning_rate**, the number of iterations **num_iterations** and, if you want to print the loss, **print_loss**. You need to use the final functions that we have used for feedforward, for computing the loss, for backpropagation and for updating the parameters. Let’s watch the next video to learn more about them.

**VIDEO**

Try to implement the code on your own using the following code:

```python
def L_layer_model(X, Y, dimensions, learning_rate = 0.0075, num_iterations = 3000, print_loss=False):
    
    # X and Y are the input training datasets
    # learning_rate, num_iterations are gradient descent optimization parameters
    # returns updated parameters
 
    np.random.seed(2)
    losses = []                         # keep track of loss
    
    # Parameters initialization
    parameters = initialize_parameters(dimensions)
 
    for i in range(0, num_iterations):
 
        # Forward propagation
        HL, memories = L_layer_forward(X, parameters)
        
        # Compute loss
        loss = compute_loss(HL, Y)
    
        # Backward propagation
        gradients = L_layer_backward(HL, Y, memories)
 
        # Update parameters.
        parameters = update_parameters(parameters, gradients, learning_rate)
                
        # Printing the loss every 100 training example
        if print_loss and i % 100 == 0:
            print ("Loss after iteration %i: %f" %(i, loss))
            losses.append(loss)
            
    # plotting the loss
    plt.plot(np.squeeze(losses))
    plt.ylabel('loss')
    plt.xlabel('iterations (per tens)')
    plt.title("Learning rate =" + str(learning_rate))
    plt.show()
    
    return parameters
```

You can verify the shapes of the training set as follows:

```python
train_set_x_new = train_set_x[:,0:5000]
train_set_y_new = train_set_y[:,0:5000]
train_set_x_new.shape
```

Now, let's watch the next video to learn how to call the function L_layer_model on the data set that we have created.

**VIDEO**

For running this model, the number of iterations considered in the video is 2,000 only. You can increase the number of iterations based on the requirement and time available. Try to implement the code as follows:

```python
parameters = L_layer_model(train_set_x_new, train_set_y_new, dimensions, num_iterations = 2000, print_loss = True)
```

Now that your model is trained, you can compute the accuracy of the model as follows:

```python
def predict(X, y, parameters):
    
    # Performs forward propagation using the trained parameters and calculates the accuracy
    
    m = X.shape[1]
    n = len(parameters) // 2 # number of layers in the neural network
    
    # Forward propagation
    probas, caches = L_layer_forward(X, parameters)
    
    p = np.argmax(probas, axis = 0)
    act = np.argmax(y, axis = 0)
 
    print("Accuracy: "  + str(np.sum((p == act)/m)))
        
    return p
```

The last step is to visualise the predicted and actual outputs of the model. You can do this using the following code:

```python
pred_train = predict(train_set_x_new, train_set_y_new, parameters)

pred_test = predict(test_set_x, test_set_y, parameters)

index  = 3476
k = test_set_x[:,index]
k = k.reshape((28, 28))
plt.title('Label is {label}'.format(label=(pred_test[index], np.argmax(test_set_y, axis = 0)[index])))
plt.imshow(k, cmap='gray')
```

This brings us to the end of the implementation stage. You studied this code in two sessions, i.e., Feedforward and Backpropagation. By now you should know how to work on neural networks and build a model from scratch. 

In the next session, you will build a model on the same data set. However, you need to use a high-level library where you need not write all the lengthy functions. Before we get started, you need to understand a few more important concepts. In the next segment, you will learn about some **regularization techniques** in neural networks.