# PCA Model - II

In the previous segment, you saw that after plotting the loading vectors of the top five variance tags, the tags ‘colourful’ and ‘horrible’ seemed to be highly correlated. 

Now, let’s plot the scatter plot of these two tags and understand whether they are actually correlated or not.

**VIDEO**

Let’s extract the two tags ‘colourful’ and ‘horrible’ from the original dataset. 

```python
x = df.select('colourful').rdd
y = df.select('horrible').rdd
```

Now, let’s plot the scatter plot of these two variables and check the correlation between them.  
 

![](https://images.upgrad.com/3d2e02d7-0c81-4814-a6f7-7918a598953e-img5.PNG)

In the plot given above, you can see that as the value of the tag ‘colourful’ increases, the value of the other tag ‘horrible’ decreases, which should be true, as a particular movie cannot be colourful as well as horrible simultaneously.

So, when you plotted the loading vectors on the scatter plot of the two PCs,  both the loading vectors were in the same direction for both the tags.

Do you think you made a mistake here?

Well, yes. You did make a mistake by plotting in 2 dimensions, i.e, using only the two principal components. Now, let’s take a look at the variance explained by the different principal components.

**VIDEO**

In the video, you have seen how much percentage of variance is explained by the two principal components. Let’s understand this better. You already have the projections of all the data points of the two principal components in ‘matrix_reduced’. Now, let’s convert this matrix into a numpy matrix in the form of an array using the following line of code.

```python
reduced_rows = matrix_reduced.rows.map(np.array).collect()
reduced_matrix = np.array(reduced_rows)
reduced_matrix
```

The first line of code creates a numpy array for every row in matrix_reduced by using the map function. Hence, reduced_rows is an RDD of numpy arrays and in order to convert reduced_rows to a numpy array we execute the second line of code.

So, to calculate the percentage of variance explained by the two principal components, you need to write the following lines of code.

```python
reduced_matrix.var(axis=0).sum() / (len(df.columns) - 3) * 100
```

Here, you first need to calculate the variance of the 2 PCs individually and then apply sum on it. Once you get the total variance of the two principal components, you need to divide it with the sum of the variance in all the PCs, which will be equal to the total number of tags/ features in the dataset because the variance of the normalized tags/ features will be 1. However, you need to subtract 3 from the df.columns because you have three extra columns in the dataset apart from the numerical tags columns, which are as follows:

-   title: Corresponding to the movies titles
-   Column corresponding to the assembled features
-   Column corresponding to the normalized features

You see that you get only 16% of the variance described by the two PCs, which is very less for any analysis using principal components.

When you select 100 PCs instead of two PCs, then you get around 67% variance. But when you select 500 PCs, then the percentage of variance is approximately 91%.

#### PCA

Qn: Can you explain the original features of the dataset after PCA was performed on them?

Ans: *The original features can be visualised in terms of their incremental direction on the principal component scatter plot, which is also called loading vectors*

#### Loading vectors

Qn: When you draw the loading vectors of the ‘colourful’ and ‘horrible’ tags on the scatter plots of the two PCs, you get the same direction in which the value of these two tags increases. This depicts that both the tags are highly correlated.

![PCA Loading Vectors Question](https://i.ibb.co/zJZSqsv/PCA-Loading-Vectors-Qn.png)

However, when you plot the scatter plot of these tags, then you see that if one tag increases, then another decrease. Now, what could be the possible reason for this discrepancy?

- The scatter plot that you draw between the data points of the tags ‘colourful’ and ‘horrible’ are not properly normalized data points. Hence, it depicts the wrong interpretation that if one tag increases, then another decrease.

- The variance described by the two principal components is very less, i.e., about 16% only. So, when you plot the loading vectors on these PCs, you get the discrepancy.

- Both A and B

- None of the above

Ans: B. *The variance of about 16% cannot give correct results. Hence, you should have more number of principal components to depict the loading vectors.*
