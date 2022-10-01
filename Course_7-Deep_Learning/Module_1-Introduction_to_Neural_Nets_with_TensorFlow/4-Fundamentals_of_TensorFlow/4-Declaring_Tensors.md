# Declaring Tensors

In the previous segment, you learnt how to declare tensors of the tf.constant type. Now, in the forthcoming video, you will learn about a different way of declaring tensors.

**VIDEO**

Let us summarise the observations from the video: 

1.  You can use tf.Variable exactly like tf.constant to initialise a tensor with the values that you can pass in a list. However, in the case of variables, these values can be changed later as well.   
     
2.  You can also specify the data type while initialising the tensor. In this way, you can be sure of the data type. Although this might seem trivial now, in the upcoming segments, you will learn about the importance of declaring the data type.   
     
3.  You can access the values of a tensor directly using the .numpy() function. It will return the values of the tensor as a NumPy array. 

  
So far, you have learnt about many different ways to declare a tensor. Now, open a Google Collab file and try to answer this question.

Exercise 

Declare a tensor of shape (2, 2, 2, 2) with random numbers from a normal distribution whose mean and standard deviation are both 1.

**VIDEO**

So far, you have learnt how to create an array but the mean and standard deviation of the random distributions are not right. In the next part of the solution, you will see how to get the required distribution. 

**VIDEO**

Now, answer these questions based on your learning from this segment.

#### Reading Data With Tensors

Qn: Consider an e-commerce data set with columns such as date of purchase, category of purchase, price, quantity, discount and mode of payment. Suppose you are asked to build an ML model using TensorFlow. Which of these actions will you perform?

- Read the raw data into a tensor and perform all the preprocessing in TensorFlow.

- Read the data into a tensor after converting all the columns to numerical forms.

- Read the data into tensors just before training.

- Read the data into tensors after creating feature vectors.

Ans: C. *The strength of TensorFlow is in building complex models and learning on huge data sets quickly.*

#### Coding With Tensors

Qn: Which of these commands will display the contents of a tensor p, which is given by `p = tf.constant([1,2,3])`?

- p

- p.numpy()

- print(p)

- p.show()

Ans:A, B & C. *`p` will show the contents, shape and data type of the tensor. The command `p.numpy()` will display the contents of the tensor as a NumPy array.*

Moving ahead, in the next segment, you will explore the mathematical capabilities of TensorFlow.