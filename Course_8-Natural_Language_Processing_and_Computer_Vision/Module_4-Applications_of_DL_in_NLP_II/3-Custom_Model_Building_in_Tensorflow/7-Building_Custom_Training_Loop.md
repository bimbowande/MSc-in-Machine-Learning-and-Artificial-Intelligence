# Building Custom Training Loop

The most interesting feature part of the model training is using the fit()  method on your model as it provides you with a seamless training operation that works smoothly.

Behind the fit() method is the backpropagation step through which you optimise your model's parameter to understand the mapping between the input data and target. The entire process can be summarised in these steps:

-   Find the prediction from your model.
-   Compute the loss between the target and the predicted value.
-   Backpropagate errors, by tracking the gradients of your computation.
-   Apply these gradients to your model parameters using an optimiser.

Tensorflow provides us [GradientTape()](https://www.tensorflow.org/api_docs/python/tf/GradientTape) and takes control of every little detail when we want to monitor all the operations and calculate their differentiation. Let's understand all these details using a simple example in the next video.

**VIDEO**

Now that you have understood how to use the Gradient Tape for calculating the differentiation, let's utilise it for building custom training for our model.

**VIDEO**

Like you have utilised the features of **tf.keras.Model** and **tf.keras.layers.Layer** for our custom model and layers, you also want to benefit from the convenient features of **fit()** method. This allows us to have control over the little details and each operation while retaining high-level abstractness and simplicity.

While customising the fit() method, you have to override the **train step** function of the Model class, like we have overridden the call() method for customising our forward pass.

The train step function is automatically called when you apply the fit() method to your model. Therefore this approach provides customisation under the comfortability of fit() method.

Broadly you can summarise the whole custom training process in these steps:

-   Creation of a new class (by subclassing keras.Model)
-   Overriding the method  `train_step(self, data)`
-   Returning a dictionary that contains the metric names with their respective values

```python
class CustomModel(keras.Model):
    def train_step(self, data):
        # Unpack the data. Its structure depends on your model and
        # on what you pass to `fit()`.
        x, y = data

        with tf.GradientTape() as tape:
            y_pred = self(x, training=True)  # Forward pass
            # Compute the loss value
            # (the loss function is configured in `compile()`)
            loss = self.compiled_loss(y, y_pred, regularization_losses=self.losses)

        # Compute gradients
        trainable_vars = self.trainable_variables
        gradients = tape.gradient(loss, trainable_vars)
        # Update weights
        self.optimizer.apply_gradients(zip(gradients, trainable_vars))
        # Update metrics (includes the metric that tracks the loss)
        self.compiled_metrics.update_state(y, y_pred)
        # Return a dict mapping metric names to current value
        return {m.name: m.result() for m in self.metrics}
```

## What's Next?

With all the learnings provided in this session, you are now ready to utilise all the techniques for building your custom layers/models as part of the capstone.