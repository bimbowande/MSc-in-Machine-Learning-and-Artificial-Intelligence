# Case Study - Credit Card Fraud Detection - I

So far, you have worked on a Regression Problem. Let’s now learn how a Classification Decision Tree works in Spark. As mentioned at the beginning of this session, Decision Trees are actively used in the financial sector. You will be given a classification problem to predict whether a credit card transaction is a fraud or not. Sajan will explain to you the dataset in the next video.

**VIDEO**

You will be dealing with the following features:

-   type
-   amount
-   nameOrig
-   oldbalanceOrg
-   newbalanceOrig
-   nameDest
-   oldbalanceDest
-   newbalanceDest
-   isFraud
-   isFlaggedFraud

All these features are self-explanatory and easy to understand by their names themselves. In the video given above, Sajan has already explained the dataset to you. Now, try to load the data and explore it on your own before moving on to the next video, where each step for the same is explained in detail.

**VIDEO**

You can use the following code to implement it yourself:

```python
# Load data from CSV file in S3 as follows:
data=sqlContext.read.csv('s3a://decisiontreespark/fraud_detection_data.csv',header=True,inferSchema=True)

# View and select the required columns as follows:
data.columns
sel_cols=['step','type','amount','oldbalanceOrg','newbalanceOrig','oldbalanceDest','newbalanceDest', 'isFraud', 'isFlaggedFraud']

# Create a dataframe consisting of selected columns as follows:
df = data.select(sel_cols)

# View and group the data by “type” as follows:
df.select("type").show(3)
df.groupby("type").count().show()

# Explore the number of fraud cases as follows:
df.groupby("isFraud").count().show()
```

Note: The dataset is loaded into a public S3 bucket and can be directly read using the command in the code snippet shown above.

So far, you have understood the data and selected the required columns. Now, before you create a Decision Tree, you need to prepare the data in the format which sklearn can understand. The first step is performed by using a String Indexer. A String Indexer converts the string values into numerical indexes. Let’s take a look at the next video to understand how it is done.

**VIDEO**

Take a look at the code given below and implement it yourself:

```python
# Import required libraries for string indexer:
from pyspark.ml.feature import StringIndexer

# Apply function for string indexer:
si = StringIndexer(inputCol="type", outputCol="type_index")

# Apply required transformation on dataframe:
df_indexed = si.fit(df).transform(df)

# You can view the new df as follows:
df_indexed.show(5)
```

So, we have converted the column ‘type’ to numerical. In the next segment, you will further encode and create vectors of these values.