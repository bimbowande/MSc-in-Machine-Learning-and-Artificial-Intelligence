# Chicago Crime Case Study - V

The next part of the cleaning process involves dealing with null values. You should always check for null values in each attribute of the dataset, and then, based on the scenario, take an appropriate step to deal with it. Let's take a look at the approach that can be followed here.

**VIDEO**

As you can see, the data set had a maximum of 37,083 null values. It is a tiny proportion of the dataset; hence, the corresponding rows can be dropped. However, you can run an additional check to determine if the null values are associated with any particular class of the target variable. In that case, removing the null values will not be the ideal step.

After removing all the null values, the next step is to check whether the columns are in the correct format. If you remember, all the columns were loaded as ‘string’ when the data was imported in the Jupyter Notebook. Therefore, in the upcoming video, Sajan will use the cast() function to transform them into the required format.

**VIDEO**

You would have noticed that all the continuous variables have been converted into the appropriate data type. The target variable ‘FBI code’ is left as string-type because it is a categorical variable. Now, you have a set of both categorical and continuous variables in the dataframe to build the model. However, before proceeding, let's try to visualise the target variable FBI code and take a look at its distribution.

**VIDEO**

In this video, we explored the target variable  FBI code and visualised the patterns in it. And, we have extracted all the features and transformed them into the correct data type. In the next segment, Sajan will label all the categorical features using the Spark pipeline.