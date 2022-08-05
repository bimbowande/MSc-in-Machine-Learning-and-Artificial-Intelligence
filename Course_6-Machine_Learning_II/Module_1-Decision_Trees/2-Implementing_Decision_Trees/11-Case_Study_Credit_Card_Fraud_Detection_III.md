# Case Study - Credit Card Fraud Detection-III

The data is now prepared in the proper format as required by the pyspark ml library. Now, you can split the data into training and testing data, and create a Decision Tree from it, as you have already done in the previous segments. In the next video, Sajan will show you how to do the same.

**VIDEO**

#### Credit Card Fraud Detection Model

Qn: Do you think accuracy would be a good measure to look at the performance of the model?

Ans: *In the case of Fraud Detection, accuracy would serve the purpose as the data is imbalanced and the accuracy will always be high.*

Qn: How will increasing recall help in case of the Fraud Detection problem?

Ans: *Recall states that out of all the actual frauds, how many is the model able to capture. Increasing the recall would mean that we are able to capture most of the fraud transactions and hence able to prevent fraud transactions to happen in future and hence reduce the losses due to fraud transactions.*

*At the same time, as the recall value increases, you'll see that the precision value falls. This means that you are flagging a lot of transactions as fraud and very few of them are actually turning out to be fraud. This is dangerous because you are halting a lot of transactions and verifying them before proceeding. This would incur more cost because you would call the customer to verify if the transaction is done by the customer or not and at the same time deteriorate the customer experience.*

*Hence, a healthy balance between recall and precision is required.*

Refer to the following code:

```python
# Divide the data into test and train data as follows:
(trainingData, testData) = df_vectors.randomSplit([0.7,0.3])

# Run the decision tree classifier function as follows:
from pyspark.ml.classification import DecisionTreeClassifier

dt = DecisionTreeClassifier(featuresCol="features", labelCol="isFraud")

# Fit the training data
model = dt.fit(trainingData)

# Transform the test data as follows:
predictions = model.transform(testData)

# View the resultant dataframe to analyse better as follows:
predictions.select("prediction", "isFraud", "features").show(5)

# Load the required libraries as follows:
from pyspark.ml.evaluation import MulticlassClassificationEvaluator

# Run the evaluator function as follows:
evaluator=MulticlassClassificationEvaluator(labelCol="isFraud",predictionCol="prediction",metricName="accuracy")

# View the accuracy as follows:
accuracy = evaluator.evaluate(predictions)
```

Let’s now analyse the confusion matrix for this Decision Tree.

**VIDEO**

Use the following code to understand the confusion matrix:

```python
# Load the required libraries:
from pyspark.sql.types import FloatType
from pyspark.mllib.evaluation import MulticlassMetrics
import pyspark.sql.functions as F

# Important: need to cast to float type, and order by prediction, else it won't work:

preds_and_labels = predictions.select(['prediction','isFraud']).withColumn('label', F.col('isFraud').cast(FloatType())).orderBy('prediction')

# Select only prediction and label columns
preds_and_labels = preds_and_labels.select(['prediction','label'])

metrics = MulticlassMetrics(preds_and_labels.rdd.map(tuple))

print(metrics.confusionMatrix().toArray())
```

You may see that the precision and recall are coming to the same value which seems to be different from what you get from the confusion matrix.  To get the precision, recall and F-measure for the different classes 0 and 1, implement the following:

```python
# Precision for label 0
precision0 = metrics.precision(0)

# Recall for label 0
recall0 = metrics.recall(0)

# Precision for label 1
precision1 = metrics.precision(1)

# Recall for label 1
recall1 = metrics.recall(1)

# F1 score for label 0
f1Score0 = metrics.fMeasure(0.0, beta = 1.0)

# F1 score for label 1
f1Score1 = metrics.fMeasure(1.0, beta = 1.0)
```

This will give you the values in accordance with the confusion matrix.

## Assignment:

Sajan has already implemented the code for credit card fraud detection in the videos given above. The functions required for processing data, i.e., String Indexer, Vector Assembler and One-Hot Encoder can be implemented in a single step using a pipeline. In the previous module, you learnt about creating the pipeline. Download the notebook for pipeline implementation given below: 

Download [Pipeline Notebook](Pipeline_Implementation_Decision_Trees.ipynb)

Try implementing the case study given above on your own before watching the solution video and answer the following questions:

#### Pipeline

State whether the following statement is true or false.  
The accuracy improves if you implement code using a pipeline.

True

False

Ans: B. *The implementation of code using a pipeline is the same as the code itself, only the code becomes compact in size.*

Qn: Which of the following statements is true?

- String indexer converts the string values to numerical indexes.

- The one-hot encoder is used to convert the column of category indices to a column of binary vectors.

- Vector indexer creates vectors of available data.

- A pipeline is used to increase simplicity and reduce the time of writing the code.

Ans: All of the above. *String indexer is used to converting the available string values to integer values. The one-hot encoder converts index values to binary vectors. Vector indexer converts data to indexes. Using pipeline makes the code short and easy to interpret.*

You have so far implemented case studies in both Python and Spark. In the upcoming segment, you will be learning how to optimise Decision Trees in Spark.