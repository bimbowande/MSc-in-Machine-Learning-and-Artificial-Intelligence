# Practice Questions

You are given an advertising data set that contains information about the money spent on advertisements (TV, radio and newspaper) and their general sales. Your task is to build a regression model that predicts the sales based on the money spent on different platforms for marketing. The first five rows of this data set are given here for your reference.

![Practice Questions](https://i.ibb.co/HhNT5Mc/Practice-Questions.png)

You can download the data set using the following [s3 link](https://advertising-dataset-ml.s3.amazonaws.com/Advertising.csv).

## **Data Set Sescription:**

'**TV**': Money spent on advertisements on TV

'**Radio**': Money spent on advertisements on radio

'**Newspaper**': Money spent on advertisements in newspaper

'**Sales**': General sales of the product

## **Points to Note:**

-   In order to carry out this regression task, you are required to use Spark ML's **[Random Forest Regressor](https://spark.apache.org/docs/latest/ml-classification-regression.html#random-forest-regression)** as used in the links given below.
-   Once the regression model is ready, you must use the MLlib's **[RegressionMetrics](https://spark.apache.org/docs/2.2.0/mllib-evaluation-metrics.html#regression-model-evaluation)**   
    function and calculate the evaluation metrics that are **rmse** and **r2 score.**
-   Use a single m4.large cluster, i.e., 1 master and 0 slave nodes.
-   While using the Random Forest Regressor, ensure that you use the **seed value as 42**. This is because the Random Forest algorithm might choose different bootstrapped samples for different seed values that would result in different values for the evaluation metrics.

An incomplete notebook has been provided in which you can fill in the blanks as per the comments provided and answer the questions given below. 

Download [Advertising Assignment Notebook](Advertising_Case_Study.ipynb)

**Note**: Since the execution of Random Forest is different on Python and Pyspark, solving the case study using Python may fetch you incorrect results. 

Here are the steps required to solve this case study: 

1.  Initialise the Spark session.
2.  Import the data set as a Spark dataframe.
3.  Check whether the data set contains any missing value. Impute the missing values in case it does.
4.  Create a single pipeline with the following stages: 
    1.  Merging of columns into a single vector (using Vector Assembler)
    2.  Creation of the Random Forest model using Spark ML's **[Random Forest Regressor](https://spark.apache.org/docs/latest/ml-classification-regression.html#random-forest-regression)  
        Note:** Use the default hyperparameters when creating the Random Forest Regressor
5.  Use the **RegressionMetrics** function to calculate the **rmse** and **r2 score.** The documentation regarding the usage of this function has been provided in the given [link](http://spark.apache.org/docs/2.2.0/mllib-evaluation-metrics.html#regression-model-evaluation).

#### Advertising Case Study

Qn: Which feature contains the maximum number of missing values?

- TV

- Radio

- Newspaper

- None of the above

Ans: D. *The given data set does not contain any missing values. Hence, we can move on to further data preparation steps as it is. The following code can be used to check for null values in this data set.*

```python
from pyspark.sql.functions import when, count, col, isnull

#### Check the number of null values for each variable

df.select([count(when(isnull(c), c)).alias(c) for c in df.columns]).show()
```

Qn: What is the feature importance for the feature 'TV'?

- 0.6121

- 0.5732

- 0.4743

- 0.4213

Ans: C. *Starting from creating the pipeline, you can use the following code to calculate the feature importances.*

```python
from pyspark.ml import Pipeline

pipeline = Pipeline(stages=[assembler, rf])

# Train model.  This also runs the indexer.
model = pipeline.fit(train)

# Make predictions.
predictions = model.transform(test)

rfModel = model.stages[1]
print(rfModel)  # summary only

# Feature Importance
rfModel.featureImportances
```

*Here, '0' refers to the first feature, which is 'TV', '1' refers to the second feature 'Radio' and '2' refers to the third feature, which is 'Newspaper'. Hence, the importance for TV is 0.4743*

Qn: Mark the correct code for creating the regression model.

- 
```python
#### Initialise the vector assembler as 'assembler'
from pyspark.ml.feature import VectorAssembler
assembler = VectorAssembler(inputCols = inputCols, outputCol = 'features')

#### Initialise the RandomForestRegressor as 'rf'
from pyspark.ml.regression import RandomForestRegressor
rf = RandomForestRegressor(labelCol="Sales", featuresCol="features", seed = 42)

#### Create the pipleing and input the stages
from pyspark.ml import Pipeline
pipeline = Pipeline(stages=[assembler, rf])
```

- 
```python
#### Initialise the vector assembler as 'assembler'
from pyspark.ml.feature import VectorAssembler
assembler = VectorAssembler(inputCols = inputCols, outputCol = 'features')

#### Initialise the RandomForestRegressor as 'rf'
from pyspark.ml.regression import RandomForestRegressor
rf = RandomForestRegressor(labelCol="Sales", featuresCol="features", seed = 42)

#### Create the pipleing and input the stages
from pyspark.ml import Pipeline
pipeline = Pipeline(stages=[rf, assembler])
```

- 
```python
#### Initialise the vector assembler as 'assembler'
from pyspark.ml.feature import VectorAssembler
assembler = VectorAssembler(inputCols = features, outputCol = 'inputCols ')

#### Initialise the RandomForestRegressor as 'rf'
from pyspark.ml.regression import RandomForestRegressor
rf = RandomForestRegressor(labelCol="Sales", featuresCol="features", seed = 42)

#### Create the pipleing and input the stages
from pyspark.ml import Pipeline
pipeline = Pipeline(stages=[assembler, rf])
```
- 
```python
#### Initialise the vector assembler as 'assembler'
from pyspark.ml.feature import VectorAssembler
assembler = VectorAssembler(inputCols = inputCols, outputCol = 'features')

#### Initialise the RandomForestRegressor as 'rf'
from pyspark.ml import RandomForestRegressor
rf = RandomForestRegressor(labelCol="Sales", featuresCol="features", seed = 42)

#### Create the pipleing and input the stages
from pyspark.ml import Pipeline
pipeline = Pipeline(stages=[assembler, rf])
```

Ans: A.

Qn: Mark the correct option for the RMSE and r2 score on the test set?

- 3 < RMSE < 4  ;  0.7 < R2 score < 0.8

- 2 < RMSE < 3  ;  0.7 < R2 score < 0.8

- 3 < RMSE < 4  ;  0.8 < R2 score < 0.9

- 2 < RMSE < 3  ;  0.8 < R2 score < 0.9

Ans: D. *You can execute the following code to get the metrics.*

```python
from pyspark.mllib.evaluation import RegressionMetrics

#important: need to cast to float type, and order by prediction, else it won't work:
preds_and_labels = predictions.select(['prediction','Sales']).withColumn('label', F.col('Sales').cast(FloatType())).orderBy('prediction')

#select only prediction and label columns
preds_and_labels = preds_and_labels.select(['prediction','label'])

metrics = RegressionMetrics(preds_and_labels.rdd.map(tuple))

# Squared Error
print("MSE = %s" % metrics.meanSquaredError)
print("RMSE = %s" % metrics.rootMeanSquaredError)

# R-squared
print("R-squared = %s" % metrics.r2)
```

*Using this code, the R2 score will come to approximately 0.87  and the RMSE will come to approximately 2.5.*

#### Spark Optimization

Qn: Which of the following optimisation techniques involved the creation of a DSI table to save the data indexes generated in all sampling times? 

- Vertical Data Partitioning

- Data-Multiplexing Method

- Static Data Allocation

- Task-Parallel Optimization

Ans: B. *In the Data-Multiplexing Method, we create a DSI table to save the data indexes generated in all sampling times. You can explore the working of the data-multiplexing method in the following [link](https://arxiv.org/pdf/1810.07748.pdf).*
