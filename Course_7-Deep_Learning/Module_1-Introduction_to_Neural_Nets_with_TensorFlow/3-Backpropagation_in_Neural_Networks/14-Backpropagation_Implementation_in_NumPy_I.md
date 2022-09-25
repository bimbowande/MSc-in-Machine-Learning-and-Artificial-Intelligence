# Backpropagation Implementation in NumPy - I

Now that you are well-versed with the loss computation and backpropagation algorithm, let’s resume the implementation of your very own neural network on the MNIST data set using NumPy.

You have already built a feedforward network using this dataset. Now, you will be continuing with backpropagation in the same code file. Before we get started answer the following questions.

#### Revisiting Feedforward Implementation

Qn: What does the memories list hold?

- The values of all activation outputs.

- The values of all parameters obtained post feedforward propagation.

Ans: B. *Memories list stores the parameter values obtained after feedforward propagation.*

Qn: Which is the output layer activation function used for the feedforward model?

- ReLU

- Softmax

Ans: B. *The softmax function is used as the output layer activation function.*

Qn: What is the number of layers for this model that you gave while initialising parameters?

- 2

- 3

- 4

Ans: B. *The number of layers in the model as initialised earlier are three.*

Qn: What is the number of neurons in the output layer?

- 10

- 9

Ans: A. *There are 10 classes from 0 to 9. Hence, the number of neurons in the output layer will be 10.*

