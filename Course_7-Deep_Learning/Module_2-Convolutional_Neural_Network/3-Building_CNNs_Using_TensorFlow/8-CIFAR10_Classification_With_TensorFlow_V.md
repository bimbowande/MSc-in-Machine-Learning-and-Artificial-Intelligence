# CIFAR-10 Classification With TensorFlow - V

You now have the complete CNN architecture ready. The next step is to train the model to obtain all the parameters and then validate the obtained results on the testing set. This segment will deal with these steps and also help you with different experiments around the hyperparameters to obtain improved results.

You will need the same steps to train and fit the CNN model as the ones carried out previously for the simple ANN architecture. Watch the next video to know more.

**VIDEO**

The following results are obtained after each epoch in the model training process.

![Model Training Process](https://i.ibb.co/2FgDMr0/Model-Training-Process.png)

As you can see, the accuracy value for the training set increases with each epoch. Note that the simple ANN model stagnated at an accuracy of 48%. This suggests that a simple CNN model is more suited for the image data set. (Note: It is still possible to develop an ANN architecture with similar results, but it would be too complex and would require much more computational resources.)

Coming to the validation set, the value has improved from the previous model but does not seem to follow the same trend as the training set.

![Train vs Validation Accuracy](https://i.ibb.co/J3YB5j4/Train-vs-Validation-Accuracy.png)
This suggests that the model is suffering from the problem of overfitting. It should be further optimised to perform better on the validation set.

For this purpose, you can alter different hyperparameters or introduce different elements in the model. The segment will cover some basic experiments for your understanding. Let's try and take a look at them one by one.

1.  **Increase in number of epochs**

You can increase the number of epochs to 50 and train the model at your end, as this will involve a lot of training time. The graph given below summarises the results obtained from this process.

![Increase in Number of Epochs](https://i.ibb.co/tqmvfyZ/Increase-in-Number-of-Epochs.png)

As you can see, the increase in training cycles does not lead to any improvement. This validates the previous argument that the model is suffering from overfitting. Let’s now move onto the next experiment.

2.  **Adding dropout layers**

One of the primary practices to overcome overfitting in a neural network is the addition of dropout layers. Let's see how this influences the present model, in the next video.

**VIDEO**

As you saw in the video, the dropout layer helps in reducing the complexity of the model because lesser information translates to the next layer due to the reduced number of neurons. The image given below summarises the results of this experiment.

![Adding Dropout Layers](https://i.ibb.co/9ypzXrF/Adding-Dropout-Layers.png)

Even though the training accuracy has dropped, there is a positive impact, as the model no longer seems to suffer from the problem of overfitting.

3.  **Batch normalisation (without dropout)**

Another experiment introduced in the video was batch normalisation. This technique normalises the input by taking an aggregate (mean or standard deviation) over batches of the layer. This also results in a small change in accuracy but is not able to handle the problem of overfitting.

![Batch Normalisation without Dropout](https://i.ibb.co/hZ5ZsmB/Batch-Normalisation-without-Dropout.png)

To further increase the accuracy and overcome overfitting, a combination of both dropout and batch normalisation can be used.

4.  **Adding more convolution units**

Under this experiment, you can try and increase the convolution units (presently two) in the architecture. The objective of adding more convolution layers is to extract more features. The following code will help you in this experiment.

```python
# Defining the model
model = models.Sequential()
 
# Adding layers to the model
 
# 1st Conv Block - 2 convolution layers and 1 Pooling layer
model.add(layers.Conv2D(32, (3, 3), padding = 'same', activation='relu', 
                        input_shape=(32, 32, 3)))
model.add(layers.Conv2D(32, (3, 3), padding = 'same', activation='relu'))
model.add(layers.MaxPooling2D((2, 2)))
 
# 2nd Conv Block - 2 convolution layers and 1 Pooling layer
model.add(layers.Conv2D(64, (3, 3), padding = 'same', activation='relu'))
model.add(layers.Conv2D(64, (3, 3), padding = 'same', activation='relu'))
model.add(layers.MaxPooling2D((2, 2)))
 
# 3rd Conv Block - 2 convolution layers and 1 Pooling layer
model.add(layers.Conv2D(128, (3, 3), padding = 'same', activation='relu'))
model.add(layers.Conv2D(128, (3, 3), padding = 'same', activation='relu'))
model.add(layers.MaxPooling2D((2, 2)))
 
# Flattening and Dense layers
model.add(layers.Flatten())
model.add(layers.Dense(512, activation='relu'))
 
# Adding the output layer
model.add(layers.Dense(10))
 
# Model summary
model.summary()
```

As you can see, we have increased the number of features from 64 to 128 in the new convolution block. You can train the model at your end, as this will involve a lot of training time. The graph given below summarises the results obtained after the experiment.

![Adding more Convolution Units](https://i.ibb.co/m4CJzzW/Adding-more-Convolution-Units.png)

As you can see, the additional convolution layer also tends to overfit the model. The training accuracy seems to increase with the increment in epochs, but the same is not reflected in the testing set.

5.  **Increasing the feature maps**

In the previous experiment, you increased a convolution unit to extract more features. However, another method of extracting more features is by increasing the feature maps in the existing convolution blocks. Let’s understand how this approach impacts the performance of the model, in the upcoming video.

**VIDEO**

You can see that we have combined all the experiments along with the increase in the number of feature maps in each convolution block. The results are summarised in the graph given below.

![Increasing the Feature Maps](https://i.ibb.co/WPt2L64/Increasing-the-Feature-Maps.png)

The accuracy of the model has increased to 78.5% over the validation set. More importantly, the trend for both the training and the validation sets is the same. Therefore, we can conclude that this particular model does not suffer from overfitting. This has been by far the best model, in terms of both accuracy and managing other problems such as overfitting.

You have now come to the end of the session. The next segment will summarise your learnings from the session.