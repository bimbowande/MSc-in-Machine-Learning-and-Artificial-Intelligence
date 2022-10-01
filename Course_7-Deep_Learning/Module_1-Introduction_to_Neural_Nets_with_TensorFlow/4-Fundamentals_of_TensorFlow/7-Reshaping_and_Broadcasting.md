# Reshaping and Broadcasting

As discussed in the previous segment, shape-modifying functions are important because several matrix operations require shape compatibility. It is likely that you will have to modify the shapes of tensors to make sure computations with ML algorithms do not throw errors. Keeping this in mind, in this segment, Avishek will introduce a few commands that can be used to modify the shapes of tensors.

**Reshaping:** As the name suggests, reshaping changes the dimension of a tensor. Nevertheless, the reshape function has certain limitations. It can reshape a tensor but cannot remove or add new elements. For instance, consider a tensor of shape (3, 4); it will have 12 elements. The reshape function can change the shape of this tensor to (4, 3) or (6, 2), or even (12, 1), but not (4, 4). In case the shape is changed to (4, 4), you will need 16 elements, but you have only 12; hence, the reshape operation will throw an error.

The forthcoming video will help you understand the concept better through a demonstration.

**VIDEO**

**Broadcasting:** There is a way you can perform an operation on tensors with mismatching dimensions as well. You can broadcast the elements to more dimensions. For instance, you can use a matrix with shape (1) and multiply it by a matrix of shape (3, 3). Even though the shapes are not compatible, this multiplication is executed because the smaller matrix is repeated over all the elements of the larger matrix. This repetition of one matrix is called broadcasting.

In PySpark, the broadcast operation includes storing a given data frame in the cache of all the machines in the network. That way all the machines can obtain the data from the broadcasted data frame faster. The PySpark API has a special command for this operation. In TensorFlow, you do not need to write any extra command to specify the matrix that is to be broadcasted. TensorFlow can determine this independently. So, before moving ahead, let’s watch the next video, which shows how broadcasting is implemented. 

**VIDEO**

There are certain limitations to broadcasting. It is possible only if for each pair of corresponding dimensions in the shape of the two tensors, either both the shapes are equal or one of them is 1. If the rank of the tensors is not the same, then the tensor with the smaller rank is assumed to have 1 as the missing rank. The table below shows a few examples.

| **Tensor a** | **Tensor b** | **Broadcasting Comment**                                                                                                                                                                                                          |
| ------------ | ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| (3,3)        | (1,)         | Only one element in matrix b is to be multiplied, which is almost similar to scalar multiplication. <br>Corresponding dimension pairs: (3, 1) and (3, assumed 1)                                                                  |
| (3,4)        | (3,1)        | Since the number of rows in tensor b is the same as that in tensor a, one column will be repeated four times for each column in tensor a.<br>Corresponding dimension pairs: (3, 3) [equal] and (4, 1) [one of the dimension is 1] |
| (2,3,3)      | (3,3)        | In this case, two dimensions match, and the 2D matrix can be repeated twice to make the operation work. <br>Corresponding dimension pairs: (2, assumed 1) [one of the dimension is 1], (3, 3) [equal] and (3, 3) [equal]          |
| (4,4)        | (2,2)        | Although the (2, 2) pattern can be repeated to create a (4, 4) matrix, this does not work.   <br>Corresponding dimension pairs: (4, 2) [not equal], (4, 2) [not equal]                                                            |

To iterate, the broadcast operation needs to meet certain conditions, and if these conditions are met, then the shapes of the tensors are said to be compatible. And compatible tensors are defined by this rule: Two shapes are compatible if for each dimension pair, they are either equal or one of them is 1. When trying to broadcast a tensor to a shape, it starts with the trailing dimensions and works its way forward.s

**Expanding dimensions:** If you noticed the possible broadcasting operations carefully, then you must have realised that in a few cases, you were essentially increasing the dimensions of a tensor by broadcasting it to a larger tensor. This can also be achieved using the expand_dimms method, with which you can add a dimension to a tensor without adding elements to the new dimension.

**VIDEO**

Try answering the following questions:

#### Libraries in TensorFlow

Qn: Consider the following Boolean matrix:

```python
q = [[True, False], [True, False]]
```

Which of the following codes will produce a result like the one shown above? 

```python
p = [[True, False],[False, False]]
```

Hint: You will need to explore the TensorFlow library to gain more understanding of the functions used in the following options

- 
```python
q = tf.Variable([[True, False], [True, False]])
r = tf.Variable([True])
p=tf.math.logical_and(q,r)
print(p)
```

- 
```python
q = tf.Variable([[True, False], [True, False]])
r = tf.Variable([True])
p=tf.math.logical_or(q,r)
print(p)
```

- 
```python
q = tf.Variable([[True, False], [True, False]])
r = tf.Variable([[True, True], [False, True]])
p=tf.math.logical_and(q,r)
print(p)
```

- 
```python
q = tf.Variable([[True, False], [True, False]])
r = tf.Variable([[False, False], [False, False]])
p=tf.math.logical_or(q,r)
print(p)
```

Ans: C. *This code will produce the desired output. It will simply calculate the logical AND between the two Boolean matrices to produce the output.*

#### Reshaping Tensors

Qn: Use TensorFlow to complete this task.  Task: Convert the tensor 'p' given in the cell below into a cube tensor of rank 3.

```python
p = tf.Variable(np.random.randn(1,64))
```

(Note: More than one option can be correct.)

- 
```python
p = tf.Variable(np.random.randn(1,64))
reshaped_p = tf.reshape(p, (8,8,1))
```

- 
```python
p = tf.Variable(np.random.randn(1,64))
reshaped_p = tf.reshape(p, (8,8,8))
```

- 
```python
p = tf.Variable(np.random.randn(1,64))
reshaped_p = tf.reshape(p, (4,4,4))
```

- 
```python
p = tf.Variable(np.random.randn(1,64))
reshaped_p = tf.reshape(p, (1,1,64))
```

Ans: A, C & D. *Correct, the resultant tensor will be of rank 3. And the number of elements before and after reshaping is also the same.*

In the upcoming segment, you will learn the concepts of **computational graphs** and **gradients** with TensorFlow.