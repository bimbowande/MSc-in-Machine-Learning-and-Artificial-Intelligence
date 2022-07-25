# Case Study - Credit Card Fraud Detection - II

Until now you converted the string values into numerical values; however, you might still face an issue, as the indexes assigned by the string indexer can be interpreted as values by the Decision Tree Classifier, which may lead to an incorrect result. Let's now understand the two most common ways of preparing categorical variables: dummy variables/one-hot encoding.  
   
You have already created dummy variables (for replacing categorical variables) in models, such as linear and logistic regression. Note that creating dummy variables is also called one-hot encoding. Take a look at the video given below to understand how one-hot encoder works.

**VIDEO**

Refer to the code given below:

```python
# Import required libraries for one-hot encoder as follows:
from pyspark.ml.feature import OneHotEncoder

# Apply function for one-hot encoder as follows:
encoder = OneHotEncoder(inputCols=["type_index"], outputCols=["type_encoded"])

# Fit and transform your dataframe with the encoded data as follows::
df_enc = encoder.fit(df_indexed)
df_encoded = df_enc.transform(df_indexed)

# View the new df as follows:
df_encoded.show(3)
```

So now, you converted the string values to indexes and assigned them dummy variables. The next step is to create a vector of all the columns/features that you will use to make a Decision Tree. This can be done by using Vector Assembler. You have already assigned the columns required to the variable names “features”. Now, you are going to create a vector for the same as shown in the following video.

**VIDEO**

Take a look at the code given below and implement it yourself for better understanding:

```python
# Import required libraries for vector assembler
from pyspark.ml.feature import VectorAssembler

# Select the columns required as follows:
selected_cols=['step','amount','oldbalanceOrg','newbalanceOrig','oldbalanceDest','newbalanceDest','type_encoded']

# Run the vector assembler function and save it into a new dataframe as follows:
va = VectorAssembler(inputCols=selected_cols,outputCol="features")
df_vectors = va.transform(df_encoded)
```

So far, you have prepared the data for the Decision Tree Classifier. In the next segment, you will be creating the Decision Tree and visualising it.