# Linear Algebra with TensorFlow

In this segment, you will learn about the functions that can help you perform linear algebra tasks. In the forthcoming video, Avishek will walk you through some commonly used functions of the linear algebra module on TensorFlow.

**VIDEO**

So, in this video, you learnt about the linalg module on TensorFlow. Let’s summarise the concepts that were covered in the video:

1.  The linalg module in the TensorFlow library has all the necessary functions for processing matrices. You can go here to read about the functions available.   
     
2.  Many matrix operations require shape compatibility. For instance, in the case of matrix multiplication, the number of columns in the first matrix needs to be equal to that in the second. Conditions such as these need to be met while performing the respective operations on tensors. And if such conditions are not met, then TensorFlow will throw an error.   
     
3.  It is possible that some linear operations are not defined. For example, all the matrices cannot be inverted. In such cases as well, TensorFlow will throw an error. So, to perform a matrix operation, that operation should be mathematically possible. For example, it is not possible to calculate the inverse of a matrix with determinant 0. It will not be possible in TensorFlow as well.    
     
4.  TensorFlow uses numerical algorithms for carrying out matrix operations.; So, it is important to have a tensor that is of float data type.

Now, answer these questions based on your learning from this segment.

#### System of Linear equations

Qn: Solve the following system of linear equations using TensorFlow. 

x + y + z + w = 13  
2x + 3y − w = −1  
−3x + 4y + z + 2w = 10  
x + 2y − z + w = 1

Answer: x=2, y=0, z=6 and w=5

(After running your code in the colab notebook paste it below)

Ans: 
```python
t1 = tf.transpose(tf.constant([[13., -1, 10,1]]))
t2 = tf.constant([[1.,1,1,1],[2,3,0,-1],[-3,4,1,2],[1,2,-1,1]])
tf.linalg.matmul(tf.linalg.inv(t2), t1)
```

Let’s summarise the theory behind solving the system of linear equations. The matrix representation of linear equations is represented as follows:
$$\Large{W.X=Y}$$

Where W is the coefficient matrix, X denotes the variables and Y is the output matrix. On solving for X, you will obtain the following: 
$$\Large{X=Y.W^{−1}}$$

In the upcoming video, Avishek will solve the above equation for you.

**VIDEO**

Based on the knowledge of the above video, try solving this question:

#### Mathematical operations on tensors

Qn: The weights and the bias term of a trained model logistic regression model are given below.   
w1 = 0.5, w2 = 1 , w3 = -1.2   
b = 0.01

The features of a certain data point are given below.
 
 x1=0.2, x2=1, x3=0.5

Using TensorFlow, find the probability of the data point belonging to the positive?

- 0.5547

- 0.2439

- 0.6248

- 0.7154

Ans: C. *You can use this code segment to calculate the probability. To make the process simpler than the one shown in the code below, you can explore the functions available in the TensorFlow library.*

```python
x = tf.Variable([[0.2, 1, 0.5]])
w = tf.Variable([[0.5], [1] , [-1.2]])
b = tf.Variable([[0.01]])

a = tf.add(tf.matmul(x,w), b)

p = tf.sigmoid(a)
print(p.numpy()[0][0])
```

In this session, you learnt how to perform linear algebra with TensorFlow. In the next segment, you will learn about a very important topic i.e., **Reshaping** and **Broadcasting.**