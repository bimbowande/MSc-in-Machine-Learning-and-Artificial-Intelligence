# Comprehension - Training a Neural Network

Training a network essentially involves finding the optimal set of weights and biases to minimise the total loss. The loss function is the difference between the actual output and the output predicted by the network (aggregated across all training data points).  
 

Let's consider a simple neural network acting as an OR gate to understand the training process, as shown in the diagram below.

**Neuron**

![Neuron](https://i.ibb.co/3TJKkZc/Neuron.jpg)

A logical OR gate is shown in the following table. Assume that the input to the OR gate is represented by two features $(x_1,~x_2)$ . The output of the gate is 1 if at least one of the inputs is 1, else it is 0.

| Input $(x_1,~x2)$ | Output $(y)$ |
| ------------ | --------- |
| (0, 0)       | 0         |
| (0, 1)       | 1         |
| (1, 0)       | 1         |
| (1, 1)       | 1         |

The table above is the training dataset, i.e we have four data points in the training set. Also, our network has a single neuron (in its only hidden layer). The activation function for this neuron is defined as follows:
 $$\large{\begin{cases}y=f(x)=1;\text{ if }x\ge1\\\\0;~otherwise\end{cases}}$$

Assume that the bias of the neuron is 0. Thus, the weight matrix is $W=[w_1,~w_2]$. Try attempting the following questions:

#### Training of a Network

Qn: Mark all the correct option(s):

- The training task is to find the weight vector $(w_1,~w_2)$ which minimizes the loss.

- In training, the network will start with a random guess of the two weights, calculate the predicted output and iterate the weights

- In training, the network will start with a random guess of the activation function, calculate the predicted output and iterate the function

- The training task is to find the set of outputs which minimizes the loss

Ans: A & B. *Training a neural network basically implies finding correct values for weights and biases which minimises the loss function. The model starts with a random guess of the initial weights, predict the output using feedforward and change the weights in the direction of reducing loss. This is the gradient descent algorithm.*

#### Output of the Network

Qn: For an initial guess of the weights $w=(0,~0)$ the predicted output:

- Is 0 irrespective of the input

- Is 1 irrespective of the input

- Depends on the input

Ans: A. *Given that v = w.x where w is the weight and x is the input. Multiplying input with weight 0 would result in $v=0$. Activation function is given as $f(v)=1$ if $v\ge1$ so $f(0)=0$ irrespective of input. 0 otherwise*

The following image shows the different combinations of the weights, the inputs $(x_1,~x_2)$, the predicted outputs and the loss for an initial guess of $W=[0,~0]$.  The input can be either of the four values in column-2. We can calculate the predicted output for different values of W, compare that with the true output of an OR gate and compute the loss. 

The aim of the following exercise is to find the right w1 and w2 which minimise the total loss and correctly represent an OR gate. 

**Training a Single Neuron with Weights = $[w_1,~w_2]$**

![Training a Single Neuron with Weights = w1, w2](https://i.ibb.co/12Z64sj/Training-a-Single-Neuron-with-Weights-w1-w2.png)

Training a Single Neuron with Weights = $[w_1,~w_2]$

#### Total Loss

Qn: For weight $W=[1,~0]$, the total loss is:

- 0

- 1

- 2

- 3

Ans: A. *The predicted outputs for each input $(x_1,~x_2)$ are $0,~0,~1,~1$. The true outputs are the same i.e. $0,~1,~1,~1$. The loss vector is $(0,~1,~0,~0)$ and hence the total loss is sum of $loss(i) = 1$.*

#### Gradient Descent

Qn: The gradient descent algorithm will:

- Move in the direction of reducing weights by changing the loss

- Move in the direction of reducing loss by changing the weights

- Move in the direction of reducing weights by changing the activation function

- Move in the direction of reducing value of activation function by changing the loss

Ans: B. *We want to minimize the loss by changing the weights, i.e. move in the direction where $\dfrac{d(Loss)}{d(W)}$ decreases.*

Qn: The gradient can be thought of as:

- The slope of a hill whose height represents the weight $[w_1,~w_2]$ and each location on the hill represents a unique cost.

- The slope of a hill whose height represents the total cost and each location on the hill represents a unique activation function.

- The slope of a hill whose height represents the total cost and each location on the hill represents a unique weight $[w_1,~w_2]$.

Ans: C. *We can imagine a hill whose height represents the total cost and each location on it represents a unique weight $[w_1,~w_2]$. Then we want to minimize the height (i.e. the cost), i.e. move in the direction of the slope of the hill to a point $[w_1,~w_2]$ where the cost / height is minimum.*

Qn: We can imagine a hill whose height represents the total cost and each location on it represents a unique weight vector $(w_1,~w_2)$. The gradient, or the slope, can then be defined as $\dfrac{d(Loss)}{d(W)}$, i.e. change in total cost with respect to the change in $W=(w_1,~w_2)$. While changing the weight vector from the (0,0) to (1, 0):

- The value of d(Loss) is positive

- The value of d(Loss) is negative

- The value of d(Loss) is 0

Ans: B. *The total costs for $w=(0,~0)$ and $w=(1,~0)$ are 3 and 1 respectively. The cost thus reduces as we move from $(0,~0)$ to $(1,~0$)$, so d(Loss) is negative.*

Qn: While changing the weight vector from the (1, 0) to (0, 1):

- The gradient is positive

- The gradient is negative

- The gradient is 0

Ans: C. *For weights = (1, 0) and (0, 1), the loss is 1, or d(Loss) is 0. Thus the gradient is $\dfrac{d(Loss)}{d(W)}=0$.*

Qn: We can imagine a hill whose height represents the total cost and each location on it represents a unique weight $(w_1,~w_2)$. In case of heavy rainfall, the water will get accumulated at the point:

- (0, 0)

- (0, 1)

- (1, 0)

- (1, 1) 

Ans: D. *The point where $w=(1,~1)$ minimizes the Loss since, at that point, the predicted output exactly matches the true output of an OR gate.* 

Note that here, we are randomly choosing the weights and calculating the loss and not in a systematic manner followed in gradient descent scheme of things. The objective of this comprehension is to understand that we need to find the optimal sets of weights to minimize the loss function in neural network training. Now that you have understood this, let's proceed to the next segment to develop an understanding of the concept of **backpropagation.**
