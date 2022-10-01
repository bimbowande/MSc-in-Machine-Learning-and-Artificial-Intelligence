# Mathematical Operations on Tensors

Now that you have learnt about the basics of tensors, this segment will focus on the mathematical operations that you can perform on them. Since TensorFlow is an ML library, it has all the necessary operations that you might need. In the forthcoming video, Avishek will explain the overall mathematical capabilities of TensorFlow. 

**VIDEO**

**Note:** In the presentation shown in the video, it is mentioned that the Jupyter notebook will be used in the demonstration. However, all the demonstrations in this module will be performed using Google Colab.

  
So, as you saw in the video, TensorFlow has all the capabilities that you might need for building an ML model. Although the objective of this module is to get you comfortable with using TensorFlow, it is not possible to cover all of its mathematical functions and capabilities. The module will discuss the fundamental concepts of coding in TensorFlow, although you are strongly recommended that you visit the [Tensorflow documentation](https://www.tensorflow.org/api_docs/python/tf) for better coverage. Now, in the forthcoming video, you will start with the most basic operations, such as addition and subtraction. 

**VIDEO**

So, as you saw in the video, TensorFlow supports all the basic mathematical operators, and you can call them by simply using the respective operators. To use the operator commands, you need to ensure that both the tensors on which the operations are being carried out have the same dimensions. An error will be thrown if their dimensions are not the same because the operations are performed element-wise. Another point to note is that when you divide any number by 0, TensorFlow is smart enough to show infinity. 

  
The same operations can also be performed using the functions in the TensorFlow library. For example, you can use tf.add() in place of the addition operator. Similarly, tf.subtract(), tf.multiply() and tf.divide() work exactly how you would expect them to. You can go [here](https://www.tensorflow.org/api_docs/python/tf/math) to read about all the available mathematical functions. 

#### Mathematical Operations on Tensors

Qn: Write a code in TensorFlow to perform this task:   
Initialise a 2-by-2 tensor with all integer values and then create another tensor by squaring all the elements in the first tensor. (Note: More than one option can be correct.)

- 
```python
tensor1 = tf.random.uniform((2,2), minval= 1, maxval= 20, dtype= tf.int32)
print("Initial tensor: ", tensor1.numpy())
tensor2 = tf.pow(tensor1, 2)
print("Squared tensor = ", tensor2.numpy())
```

- 
```python
tensor1 = tf.random.uniform((2,2), minval= 1, maxval= 20)
print("Initial tensor: ", tensor1.numpy())
tensor2 = tf.pow(tensor1, 2)
print("Squared tensor = ", tensor2.numpy())
```

- 
```python
tensor1 = tf.random.uniform((2,2), minval= 1, maxval= 20, dtype= tf.int32)
print("Initial tensor: ", tensor1.numpy())
tensor2 = tensor1 * tensor1
print("Squared tensor = ", tensor2.numpy())
```

- 
```python
tensor1 = tf.random.uniform((2,2), minval= 1, maxval= 20, dtype= tf.int32)
print("Initial tensor: ", tensor1.numpy())
tensor2 = tf.multiply( tensor1 , tensor1)
print("Squared tensor = ", tensor2.numpy())
```

Ans: A, B & D. *The `random.uniform` function generates the initial tensor and the pow function calculates the element-wise squaring operation. Squaring can also be achieved with the multiplication operator. Numbers can be squared using the tf.multiplication operator as well.*

Qn: What will be the result of this code?
```python
t1 = tf.Variable([[2,3,4], [5,7,9], [1,6,3], [5,8,4]])
t2 = tf.Variable([[2,3,4,5], [5,7,9,4], [1,6,3,9]])

t3 = t1 + t2
```

- The tensor t3 will be assigned the sum of the two tensors.

- An error will be thrown.

Ans: B. *Since the shapes of the tensors are not compatible, the code will throw an error.*

Moving ahead, in the next segment, you will learn about the linear algebra module available in the TensorFlow library.