# MNIST Implementation on TensorFlow - II

Now that the data is ready, let us start with the model building process in the forthcoming video.

**VIDEO**

The basic building block of a neural network is a **layer**. Layers extract representations from the data fed into them. The majority of deep learning consists of chaining together simple layers. Most layers, such as ‘tf.keras.layers.Dense’, have parameters that are learnt during training. 

You can define the layers of your model as shown below.

```python
model = tf.keras.Sequential([tf.keras.layers.Flatten(input_shape = (28,28)),
    tf.keras.layers.Dense(128 , activation = "relu"),
    tf.keras.layers.Dense(128 , activation = "relu"),
    tf.keras.layers.Dense(10)])
```
The first layer in this network, tf.keras.layers.Flatten, transforms the format of the images from a 2D array (of 28-by-28 pixels) to a 1D array (of 28 * 28 = 784 pixels). Think of this layer as unstacking the rows of the pixels in the image and lining them up. This layer has no parameters to learn; it only reformats the data.  
 

After the pixels are flattened, the network consists of a sequence of two tf.keras.layers.Dense layers. These are densely connected or fully connected, neural layers. The first dense layer has 128 nodes (or neurons). The second (and last) layer returns a logits array of length 10. Each node contains a score, which indicates that the current image belongs to one of the 10 classes. Note that this is happening as we'll apply the softmax in the end.

The next step is to compile the model. Before the model is ready for training, it needs a few more settings. These are added during the model’s compile step:

1.  **Loss function:** This is the function you specify during training basis the type of problem you are solving: regression, classification, multiclass classification among others.. You want to minimise this function to ‘steer’ the model in the right direction.  
     
2.  **Optimiser:** This is how the model is updated based on the data that it sees and its loss function. Usually, it is the stochastic gradient descent abbreviated as 'sgd' but there are many other variants, for which you can refer to the optional session.  
     
3.  **Metrics:** These are used to monitor the model during training and testing steps. The example below uses accuracy, the fraction of the images that are classified correctly.

You can compile your model as shown below.

```python
model.compile(optimizer = 'sgd',
              loss = tf.keras.losses.SparseCategoricalCrossentropy(from_logits= True),
              metrics = ['accuracy'])
```
So, now that your model is ready, it’s time to train it. Training a neural network model requires performing these steps:

1.  Feed the training data into the model. In this example, the training data is in the train_images and train_labels arrays.
2.  The model learns to associate images and labels.
3.  You ask the model to make predictions about a test set, which, in this example, is the test_images array.
4.  You need to verify that the predictions match the labels from the test_labels array.

In the next video, you will see how this is done.

**VIDEO**

You can implement it on your own using this code.

```python
# Feed the model and it learns from the training data:
model.fit(train_images , train_labels , epochs = 10)
 
# Evaluate Accuracy
test_loss , test_acc = model.evaluate(test_images , test_labels , verbose = 2)
print("\n Test Accuracy :" , test_acc)
```

This brings us to the last step of the model building and training process, i.e., making predictions. With the model trained, you can use it to make predictions about some images. The model’s linear outputs, [logits](https://developers.google.com/machine-learning/glossary#logits), attach a softmax layer to convert them to probabilities, which are easier to interpret.

In the forthcoming video, you will see how this can be done.

**VIDEO**

Now, try implementing it on your own as shown below.

```python
probability_model=tf.keras.Sequential([model,tf.keras.layers.Softmax()])
predictions = probability_model.predict(test_images)
 
# Let's take a look at the first prediction:
predictions[0]

# You can see which label has the highest confidence value:
np.argmax(predictions[0])
test_labels[0]
```

With this, you have completed the modelling using TensorFlow. You can see that you do not have to write any code for feedforward or backpropagation, and it really eliminates all the effort. You just need to define the model structure and the hyperparameters. In the next segment, you will summarise your learning from this session.