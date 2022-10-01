# Feedforward Implementation in NumPy - I

Now that you are well acquainted with feedforward neural networks, let’s try implementing it on NumPy using the MNIST data set. You will build a complete neural network using this data set, i.e., feedforward, loss computation, backpropagation and parameter updates. However, in this session, you will only focus on the feedforward portion of the model. 

You can download the data set given below. It is recommended that you write the code side by side and implement it using different candidate values for a better understanding.

Download [MNIST Dataset](mnist.pkl.gz)

For the demonstration, in the module, you will use the Google Colaboratory platform to code. It is a platform provided by Google that gives access to a GPU. In this video, Avishek will introduce the Google Colab environment.

**VIDEO**

As you saw in the video, Google Colab is similar to Jupyter Notebook, and you can write small sections of code and execute them. So open Google Colab and create your own notebook to start coding along with the videos.

In the next video, let’s get started with the model building process by understanding the data set.

**VIDEO**

The MNIST data set consists of 70,000 images of handwritten digits. It consists of digits from 0 to 9, and you are required to classify the class to which the image belongs. The images in the MNIST data set are 28X28 pixels, and the input layer has 784 neurons (each neuron takes 1 pixel as the input). The output layer has 10 neurons, with each giving the probability of the input image belonging to any of the 10 classes. The image is classified into the class that is represented by the neuron with the highest probability. In the diagram below, you can see a few sample images that are available in the dataset.

![MNIST Digits](https://i.ibb.co/fHRW0PG/MNIST-Digits.png)

Note that backpropagation is the final step in the training of a neural network. You need not worry about it here as we'll cover the code implementation as well as the theory in the next session.

You can import the libraries required for this implementation from the code snippet given below.

```python
# Import required libraries:
import numpy as np
import pickle
import gzip
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import h5py
import sklearn
import sklearn.datasets
import scipy
from PIL import Image
from scipy import ndimage
%matplotlib inline
```

You are well versed with most of these libraries; however, the following few libraries might be new to you. 

1.  [pickle](https://docs.python.org/3/library/pickle.html#:~:text=%E2%80%9CPickling%E2%80%9D%20is%20the%20process%20whereby,back%20into%20an%20object%20hierarchy.): Python object serialisation library which converts python object into byte streams and vice versa.
2.  [gzip](https://docs.python.org/3/library/gzip.html): Used to compress and decompress files with the .gz extension.
3.  [h5py](https://docs.h5py.org/en/stable/): This allows you to store and manipulate large numerical data sets.

In the next video, you will go through the steps involved in data preparation for building the feedforward model. 

Play Video

3221820

As you saw in the video, you can start by loading the data using the load_data() method. Since the data set has a .gz extension, you will use the gzip library to open the data set. This function will return three buckets of data: training_data, validation_data and test_data. Try implementing the code on your own using the code snippet below:

```python
# Load the data:
def load_data():
    f = gzip.open('mnist.pkl.gz', 'rb')
    f.seek(0)
    training_data, validation_data, test_data = pickle.load(f,encoding='latin1')
    f.close()
    return (training_data, validation_data, test_data)

# Load the data into training_data, validation_data and test_data arrays:
training_data, validation_data, test_data = load_data()
training_data
```

Next, you can explore the data and gain a good understanding of it. You can use the code given below.

```python
# Check the shape of data:
print(training_data[0].shape)
print(training_data[1].shape)

# Take a look at the feature and target dataset:
print("The feature dataset is:" + "\n" + str(training_data[0]))
print("\nThe target dataset is:" + "\n" + str(training_data[1]))
 
# Take a look at the length of training data:
print("\nThe number of examples in the training dataset is:" + str(len(training_data[0])))
 
# Take a look at number of datapoints in each input:
print("\nThe number of points in a single input is:" + str(len(training_data[0][1])))
```

Next, you will one-hot encode the data into vectors that can then be used for model building and training. You can do this using the code provided below. You one-hot encode the data labels as the output of the network is a (10,1) vector. Hence, the ground truth label should also be of the same dimension. Moreover, it'll help you in the loss/ error calculation. You'll see that in the next session. 

```python
def one_hot(j):
# input is the target dataset of shape (m,) where m is the number of data points
# returns a 2 dimensional array of shape (10, m) where each target value is converted to a one hot encoding
    n = j.shape[0]
    new_array = np.zeros((10, n))
    index = 0
    for res in j:
        new_array[res][index] = 1.0
        index = index + 1
    return new_array
 
data = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
print(data.shape)
one_hot(data)
```

In this segment, you learnt how to load and explore your data. In the next segment, you will learn how to convert all the data into the one-hot encoded vector using the function that you just wrote.