# Chicago Crime Case Study - IV

In the previous segment, we used various data visualisation techniques to get insights from the derived data using plotting libraries. This helped us understand some of the variables from the available pool in the data set. Now, in this segment, Sajan will apply basic EDA on other variables to answer some basic questions such as how many arrests were made or how many crimes were domestic.

Let’s see how to do this in the next video.

**VIDEO**

#### StringIndex

Qn: Fill in the blanks for inputCol and outputCol:

```python
# Building a function for encoding all the categorical variables
for categoricalCol in categorical_features:
    stringIndexer=StringIndexer(inputCol=_______,outputCol=__________+'Index')
```
   

- categoricalCol, categoricalCol

- categoricalCol, categorical_features

- categorical_features, categorical_features

- categorical_features, categoricalCol

Ans: A. *For every categorical column (categoricalCol in the for loop) in the list categorical_features, you first need to StringIndex it i.e, convert to a number and then one hot encode it.*

#### OneHotEncoderEstimator

Qn: Fill in the blanks inputCols and outputCols in 

```python
for categoricalCol in categorical_features:
    stringIndexer=StringIndexer(inputCol=categoricalCol,outputCol=categoricalCol+'Index')
    encoder=OneHotEncoderEstimator(inputCols=________________, outputCols= ____________)
```

Remember that you need to differentiate between the new and original columns.

- stringIndexer.getOutputCol(), categoricalCol+"Class"

- categoricalCol+'Index', categoricalCol+"ClassVec"

- stringIndexer.getOutputCol(), categoricalCol+"ClassVec"

- categoricalCol+'Index', categoricalCol

Ans: B & C. *Input to OneHotEncoderEstimator is the output column of stringIndexer which is stringIndexer.getOutputCol() = categoricalCol+'Index'. Output can be categoricalCol+"ClassVec" or categoricalCol+"Class" that differentiates it from the original variable.*

#### Functions

Qn: What happens in 

```python
stages+=[stringIndexer,encoder]
```

in the last line of the code

```python
# Building a function for encoding all the categorical variables
for categoricalCol in categorical_features:
    stringIndexer=StringIndexer(inputCol=categoricalCol, outputCol=categoricalCol+'Index')
    encoder=OneHotEncoderEstimator(inputCols=[stringIndexer.getOutputCol()],outputCols=\
                                   [categoricalCol+"ClassVec"])
    stages+=[stringIndexer,encoder]
```

Choose an appropriate answer.

- It adds the combined stringIndexer and the combined encoder for all the categorical columns in categoricalCol at once into the list stages. In other words, for 5 categorical variables, only 2 elements are added to stages: 'stringIndexer' and 'encoder'.

- It adds the stringIndexer and the encoder for each categorical column in categoricalCol after every loop into the list stages. In other words, for 5 categorical variables, 10 elements are added to stages: 'stringIndexer' and 'encoder' for each categorical column in categoricalCol

Ans: B.

In this video, Sajan helped you with the steps to apply conditional formatting on different columns to analyse their distribution. You can use these steps to explore the other columns as well. Now, let’s proceed with the next steps of model development.

You would have noticed that even after dropping some columns, you are still left with a large number of columns to conduct the analysis. So, in the next video, Sajan selects some other columns to drop in order to reduce the size of the training data. 

**VIDEO**

The following attributes were dropped from the dataset:

-   ID Columns: ‘_c0’, ‘ID’ and ‘Case Number’
    
-   Columns with a lot of text: ‘Block’ and ‘Description’
    
-   Columns with unnecessary information: ‘Updated on’ and ‘Location’
    

As mentioned by Sajan, you should check the number of unique values in each column to identify those with a huge count of distinct values after the steps given above. The random forest model cannot handle the categorical variables directly and requires you to encode the categorical values using the one-hot encoding (in this case). This results in the addition of a new column for each label in the column. Therefore, to restrict the number of columns in the process of model training, Sajan will identify and drop such categorical columns; watch the next video to understand this.

**VIDEO**

By now, you must have understood that many categorical columns such as ‘IUCR’, ‘Beat’, ‘Ward’ and ‘Community area’ contain a lot of unique values and need to be dropped because if we include them, many new columns will have to be created. 

In the next segment, we will deal with irregularities in the dataset like null values and misalignments of the column data type.