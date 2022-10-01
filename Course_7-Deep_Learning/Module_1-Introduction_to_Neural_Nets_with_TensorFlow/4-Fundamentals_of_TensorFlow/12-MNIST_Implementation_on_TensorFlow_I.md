# MNIST Implementation on TensorFlow - I

Let us get started with implementing a neural network on TensorFlow using the MNIST data set to classify handwritten digits into 10 different classes. You have already implemented the same using NumPy. Now, you will be doing the same on TensorFlow using different libraries. But before getting started, you will learn a bit about **Keras.**

  
Keras is a high-level library designed to work on top of TensorFlow. The main idea of Keras is to be an easy-to-use, minimalistic API that can be used to build and deploy deep learning models quickly. Due to its simplicity, Keras’s syntax and model building pipeline are easy to learn for beginners (although it does not compromise on flexibility - you can do almost everything with Keras that you can do with pure TensorFlow).

  
You will be surprised to see how only a few lines of Python code in Keras can build and train complex, deep neural networks. In the forthcoming segment, you will learn about the typical model building process in Keras. 

  
Now, let us get started with the implementation. Let’s watch this video.

**VIDEO**

Before getting started, you can check the version of TensorFlow as shown below.

```python
# TensorFlow and tf.keras
import tensorflow as tf
 
# Helper libraries
import numpy as np
import matplotlib.pyplot as plt
 
print(tf.__version__)
```

You can load as shown below.

```python
mnist = tf.keras.datasets.mnist
 
(train_images,train_labels),(test_images, test_labels)=mnist.load_data()

class_names = ['0','1','2','3','4','5','6','7','8','9']
```

Now, in the next video, you will explore the data a bit.

**VIDEO**

You can explore the data on your own using this code.

```python
# Explore the training data as follows:
train_images.shape
len(train_labels)

# Explore the test data as follows:
test_images.shape
len(test_labels)

# Visualise an image from the training dataset as follows:
plt.figure()
plt.imshow(train_images[0])
plt.colorbar()
plt.grid(False)
plt.show()
```

Now, the next step is to preprocess the data. If you observe the first image in the training set, you will notice that the pixel values fall in the range of 0 to 255, although for training, the values should lie between 0 and 1. In the next video,you will see how to do so.

**VIDEO**

Scale these values to a range of 0 to 1 before feeding them to the neural network model. To do so, you can divide the values by 255 as shown below.

```python
train_images = train_images / 255.0
test_images = test_images / 255.0

# Visualise an image from the training dataset as follows:
plt.figure(figsize = (10,10))
for i in range(25):
  plt.subplot(5,5,i+1)
  plt.xticks([])
  plt.yticks([])
  plt.grid(False)
  plt.imshow(train_images[i],cmap = plt.cm.binary)
  plt.xlabel(class_names[train_labels[i]])
plt.show()
```

So far, in this segment, you have seen how data is loaded, explored and preprocessed. In the upcoming segment, you will learn how to build and train a model on TensorFlow.