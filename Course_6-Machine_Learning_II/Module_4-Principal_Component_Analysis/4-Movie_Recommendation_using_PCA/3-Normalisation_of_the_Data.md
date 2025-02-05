# Normalisation of the Data

In this segment, you will learn to normalise the dataset which is an important step before building the PCA algorithm. It puts all the data points on a single scale. You can refer to the optional content on Summary Statistics to learn more about normalisation.

Let’s hear from Jaidev in the next video and perform the normalisation of the dataset.

**VIDEO**

Now, let’s go through the code one by one.

- In the previous sessions, you learnt about the following lines of code to perform the scaling step in a data frame.

```python
assembler = VectorAssembler(inputCols=[c for c in df.columns if c != 'title'], outputCol='features')
scaler = StandardScaler(inputCol='features', outputCol='normFeats', withMean=True)
df = assembler.transform(df)
scalerModel = scaler.fit(df)
df = scalerModel.transform(df)
```

So, here, the first column, i.e., ‘title’ needs to be removed from the scaling, as this column includes the titles of the movies.

- You learnt that after performing the step given above, you got an error message, which said that some column names contain a dot (‘.’) and, hence, they have to be rectified. So, you can apply the following lines of code to replace each dot with an underscore (‘_’).

```python
newCols = []

for c in df.columns:
	if "." in c:
        new_column = c.replace('.', '_')
            df = df.withColumnRenamed(c, new_column)
            newCols.append(new_column)
        else:
            newCols.append(c)
```

 Here, you have created a list object named ‘newCols’ and appended all the column names one by one in this list. So, now, if a column name contains a dot, then it will be replaced by an underscore, and the ‘newCol’ list will be appended with the updated column name. 

Now, if you perform the normalisation step, then there will not be any error and normalised columns will be stored in _‘normFeats’_. 

So, in this segment, you learnt to normalise the dataset. In the next segment, you will learn how to build a PCA model using this dataset.

#### Normalization

Qn: Match the following columns

| 1. VectorAssembler | I. It transforms a data set of vector rows, normalizing each feature to have a unit of standard deviation and/or zero mean.                                                                                          |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2. StandardScalar  | II. It is a transformer that combines a given list of columns into a single vector column. It is used to combine raw features and features generated by different feature transformers into a single feature vector. |

- 1 - I, 2 - II

- 1 - II, 2 - I

- None of the above

Ans: B. 