The next step is to compute the loss function after every forward pass to keep checking whether it is decreasing with training. The **compute_loss** function calculates the cross-entropy loss. You may want to use [np.log()](https://docs.scipy.org/doc/numpy/reference/generated/numpy.log.html), [np.sum()](https://docs.scipy.org/doc/numpy/reference/generated/numpy.log.html) and [np.multiply()](https://docs.scipy.org/doc/numpy/reference/generated/numpy.multiply.html) here. Do not forget that the loss computed is the average loss across all the data points in the batch. It takes the output of the last layer **HL** and the ground truth label **Y** as input and returns the **loss**. Let’s watch the next video to learn how to compute the loss function.

**VIDEO**

#### Activation Function

Qn: What value did you store in sigmoid_memory while performing feedforward?

- Cumulative input, Z

- The output of the hidden layer, H

Ans: A. *Sigmoid_memory stores the input to the sigmoid function i.e., Z.*

You can compute the loss of your model using the following code snippet:

```python
def compute_loss(HL, Y):
# HL is probability matrix of shape (10, number of examples)
# Y is true "label" vector shape (10, number of examples)
    m = Y.shape[1]
 
# loss is the cross-entropy loss
    loss = (-1./ m) * np.sum(np.multiply(Y, np.log(HL)))
    loss = np.squeeze(loss)
      
# To make sure that the loss's shape is what we expect (e.g. this turns [[17]] into 17).
    assert(loss.shape == ())
   
    return loss
```

Here note that the python code written to compute the loss uses 'np.multiply' to find the product of Y and HL. This is not the same as you saw in the pseudo-code where you computed the dot product of the two vectors. Let us understand why you cannot directly compute the dot product using 'np.dot'. 

If you recall the representation of loss that we saw earlier, it consists of **element-wise multiplication** of Y vector and HL vector(which was p vector in our case) as shown below:
$$\large{-y^T.log(p)=-\begin{bmatrix}y_1&y_2&y_3\end{bmatrix}.\begin{bmatrix}log(p_1)\\log(p_2)\\log(p_3)\end{bmatrix}=-(y_1log(p_1)+y_2log(p_2)+y_3log(p_3))}$$

Using dot product for these vectors will give the correct result but consider if the actual and predicted outputs are in form of matrices as you have used to verify your code ie., HL is 10X5 Y is 10X5. If you apply the dot product function here, it will throw an error due to the incompatible matrix shapes. 

In order to avoid this, you will use np.multiply which will give you the element-wise multiplication of Y and HL as required. After performing the multiplication, next you will be performing the [np.squeeze()](https://numpy.org/doc/stable/reference/generated/numpy.squeeze.html) function to achieve the desired shape of the output.

Also, note that in the code above you are using 1./m instead of 1/m to ensure that the result of division is of float data type and not an integer. For example, 3/5=0 but 3./5=0.6. In python ./ gives a float value.

Do not forget to verify your code before moving ahead:

```python
# sample
# HL is (10, 5), Y is (10, 5)
np.random.seed(2)
HL_sample = np.random.rand(10,5)
Y_sample = train_set_y[:, 10:15]
print(HL_sample)
print(Y_sample)
 
print(compute_loss(HL_sample, Y_sample))
```

Similar to what you did while performing feedforward, you will be writing the activation functions for backpropagation. Let’s watch the next video to learn how to do this.

**VIDEO**

You can write the sigmoid activation function NumPy code as follows:

```python
def sigmoid_backward(dH, sigmoid_memory):
# Implement the backpropagation of a sigmoid function
# dH is the gradient of the sigmoid activated activation of shape same as H or Z in the same layer    
# sigmoid_memory is the memory stored in the sigmoid(Z) calculation
    
    Z = sigmoid_memory 
    H = 1/(1+np.exp(-Z))
    dZ = dH * H * (1-H)
    
    assert (dZ.shape == Z.shape)
    
    return dZ
```

You can write the ReLU activation function NumPy code as follows:

```python
def relu_backward(dH, relu_memory):
# Implement the backpropagation of a relu function
# dH is gradient of the relu activated activation of shape same as H or Z in the same layer    
# relu_memory is the memory stored in the sigmoid(Z) calculation
    
    Z = relu_memory
    dZ = np.array(dH, copy=True) 
# dZ will be the same as dA wherever the elements of A weren't 0
    dZ[Z <= 0] = 0
    
    assert (dZ.shape == Z.shape)
    
    return dZ
```

Now that you have calculated the loss of the model and defined the loss functions, it is time to propagate backwards and calculate the gradients. Remember that the **layer_backward** function is a complementary function of the **layer_forward** function. Similar to how the **layer_forward** function calculates $H$ using $W$, $H_{prev}$ and $b$, the layer_backward function uses $dH$ to calculate dW, $dH_{prev}$ and $db$. You have already studied the important formulas in backpropagation. To calculate $dZ$, you need to use the **sigmoid_backward** and **relu_backward** functions. You might need to use [np.dot()](https://docs.scipy.org/doc/numpy/reference/generated/numpy.dot.html) and [np.sum()](https://docs.scipy.org/doc/numpy/reference/generated/numpy.sum.html) for the rest. Let’s take a look at the code in the next video.

**VIDEO**

You can implement the code for the layer_backward function on your own using the following code:

```python
def layer_backward(dH, memory, activation = 'relu'):
# takes dH and the memory calculated in layer_forward and activation as input to calculate the dH_prev, dW, db
# performs the backprop depending upon the activation function
    
    linear_memory, activation_memory = memory
    
    if activation == "relu":
        dZ = relu_backward(dH, activation_memory)
        H_prev, W, b = linear_memory
        m = H_prev.shape[1]
        dW = (1. / m) * np.dot(dZ, H_prev.T) 
        db = (1. / m) * np.sum(dZ, axis=1, keepdims=True)
        dH_prev = np.dot(linear_memory[1].T, dZ)
        
    elif activation == "sigmoid":
        dZ = sigmoid_backward(dH, activation_memory)
        H_prev, W, b = linear_memory
        m = H_prev.shape[1]
        dW = (1. / m) * np.dot(dZ, H_prev.T) 
        db = (1. / m) * np.sum(dZ, axis=1, keepdims=True)
        dH_prev = np.dot(linear_memory[1].T, dZ)
    
    return dH_prev, dW, db
```

You can verify the code as follows:

```python
# l-1 has two neurons, l has three, m = 5
# H_prev is (l-1, m)
# W is (l, l-1)
# b is (l, 1)
# H should be (l, m)
H_prev = np.array([[1,0, 5, 10, 2], [2, 5, 3, 10, 2]])
W_sample = np.array([[10, 5], [2, 0], [1, 0]])
b_sample = np.array([10, 5, 0]).reshape((3, 1))
 
H, memory = layer_forward(H_prev, W_sample, b_sample, activation="relu")
np.random.seed(2)
dH = np.random.rand(3,5)
dH_prev, dW, db = layer_backward(dH, memory, activation = 'relu')
print('dH_prev is \n' , dH_prev)
print('dW is \n' ,dW)
print('db is \n', db)
```

So far, you have calculated the loss of the model and written the activation functions for backpropagation. You also wrote the backpropagation function for a single layer. In the next segment, you will write the code for the backpropagation of multiple layers at once.