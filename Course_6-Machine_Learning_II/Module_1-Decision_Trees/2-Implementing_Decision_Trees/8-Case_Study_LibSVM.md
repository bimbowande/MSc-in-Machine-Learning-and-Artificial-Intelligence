# Case Study - LibSVM

In this segment, let’s learn how Decision Trees are implemented in Spark with the help of a case study. We will be using a LibSVM dataset for this case study which is a regression task. LibSVM dataset is used to represent data that contains numerous missing values in a compact form. Now, let’s take a look at the following video where Sajan will explain to you about the dataset and the problem at hand.

**VIDEO**

You can access the dataset here:

Download Dataset

Use this notebook to code:

Download Notebook


Once you have downloaded the dataset, you can save your dataset in an S3 bucket so that you can access it while using the EMR cluster. Let’s take a look at the next video to understand how to create a Regression Decision Tree.

**VIDEO**

You can use the following code to create a Decision Tree:

```python
# Import the libraries required for loading data as follows:
from pyspark.mllib.util import MLUtils

# Load the data from S3 bucket
data = MLUtils.loadLibSVMFile(sc, 's3a://decisiontreespark/libsvm_data.txt')

# View the data and its count as follows:
data.take(1)
data.count()

# Divide the data into training and test data as follows:
(trainingData, testData) = data.randomSplit([0.7,0.3])

# Load the libraries required for Decision Trees as follows:
from pyspark.mllib.tree import DecisionTree, DecisionTreeModel

# Create a Decision Tree Regressor as follows:
model=DecisionTree.trainRegressor(trainingData,categoricalFeaturesInfo={},impurity="variance”,maxDepth=2)

# Run the model and check the following predictions made by the model:
predictions = model.predict(testData.map(lambda x: x.features))

# You can compare the predictions with the actual result by mapping them as follows:
labelAndPreds = testData.map(lambda x: x.label).zip(predictions)
```

So far, you created a Regression Decision Tree and compared the predictions with the actual output labels. Now, you will be calculating the mean square error (MSE). The formula for MSE is as follows:

$$\dfrac{1}{N}\sum^N_{i=1}(Y−\hat{Y})^2$$

MSE, in simple terms, is the square of the difference between the actual and predicted values divided by the number of observations. You can calculate as shown in the video.

**VIDEO**

Use the following code to calculate MSE value and visualise the tree:

```python
# Calculate the MSE value as follows:
mse_value= labelAndPreds.map(lambda x: (x[0]-x[1])*(x[0]-x[1])).sum()/ float(testData.count())
mse_value

# Visualise the tree as follows:
print(model.toDebugString())
```

#### Depth of Tree

Qn: Does the depth of the tree increase as you increase the parameter 'max_depth'?

- No, it doesn't, as the number of data points is not sufficient to get significant information gain to split further. 

- Yes, the depth of the tree increases to 2.

Ans: A.

So far, you have implemented a regression problem. In the upcoming segments, you will be solving classification tree case-studies.