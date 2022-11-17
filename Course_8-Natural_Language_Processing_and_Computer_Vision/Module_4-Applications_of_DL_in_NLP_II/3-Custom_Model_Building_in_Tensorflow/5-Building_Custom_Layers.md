# Building Custom Layers

Instead of using our built-in layers or functions, what if you want to create your own dense layer or your own activation function like softmax or ReLU?

Most of the time when writing code for machine learning models, you want to use the built-in layers as they solve all the traditional problems. But if you want to operate at individual operations and manipulate individual variables, rather than a higher level of abstraction, you need to build classes that extend the **[tf.keras.Layer class](https://www.tensorflow.org/api_docs/python/tf/keras/layers/Layer).** Therefore you don't necessarily have to depend upon the built-in layers provided by the Keras API. 

Let's see how we can utilise the concept of subclassing for building new/custom layers.

**VIDEO**

Here is a basic implementation of `tf.keras.layers.Dense` using custom layer:

```python
class custom_dense(keras.layers.Layer):
    def __init__(self, units, input_dim):
        super().__init__()
        self.w = self.add_weight(
            name="w",
            shape=(input_dim, units),
            initializer="random_normal",
            trainable=True,
        )
        self.b = self.add_weight(
            name="b", shape=(units,), initializer="zeros", trainable=True
        )

    def call(self, inputs):
        return tf.matmul(inputs, self.w) + self.b
```

As explained in the video, using the `__init__` & `call()` method, you can define all input-independent initialisations and forward computations for the layer.

## Model Building by Composing Layers

In machine learning models, models are implemented by composing existing layers. In the previous video,  you have built two custom layers (i.e. **custom dense & custom ReLU function).** Let's now utilise them to build your model in the next video.

**VIDEO**

In the Functional API, once you have defined the functions/modules you can utilise the resulting block to define the architecture of your model. Similarly in the Subclassing API, you use the custom layers to define the model structure.

The **_init_()** defines all the instances of the custom layers that will be utilised in building the model. Once all the instances are defined, you can create the **call()** method which overrides how the computation should happen between the instances & other layers.

## Coming Up

In the next segment, you will study how to build datasets using the tf.data API.