# Model Subclassing

In the previous segment, you have learnt how to implement Sequential and  Functional API.

Among these two, you might have observed that the Sequential API is the easiest approach to build models, but it’s also a naive approach there are many limitations when it comes to:

-   Building models with multiple inputs and outputs
-   Sharing layers

The Functional API bridge this gap by allowing you to create more complex models. This approach provides the support of **multiple inputs and multiple outputs, layer sharing, branching and reusability.** But in this approach for each block, we are applying operations on the built-in layers. The Keras API provides you with many built-in layers like:

-   Convolutional layers: Conv1D, Conv2D, etc.
-   Pooling layers: MaxPooling1D, MaxPooling2D, etc.
-   RNN layers: GRU, LSTM, etc.
-   BatchNormalization, Dropout, Embedding, etc.

But if you don't want to work with these built-in layers and you want to create your own layers, then the third approach - **Model Subclassing** provides an elegant solution.

Model Subclassing is tailor-made for advanced developers who want to customise how their **model, layer, and training process** works. Let's understand this in detail in the next video.

**VIDEO**

As explained in the video, the subclassing approaches are based on the process of creating classes that extend from the **[tf.keras.Model](https://www.tensorflow.org/api_docs/python/tf/keras/Model) class.** Using the principle of inheritance, these classes inherit the general properties of a model class that is defined already, thus providing us code reusability. Thus the **tf.keras.Model** class becomes the **parent** for these **subclasses**. This is why this approach of custom model building is called **Model Subclassing.**

Here the class that we are defining is a blueprint for creating objects, through which we can define certain characteristics for different objects when created. These characteristics would help in initialisation when each object of a class is initialised.

The notebook that you will use in this session can be downloaded below:

Download [Working with Tensorflow](TensorFlow_Classing.ipynb)

**VIDEO**

As explained in the video, there are two crucial terms in Model subclassing:

-   **__init__ method**: Where you can do all input-independent initialisation. The **init** method is similar to constructors in C++ and Java. Constructors are used to initialising the object’s state. The task of constructors is to initialise(assign values) to the data members of the class when an object of the class is created. The method is useful to do any initialisation you want to do with your object.
-   **self**: The keyword self represents the instance of a class and binds the attributes with the given arguments. It is an instance of the class that we are building, therefore 'self' represents the objects when they are created.  By using the 'self' keyword we can access the attributes and methods of the class and can bind the instance or objects with the attributes at the time of object creation.

There is another crucial parameter called **super()** which is very essential for the concept of class and inheritance. Let's understand it in the next video.

**VIDEO**

## Coming Up

In the next segment, you will study how to utilise model subclassing for building your deep learning models.