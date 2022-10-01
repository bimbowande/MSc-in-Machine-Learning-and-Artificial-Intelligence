# Graded Questions

Please note that the following questions are graded. **All the best!**

#### TensorFlow

Qn: Which of these benefits of TensorFlow make(s) it suitable for deep learning as compared to other libraries like NumPy? (Note: More than one option may be correct.)

- Ability to hold structured data

- Ability to access specialised hardware

- Ability to build complex models with less coding effort

- Ability to calculate gradients automatically

Ans: B, C & D. *Having specialised hardware makes training on large data sets fast. Deep learning models are usually complex, and this ability of TensorFlow makes the coding task easier. Although other libraries have this capability, this capability of TensorFlow helps in building custom models.* 

#### NumPy vs Tensors

Qn: How do tensors differ from NumPy arrays?

- The complete tensor has to be of the same data type.

- The linalg module is only available in NumPy.

- Auto-gradient is available only in TensorFlow.

- Tensors can be processed in GPUs and TPUs.

Ans: D. *TensorFlow has the capability to access special-purpose hardware, and this is the main difference between NumPy and TensorFlow.*

#### Broadcasting

Consider the matrix given below.

```python
p = [[1,2,3,4], [6,7,8,9], [1,2,3,4], [6,7,8,9]]
```

Which of the following codes will produce a result like the one shown below?

```python
q = [[100,200,300,400], [60,70,80,90], [100,200,300,400], [60,70,80,90]]
```

- 
```python
p = tf.Variable([[1,2,3,4], [6,7,8,9], [1,2,3,4], [6,7,8,9]])
r = tf.Variable([[100], [10], [100], [10]])
q=p*r
print(q)
```

- 
```python
p = tf.Variable([[1,2,3,4], [6,7,8,9], [1,2,3,4], [6,7,8,9]])
r = tf.Variable([[100, 10, 100, 10]])
q=p*r
print(q)
```

- 
```python
p = tf.Variable([[1,2,3,4], [6,7,8,9], [1,2,3,4], [6,7,8,9]])
r = tf.Variable([[100], [10]])
q=p*r
print(q)
```

- 
```python
p = tf.Variable([[1,2,3,4], [6,7,8,9], [1,2,3,4], [6,7,8,9]])
r = tf.Variable([[100, 10]])
q=p*r
print(q)
```

Ans: A. *The tensor r is broadcasted to repeat in all rows to obtain the desired output.*

#### Auto Gradient in TensorFlow

Qn: The displacement (in meters) of a point is given by the following:
$\large{S = 3rcos(\theta)}$
Where $r$ and $\theta$ are functions of time t (in seconds) and are given by the following:  
$\large{r=t^2}$
$\large{\theta=t-\pi}$
What is the magnitude of the velocity of the point at t = 0.5 seconds? Note that velocity can be found out by differentiating displacement with respect to time.

- 2.26 m/s

- 3.7 m/s

- 0.89 m/s 

- 7.24 m/s

Ans: A. *To find speed, calculate the derivative of displacement s with respect to time. The following code will help you calculate it.*

```python
t = tf.Variable([0.5])
const = tf.constant([3.0], dtype=float)

with tf.GradientTape() as tape:
 theta = t - 3.14
 r = tf.pow(t,2)
 s = const * r * tf.math.cos(theta)

ds_dt = tape.gradient(s,t)

print(ds_dt.numpy()[0])
```

In the next session, you will learn about some additional concepts and topics related to deep learning models.