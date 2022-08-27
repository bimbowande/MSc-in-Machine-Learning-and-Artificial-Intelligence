# EDA on Data Set

In the previous segment, you explored the features of the given data set. The next step of the model building process is to perform EDA on the data set. In the upcoming video, Sajan will perform EDA on the data set.

**VIDEO**

In order to read the data, you can either add the data into your personal s3 bucket and get the link, as done by Sajan in the video above, or add the data file into your instance. You can find the code snippet for the same provided below.

```python
df = spark.read.csv('music_data.csv', header=True, inferSchema=True)
```

**Note**: The path to your S3 may be different from the one mentioned above. Remember to add the correct path in your code.

Now, after loading the data, you only require the ‘artist_name’ and ‘plays’ columns in order to perform clustering on artists based on their popularity. So, you can select the required columns using the following command:

```python
df_artist = df.select(['artist_name', 'plays'])
```

As explained in the video, one artist can be played by different users. So, in order to find the number of times that an artist’s songs were played by users, you need to calculate the sum for different users. For this, you can use the following command:

```python
artist_aggr = df_artist.groupby('artist_name').sum()
```

Note that the new DataFrame formed by the step mentioned above contains fewer columns than the previous DataFrame due to the aggregation of features.

After finding the total sum for different users, you need to use a vector assembler in order to transform the columns into vectors because the model inputs in PySpark consist of vectors. You can use the following commands to implement a vector assembler:

```python
assembler = VectorAssembler(inputCols=['plays_sum'],outputCol='features')
model_data = assembler.transform(artist_data)
```
Now, you can use ‘model_data’ as the final DataFrame for model building.

#### EDA on Data Set

Qn: What is the use of the following code snippet?

```python
artist_aggr = df_artist.groupby('artist_name').sum()
```

- It is used to find the total number of songs played by a user.

- It is used to find the total number of times an artist’s songs have been played.

- It is used to find the total number of artists present in the data set.

- None of the above

Ans: B. *Correct. .groupby().sum() calculates the total number of times an artist has been played by all the users.*
