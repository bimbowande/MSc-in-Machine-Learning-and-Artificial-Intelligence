# Tensors

A **tensor** is the **fundamental data structure** used in TensorFlow. It is a multidimensional array with a uniform data type. You have learnt about Spark’s structured API, that is, data frames, which have the same data type for each column. On the other hand, the data type for an entire tensor is the same. 

So, what impact does this have on the ML process? 

In the case of data frames, all the raw data, such as integers, strings and floats, can be loaded into a single data frame. So, you could load raw data into a data frame and then process the data to convert it into a numerical form for ML. In the case of tensors, data would need to be loaded into another data structure and processed first. And when you are ready to learn from the data, you can load it into a tensor. 

Now, in the forthcoming video, you will learn more about tensors from Avishek.

**VIDEO**

So, in the video, you learnt that tensors are **_n_-dimensional arrays**, which are quite similar to **NumPy arrays**. An important difference between these is their performance. NumPy is a highly efficient library that is designed to work on CPUs. On the other hand, TensorFlow can work on CPUs and GPUs. So, if you have a compatible GPU, then it is highly likely that TensorFlow will outperform NumPy.

  
In most use cases in ML, you will use either **2D** or **3D tensors**. A 2D tensor is equivalent to a matrix. It can be used to represent a feature matrix, with each column being a feature and each row being a data point. A 2D tensor would suffice most ML needs. In fact, you might want to convert a higher dimension tensor to a 2D tensor for learning tasks. Recall the ML algorithms that you have learnt so far in this course; the data sets for all of them were in a matrix form, where each row represented a data point and each column represented a feature. This is how all algorithms are designed to work. 

  
For tasks such as image processing, higher dimensions might be needed to represent images. For instance, to completely represent a colour image using a tensor, you will need a 3D tensor in which two dimensions will represent the resolution of the image and the last dimension will represent the number of colour channels, i.e., RGB. These dimensions of the tensor are also called the ranks of the tensor.

  
You can declare two types of tensors in TensorFlow. In the next video, you will learn about them from Avishek.

**VIDEO**

Let us summarise the differences between these two types of tensors:

1.  The values of constant tensors cannot be changed once they are declared, whereas the values of variable tensors can be changed once they are declared.   
     
2.  Constant tensors need to be initialised with a value while they are being declared, whereas variable tensors can be declared later using operations.   
     
3.  An important difference is that differentiation is calculated for variable tensors only, and the gradient operation (this will be explored later in the module) ignores constants while differentiating. 

Note: tf.constant is similar to tf.Tensor; both of them have immutable values. But tf.Variable is different from both. Whenever you declare a tensor with tf.constant, it will be an object of type tf.tensor, as compared with tf.Variable, which is a different object altogether. You can visit the [tf.constant](http://www.tensorflow.org/api_docs/python/tf/constant) page of the documentation to understand this better.

Now, answer these questions based on your learning from this segment.

#### Tensors

Qn: What type of data will need a tensor with rank 4 to capture all the information present in it?

- Text data

- Image data with three colour channel (RGB)

- Image data with four colour channels (CMYK)

- Video data

Ans: D. *Videos are made up of continuously changing images. Rank 3 tensors are sufficient to capture information from each image. The fourth dimension will be used to store timestamps.*

#### Constant and Variable Tensors

Qn: Which of these data would you assign to tf.constant?

- Weights of a model

- Learning rate to be used in gradient descent. 

- The feature matrix

- Actual labels of the data

Ans: B, C & D. *The learning rate will remain constant through the entire learning stage. It must be loaded in tf.constant. The feature matrix will remain constant through the entire learning stage. It must be loaded in tf.constant. Labels will remain constant through the entire learning stage. They must be loaded in a tf.constant.*

Moving ahead, in the next video, you will learn how to declare tensors in TensorFlow.

**VIDEO**

So, in the video, Avishek demonstrated the use of tf.constant to declare tensors. Here are the key observations from the video:

1.  The latest version of TensorFlow, that is, 2.2, is used for the demonstrations. In fact, this version will be used for all the demonstrations in this module. Ensure that you also use the same version when you practise coding. To make sure that you always import the correct version of TensorFlow, use this segment of code:
    
    tf.__version__
    
2.  Three different ranks of tensors were initialised using a list of integer numbers. Note the way in which the tensor with three dimensions was initialised. There are two points to note here: First, the number of square brackets and, second, the use of multiplication. Apart from the brackets needed to declare the 2D array, there is one extra pair. This extra pair of brackets tells TensorFlow that the rank of the tensor being initialised is 3. By multiplying the array by 5, the same array was repeated five times to give the values to the rank 3 tensors. Similarly, you can use a single element or a single row of values to create a tensor of your desired dimension.   
     
    
3.  Whenever a tensor is printed, you will notice its: 
    
    1.  Values, 
        
    2.  Shape and 
        
    3.  Data type.   
         
        
4.  TensorFlow is able to auto-detect the data type of a tensor-based on its values. The following two things can happen if there is variability in the data types of the given values:
    
    1.  The different data types can be combined into one. For example, if a few of the declared numbers are integers and a few are floats, then TensorFlow will make all of them float.
        
    2.  The data types cannot be combined. For example, strings and floats cannot be combined. In such a case, TensorFlow will show an error.
        

        However, the entire tensor needs to have the same data type. 

Now, answer these questions based on your learning from this segment.

#### Initializing Tensors

Which of these is the correct way of initializing a tf.constant tensor ‘p’?

- 
```python
pythonp = tf.constant([1,2,3])
```

- 
```python
p = tf.constant()
q = tf.constant([1,3])
p = q+1
```

- 
```python
p = tf.constant()
p = [1,3]
```

Ans: A. *Constant tensors need to be initialised in the correct manner when they are being declared.*

So, in this segment, you learnt about the methods of declaring tensors of different ranks. Nevertheless, all the tensors declared in this segment were of type tf.constant. In the next segment, you will learn how to declare tf.Variable tensors.