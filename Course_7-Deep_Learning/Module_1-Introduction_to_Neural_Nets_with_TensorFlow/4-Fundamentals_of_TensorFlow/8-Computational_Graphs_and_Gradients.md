# Computational Graphs and Gradients

In the previous segment, you started exploring the mathematical capabilities of TensorFlow. Now, in this segment, you will look at an important capability of TensorFlow, which might be helpful for ML tasks: **Calculating gradients.** 

TensorFlow can find the gradients of equations automatically. Since almost all ML algorithms make use of gradients in the learning process, this ability plays a crucial role in building custom training algorithms. But before you learn about the auto-gradient, you need to understand another concept: **Computational graphs.** 

A computational graph is a representation of the mathematical operations in a TensorFlow program. The forthcoming video will introduce you to the concept of computational graphs.

**VIDEO**

Tensors and computational graphs are the two fundamental concepts in TensorFlow. You know that tensors are the data structures that are used to store data in TensorFlow. In contrast, computational graphs are used to know the ‘flow’ through the different mathematical operations that a tensor will undergo. In a computational graph, the edges show the data (in the form of tensors), whereas the nodes show the mathematical operations that need to be performed on the tensors.

  
Computational graphs have a few benefits, which include the following:

1.  **Visualisation:** Computational graphs help with visualising algorithms, which in turn makes it easier to develop and maintain complex algorithms. This is especially helpful in the case of neural networks since neural network models are quite complex.   
     
2.  **Gradient calculations:** An important ability of TensorFlow is to calculate gradients. Computational graphs are used to trace the dependencies of variables on each other. As you saw in the video, a path is traced from a dependent variable to an independent variable first, and then all the intermediate gradients are calculated and used to compute the expected gradient using the chain rule of differentiation.  
     
3.  **Distributed architecture:** Computational graphs also help with distributing the training process on a cluster of machines. In one of the upcoming segments, you will learn how this distributed architecture works exactly.

Now, in the next video, you will learn about the GradientTape() functionality, which helps with gradient calculation in TensorFlow.

**VIDEO**

The gradient of any function can be calculated by following these steps: 

1.  Initialise the independent variables. The dependent and independent variables need to be tf.Variable-type tensors for the gradient to work.  
     
2.  Create a context of GradientTape() and record the equations that relate to the different variables inside the context.  
     
3.  To find the derivative of an equation that is recorded in the gradient tape context, use .gradient() outside the context and pass in the variable to differentiate and the variable with respect to which the differentiation will occur.

GradientTape() internally calculates the value of the gradient at the given value of the independent variable. Gradient tape has a few other capabilities as well. You will learn about them in the next segment. For now, attempt these questions based on your learning from this segment. 

#### Gradient in TensorFlow

Qn: What is the slope of the curve $y=3x^3+5x^2−3x+10$ at $x=−2$? 

- -2

- 13

- 4

- -6

Ans: B. *This code snippet will help you find the slope of the given curve at x = -2:*

```python
x = tf.Variable([-2], dtype=float)

with tf.GradientTape() as tape:
 y = 3*tf.pow(x,3) + 5*tf.pow(x,2) - 3*x +10

dy_dx = tape.gradient(y,x)

print(dy_dx.numpy()[0])
```

Qn: Consider the function given below: 
$$y=3^{0.2x}+5x^2−log(x)+tanh(x)$$

Using TensorFlow, at $x=10$, find out whether the function is increasing or decreasing.

- Increasing 

- Decreasing

Ans: A. *A function is said to be increasing at a given point if its slope at that point is positive. Find the slope of the curve at x = 10 and check its sign. If the sign is positive, then the function is increasing. If it is negative, then the function is decreasing. Use this code to find the slope of the function at x = 10.*

```python
x = tf.Variable((10), dtype=tf.float32)
with tf.GradientTape() as tape:
  y = tf.pow(3, 0.2 * x) + 5* tf.pow(x,2) - tf.math.log(x) + tf.math.tanh(x)
dy_dx = tape.gradient(y,x)
print("The slope of the function at x = 10 is ", dy_dx.numpy())
```

Moving ahead, in the next segment, you will learn how to compute partial derivatives using GradientTape().