# CIFAR-10 Classification With TensorFlow - I

In the next few segments, you will work in the Google Cloud Platform (GCP) environment to train a CNN network on the [CIFAR-10 data set](https://www.cs.toronto.edu/~kriz/cifar.html) for classification. It has 10 classes of 60,000 RGB images each of size (32, 32, 3). The image given below summarises the 10 classes present in the data set.

![CIFAR10 Dataset](https://i.ibb.co/D9fCp6x/CIFAR10-Dataset.jpg)

**Note:**

-   You are expected to work with Google Colab for this session. We recommend that you use a GPU to run the CIFAR-10 notebooks.
-   You are not expected to download the data set separately. It can be called directly in the notebook through the Keras API.

You can download the notebook for this demonstration from below.

Download [CNN_CIFAR-10](CNN_CIFAR10.ipynb)

Let’s hear Ajay give a brief on the problem statement and the data set in the upcoming video.

**VIDEO**

As highlighted in this video, you will learn how to build a simple CNN architecture to perform classification over the CIFAR-10 data set. Due to the smaller size of the input, a deep VGGNet architecture would not be the right fit for the task. So, you will be working with a smaller version of the same for classification purposes.

However, before you start with the model-building process, it is important to know more about the data. Watch the next video to learn how to load and explore the CIFAR-10 data set.

**VIDEO**

This video covered the initial steps of importing the required libraries and the data set for building the CNN model. The following libraries will be essential in executing the tasks ahead:

-   Keras from TensorFlow for loading the data set and other model building components
-   Matplotlib and Seaborn for data visualisation

After the required libraries have been imported, the load_data() attribute of the ‘dataset’ function is used to load the CIFAR-10 data set.

![CIFAR10 load_data()](https://i.ibb.co/ckt7t8D/CIFAR10-Load-Data.png)

The data set is automatically segregated into ‘training’ (50,000 images) and ‘testing’ (10,000 images) sets. Both the sets are also accompanied by the corresponding labels for each data sample. All the class names are specified under the variable ‘class_names’ for later reference. In addition to defining the variables, the video summarised how to normalise the pixel values associated with each image. All the values were simply divided by 255 to scale them between 0 and 1.

Now that all the variables have been defined, let’s verify that all the elements are loaded correctly.

**VIDEO**

The video highlighted the structure of both the training and the testing sets. The only difference between the two is the number of samples.

In the next segment, you will perform some basic operations on top of the images to understand the visual data better.