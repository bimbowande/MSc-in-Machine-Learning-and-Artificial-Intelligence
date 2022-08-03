# Chicago Crime Case Study - III

So far, you have learnt to extract the useful data from the dataset. In this session, you will learn to conduct visual analysis and gather information primarily on the extracted attributes using Matplotlib that was installed earlier on the SparkContext.

In the next video, Sajan will conduct the necessary statistical analysis on the extracted data for the ‘hour’ column to visualise the patterns in it.

**VIDEO**

From the plot, we inferred that the highest number of crimes occur during the 19th hour, which is around 7 pm. If you remember correctly, we extracted one more attribute that was the ‘day_of_week’. Similar to the statistical analysis on ‘hour’ attribute, we will now conduct analysis on the ‘day_of_week’ attribute to find some patterns in the video below.

**VIDEO**

You would have noticed that all the continuous variables have been converted into the appropriate data type. Now, you have a set of both categorical and continuous variables in the dataframe to build the model. However, before we proceed, let's try to visualise the target variable FBI code and take a look at its distribution.

**VIDEO**

Using the bar plot, we found that theft and battery are the two widely committed crimes, followed by criminal damage, and so on. You also understood that street, residence, apartment and sidewalk are the four locations in which most of the crimes are committed.

#### Data Exploration

Qn: Which of the following locations have the highest crime rates?

- Apartments

- Residences

- Sidewalks

- Street

Ans: D. *Using the groupby function, you can calculate the frequency of crimes in each location. Once you have the count, you can order them in descending order. On performing this operation, it is found that the location 'Street' has the highest count of crimes.*

```python
location_df = df.groupBy("Location Description").count().orderBy("count", ascending = False).toPandas()
location_df.head()
```

Qn: Which of the following statements are true? \[More than one option may be correct]

- There has been a decrease in crime activity over the last five years.

- There has been an increase in crime activity over the last five years.

- The decrease in crime activity may be the reason for the decrease in the number of arrests.

- The increase in crime activity may be the reason for the increase in the number of arrests.

Ans: A & C.

- *By performing a groupby operation over the year as shown below, you will notice that there is a steady decline in the crimes in the last five years.  The following code can be used to estimate the number of crimes each year.*

```python
year_df = df.groupBy("Year").count().orderBy("count", ascending = False).toPandas()
year_df.head()
```

- *By performing a groupby operation over the year, you will notice that there is a steady decline in the number of arrests in the last five years. This maybe attributed to the fact that the crimes have been on a decline over the last five years. The following code can be used to estimate the number of arrests each year.*

```python
import pyspark.sql.functions as F
arrest_df = df.filter(F.col('Arrest') == 'True')

arrest_year_df = arrest_df.groupBy("Year").count().orderBy("count", ascending = False).toPandas()

arrest_year_df.head()
```

In the next segment, we will apply basic EDA to get further insights, and then try to answer other questions on the dataset.