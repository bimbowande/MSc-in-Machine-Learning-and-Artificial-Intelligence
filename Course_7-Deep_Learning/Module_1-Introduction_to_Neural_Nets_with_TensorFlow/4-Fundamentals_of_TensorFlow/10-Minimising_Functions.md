# Minimising Functions

In this segment, we will use GradientTape() to find the minima of any given function. Through an example, you will learn how to minimise a function using TensorFlow. The function that needs to be minimised is given below:
$$\Large{y=x^2−4}$$

So, in the forthcoming video, we will look at the problem statement and the approach before understanding how to solve it.

**VIDEO**

It is highly recommended that you attempt this before watching the solution video. Writing code to solve this problem will give you a basic understanding that is necessary for writing your own custom training algorithms. 

## Solution 

The solution video to this problem is split into 4 parts. In the first couple of parts, Avishek will build the loop for gradient descent. And then in the next couple of videos, you will learn to add additional steps to make the training process more informative. And then finally analyse the results.  

### Solution - Part 1 

1.  Initialise the independent variable with an initial guess. 
2.  Declare the function. 
3.  Start building the gradient descent loop.

Let us take a look at the upcoming video and understand the solution.

**VIDEO**

### Solution - Part 2

1.  Complete the gradient descent loop

Get started with the upcoming video where Avishek will explain the solution.

**VIDEO**

With this, the actual solution is complete. In the next steps, Avishek will help us add functionalities that will help us track some important metrics. In this case, those are the value of y and the value of x. Also, you will learn why is it important to use tf.assign to update values of tensors. Take a look at the upcoming video.

**VIDEO**

In the above video, you computed the minima for the given function. Additionally, find the minima of the given function theoretically and compare it to the once computed using TensorFlow.  
 
Given function:  y=x2−4

Differentiating the equation with respect to x you get: dydx=2x

To find the minima, you need to equate dydx to 0. 

Therefore the value of y is minimum when x = 0 and the minimum value of y = -4.

As you can see the minima you calculated above lies very near to the minima that were computed by the TensorFlow function. This verifies your results. Now, that you have a good understanding of this topic, answer the following questions:

#### Minimising Functions

Qn: Using TensorFlow, find the minima of the function: Instead of using the tolerance to decide convergence of the solution, use step gradient method.

number of iteration = 10; learning rate = 0.1

$y=7x^2−4x+10$

Answer y = 9.428 at x = 0.285

Ans: 
```python
import time
import tensorflow as tf
 
x = tf.Variable(tf.random.normal((1,)))
print("Initial value of x:", x.numpy()[0])
 
yprev = 7 *x ** 2 - 4 * x + 10.
print("Initial value of y using initial value of x:", yprev.numpy()[0])
 
iteration = 10
lr = 0.1
 
i = 0
for i in range(iteration):
  i += 1
 
  with tf.GradientTape() as tape:
    y = 7 *x ** 2 - 4 * x + 10.
  
  dy_dx = tape.gradient(y, x)
  x.assign(x - lr * dy_dx) 
 
  ynew = 7 *x ** 2 - 4 * x + 10.
 
  print("x, ynew:", x.numpy()[0], ynew.numpy()[0])
  
  yprev = ynew
  time.sleep(1)
```

In the next segment, let’s take a look at the distributed capabilities of tensors.