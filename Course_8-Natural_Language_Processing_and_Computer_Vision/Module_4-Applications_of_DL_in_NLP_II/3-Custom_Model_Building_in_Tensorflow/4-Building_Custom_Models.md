# Building Custom Models

Inheritance is a concept in object-oriented programming in which a class derives (or inherits) attributes and behaviours from another class without needing to implement them again.

It allows you to call methods of the superclass in your subclass. So, now you will inherit the basic characteristics of **tf.keras.Model class** to build your own custom deep learning models. 

Sandeep will now help you in implementing this using a simple example of the MNIST dataset in the next video.

**VIDEO**

Here, you have another method, **call()**, that you need to utilise in the subclassing approach. Using this method, you can apply different operations which you want to perform for the layers that are defined in the __init__ function earlier. So, the call() method is the place where we define our forward pass of the model.

By customising the call() method, we are overriding the inherited call method. Therefore we don't need to invoke it using the **model.call()**, it automatically is activated when the instance of your model is called.

But as you have seen there is an error that has popped up when we wanted to summarise our model. Let's see how we can resolve this error in the next video.

**VIDEO**

Both the Sequential and Functional API represents a graph structure of layers which is built by stacking layers one on top of each other. Both these approaches can infer the shape of all other layers defined in the model once you have provided the **input_shape** to the first layer. Therefore, you can easily print the input/output shapes using model.summary().

But on the other hand, model subclassing is defined using the class which is only invoked by the call method. Here, there is no graph structure for layers, so you cannot know how different layers are interacting with each other since that is defined in the body of the class.

Therefore you cannot infer the input/output shape in the subclassing approach until you have tested with the given data. This is the reason why no error will be thrown if you run the model with the data and then use **model.summary()**. 

## Coming Up

In the next segment, you will study how to build custom layers.