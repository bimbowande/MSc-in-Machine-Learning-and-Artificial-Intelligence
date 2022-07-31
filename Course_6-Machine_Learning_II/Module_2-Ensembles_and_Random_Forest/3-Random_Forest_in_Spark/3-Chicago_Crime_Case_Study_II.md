# Chicago Crime Case Study - II

So far, you have gone through the data set and its attributes that will be used for predicting the FBI code. In this session, we will first set up the Spark environment for successful code execution and then move on to the data exploration and cleaning.

In the following video, Sajan will set up the Spark environment and create the SparkContext.

**VIDEO**

In the video, you saw that we first configured the Spark environment according to the requirement. Then, we created the SparkContext using the getOrCreate() function. Further, we installed specific versions of the external packages such as Pandas and Matplotlib that are not coupled with the existing SparkContext.

#### Spark Context

Qn: Which of the following functions of SparkContext will you use to get a spark context if it is already present or create a new one if none is created?

- `getOrCreate()`

- `SparkContext()`

- `longAccumulator`

- `None of the above` 

Ans: A. *This function gets the existing SparkContext if it is present or creates a new one in another case.*

Now that we have set up the environment, let's move on to loading and viewing the data set. In the next video, Sajan will proceed with understanding the data further after loading it in Spark.

**VIDEO**

Now that the data set is loaded in the Spark environment, you can use the printSchema() function to view the entire schema of this dataset. Then, you must change the type of the column Date to the timestamp format, which is the desired 24-hour clock format. This will be used further for analysing the data and finding patterns.

Let’s see how to transform the variable in the next video.

**VIDEO**

Now that the date has been converted to the desired timestamp format, it becomes feasible to extract the hour from the data. One of the first steps when working with big data is to clean the given data to include only the relevant information. It makes the entire process simple and effective, as unwanted details will not be loaded in the Spark memory. Therefore, you must start by dropping the columns that are either not relevant to the final model or capture similar characteristics (correlated). 

In the upcoming video, Sajan will extract the hour and other required attributes while dropping the unnecessary ones.

**VIDEO**

In the video, we have extracted the necessary data from the desired columns. Now, we can drop ‘Data’ and ‘Data_Time’ as they are no longer useful for us. This also helps to reduce the processing overhead. In the next segment, you will perform visualisation statistical analysis on variables to get data insights.