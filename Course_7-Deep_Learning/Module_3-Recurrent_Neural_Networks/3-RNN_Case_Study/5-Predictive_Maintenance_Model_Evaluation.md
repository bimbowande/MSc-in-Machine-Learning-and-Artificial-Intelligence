# Predictive Maintenance - Model Evaluation

Having learnt about the model building in the previous segment , let’s see how to train the LSTM model and also analyse the results on evaluation and test set.

**VIDEO**

The model training part is similar to what you saw in previous deep learning models which can be done by using Keras’s model.fit() method. To save the best models and incorporate the early stopping feature we use a parameter “callback” which facilitates the function calls at each epoch.

Value of the loss function is a good measure to check how the model is performing while training it. Our model shows good optimisation in the loss value as shown by the below graph.![Predictive Maintenance Loss Graph](https://i.ibb.co/bvpF26P/Predictive-Maintenance-Loss-Graph.png)

In our case, the loss function of training data as well as validation data gets down quite steeply before flattening out to indicate that the minima has reached. The best time to stop the training is when the training loss is going down but loss on testing data starts going up as shown in the above graph at epoch number 20.

The model evaluation part includes testing the model’s performance on validation data and most importantly test data. This performance can be model accuracy, precision/ recall/ F1 score or confusion matrix as well. Let’s check the confusion matrix as it is the most granular measure.

  
In the confusion matrix given below, x-axis is true labels whereas y-axis is predicted labels.

```python
[[67  1]  
 [ 1 24]]
```

It shows that out of the (67+1=68) label 0 actual data, 67 has been predicted correctly, whereas 24 label 1 actual data has been predicted correctly out of (24+1=25). We can derive other performance measure from this matrix as well such as accuracy which will be # of correctly predicted data points/ # of total data points. Putting values in the accuracy formula we get 91/93 = 0.9785 or 97.85% which is pretty decent for our use case.

As we have fewer data points in the test set, we can afford to directly plot the actual labels along with predicted labels to check the performance of our model which is given below.

![Predictive Maintenance Prediction Performance](https://i.ibb.co/NSdwwp0/Predictive-Maintenance-Prediction-Performance.png)

You can see that almost all of the data points have been correctly predicted except two points - one between 40-60 data points and another just after the 80th data point.

Now that you have gone through the whole coding demonstration, you can still do some experiments with the code. One such experiment can be replacing the LSTM model with GRU. Let’s explore some of these with the professor.

**VIDEO**

So, you saw that GRU has fewer parameters than LSTM, takes less time to train & inference and has almost similar results. When we say less time to train, the time measure will be time taken per epoch. As GRU might take more epochs to train, the overall time taken might be even more than LSTM.

You can make a few experiments on the values of hyperparameters and also keep a tab on how results and parameters change. You may use a simple RNN or GRU model and see how it performs.

In the next segment, you will get to know some real-life applications where RNN or its variation is used.