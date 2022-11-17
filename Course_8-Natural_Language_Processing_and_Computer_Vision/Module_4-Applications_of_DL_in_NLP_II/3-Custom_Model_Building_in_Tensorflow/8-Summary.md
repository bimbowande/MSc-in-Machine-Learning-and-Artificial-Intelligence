# Summary

You have come a long way! You have learnt how to customise your layers, models and the training function using the approach of Model subclassing. The most important points to re-iterate are:

`tf.keras` provides many built-in layers, for example:

-   Convolutional layers: Conv1D, Conv2D , etc , etc.
-   Pooling layers: `MaxPooling1D`, `MaxPooling2D`, etc.
-   RNN layers: `GRU`, `LSTM`, etc.
-   `BatchNormalization`, `Dropout`, `Embedding`, etc.

But if you don't find what you need, it's easy to extend the API by creating your own layers. All layers subclass the `Layer` class and implement:

-   `call` method, that specifies the computation done by the layer.
-   `build` method, that creates the weights of the layer (this is just a style convention since you can create weights in `__init__`, as well).
-   The outer container, the thing you want to train, is a `Model`. A `Model` is just like a `Layer`, but with added training and serialization utilities.