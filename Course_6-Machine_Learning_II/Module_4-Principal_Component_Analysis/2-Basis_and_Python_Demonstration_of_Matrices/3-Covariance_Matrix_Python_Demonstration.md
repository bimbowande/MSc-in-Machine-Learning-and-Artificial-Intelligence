# Covariance Matrix Python Demonstration

In the previous segment, you learnt about the Python demonstration of vectors. In this segment, you will understand the covariance matrix and its related aspects in Python.

Refer to the following dataset, which consists of three columns: Gender, Height and Weight. 

Download [Gender dataset](hwg.csv)

Now, let’s hear Jaidev in the next video and understand the concept of covariance using Python codes.

**VIDEO**

The key points from the video are summarised below.  
 

Once you load the data into a ‘df’ data frame, you need to plot a scatter plot for the height and weight of each gender using different colours. You can use the following code to plot gender-wise scatter plots.

```python
fig, ax = plt.subplots(figsize=(8, 6))
df['genc'] = df['Gender'] == 'Male'
df.plot.scatter('Height', 'Weight', c=df['genc'].astype(int), ax=ax, cmap= plt.cm.viridis)
```

In the code snippet above, a new column df[‘genc’] has been created from the column ‘Gender’, where gender equals to ‘Male’.  
This new column has been used to differentiate the colours of the scatter plots between ‘Male’ and ‘Female’ in the plot.scatter() method.

You can refer to the following link to get an idea about the colouring of the scatter plots.  
[Colouring the scatter plot](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.scatter.html)

  
So, you get the following scatter plot:

![Scatter Plot Height vs Weight](https://i.ibb.co/4Td4YKR/Scatter-Plot-Height-vs-Weight.png)

You can see that they vary linearly with each other.  
 

The histogram of ‘Height’ and ‘Weight’ is plotted below. 

```python
fig, ax = plt.subplots(figsize=(8, 6))
df['Height'].hist(bins=50, ax=ax, alpha=0.5, label='Height')
df['Weight'].hist(bins=50, ax=ax, alpha=0.5, label='Weight')
plt.legend()
```

![Hist Plot Height vs Weight](https://i.ibb.co/9GgxR77/Hist-Plot-Height-vs-Weight.png)

Here, you can see that the spread of height around its mean is less (in red) than the spread of weight (in blue) around its mean. 

In the next part, Jaidev calculated the covariance matrix between the height and weight using a predefined function in Python:

```python
np.cov(df['Height'], df['Weight'])
```

When you run the code given above, you get the following covariance matrix.

![Covariance Height vs Weight](https://i.ibb.co/MDDmLFQ/Covariance-Height-vs-Weight.png)

Here, you can see the non-diagonal entries are the same, which means that the covariance of height with respect to weight is the same as the covariance of weight with respect to height.

Also, the diagonal entries are the variances of the weight and height. In the histogram plot, you saw that the variance of height is less than the variance of weight.

So, in the case above, you saw a fairly high covariance, which is around 114.24. Now, let’s examine another scenario where you have a low covariance. 

**VIDEO**

Notes:

-   In the above video at 0:42, the correct statement is "As height grows, the weight actually decreases".
-   Also, the correct statement from 3:22 to 3:26 should be "-3 to +3 on both the axes".

In this video, Jaidev mentioned an important statement, which is as follows:

"If the value of covariance is high, then there is a high tendency that one variable is linearly associated with the other variable", which means:

-   If there is a high positive covariance, then there is a high linear association between the two variables, and if one variable increases, then the other will also increase.
-   Similarly, if there is a high negative covariance, then there is a high linear association between the two variables. But in this case, if one variable increases, then the other will decrease.

In the previous video, you were introduced to a high positive covariance scenario.

Now, to demonstrate a low covariance scenario, Jaidev did not take a different data set. He simply created a data set by rotating all the data points (or data points vectors: yellow dots) corresponding to 'Male' by 90 degrees counterclockwise and created a different new data set, whose gender-wise (female dots in blue and male dots in yellow) scatter plot looked similar to the one given below.

![Scatter Plot Male vs Female](https://i.ibb.co/nmf8g42/Scatter-Plot-Male-vs-Female.png)

Here, you can see the male data points (red dots) are rotated 90 degrees counterclockwise as compared to the previous scatter plot (yellow dots).

Now, let’s understand how Jaidev has rotated all the height and weight data points 90 degrees counterclockwise, with the help of an example. 

Suppose you have a vector ‘v’ and a matrix ‘M’ as shown below:

v=[−32],  M=[103−1]

Now, when you multiply ‘M’ with ‘v,’ you get the following vector:

Mv=[−3−11]

Do you know what happens when you multiply a matrix with a vector?

When you multiply a matrix with a vector, it not only rotates that particular vector but also scales it up. This matrix is called the **‘transformation matrix’.**

Similarly, when you want to rotate a particular vector by an angle of θ (in radian) without scaling it up, you can multiply that vector with the following generalised transformation matrix:

![Transformation Matrix](https://i.ibb.co/Wxhzh3x/Transformation-Matrix.png)

#### Rotation of a vector

Qn: Suppose you want to rotate a vector ‘v1’ by an angle of 180 degrees. What will be the rotation matrix?

- $R=\begin{bmatrix}1&0\\0&1\end{bmatrix}$

- $R=\begin{bmatrix}-1&0\\0&-1\end{bmatrix}$

- $R=\begin{bmatrix}0&-1\\1&0\end{bmatrix}$

- $R=\begin{bmatrix}0&1\\-1&0\end{bmatrix}$

Ans: B. *The cos(180 degrees) is equal to -1 and sin(180 degrees) is equal to zero.*

#### Vectors

Qn: What will be the transformed vector ‘$t$’ when you rotate the vector ‘$v_1$’ by an angle of 180 degrees? $v_1=\begin{bmatrix}1\\1\end{bmatrix}$

- $t=\begin{bmatrix}1\\1\end{bmatrix}$

- $t=\begin{bmatrix}-1\\1\end{bmatrix}$

- $t=\begin{bmatrix}-1\\-1\end{bmatrix}$

- $t=\begin{bmatrix}1\\-1\end{bmatrix}$

Ans: C. *This option is correct, as the vector is obtained from the 180 degrees transformation of the vector ‘$v_1$'.*

The codes that you learnt in the video are summarised below.

First, you need to create a transformation matrix to transform a particular vector by an angle θ (in radian).

```python
def get_rotation_matrix(theta):  # in RADIANS!
    return np.array([[np.cos(theta), - np.sin(theta)],
                     [np.sin(theta), np.cos(theta)]])
```
Now, before rotating the data for analysis, you can normalize the data so that all the analysis is performed on the origin. Hence, to normalize the data, you need to write the following lines of code.

```python
# Normalize the data, so we are rotating about the origin
X = df[['Height', 'Weight']].values
xCent = X - X.mean(axis=0)
xNorm = xCent / xCent.std(axis=0)

# put it back into the dataframe
df['hnorm'] = xNorm[:, 0]
df['wnorm'] = xNorm[:, 1]
```
You can refer to the optional module on summary statistics to get an idea about normalization.

When you plot the normalized data points on scatter plots, you get the following scatter plot, which is located around the origin.

![Scatter Plot Hnorm Wnorm](https://i.ibb.co/XDCQJw7/Scatter-Plot-Hnorm-Wnorm.png)

In the next part, Jaidev separated the male and female normalized data in ‘X’ and ‘Y’, respectively, using the following code.

```python
males = df[df['Gender'] == 'Male']
X = males[['hnorm', 'wnorm']].values
females = df[df['Gender'] == 'Female']
Y = females[['hnorm', 'wnorm']].values
```
Now, let’s create a transformation matrix, also called the ‘rotator_90’ matrix, to rotate the male data points 90 degrees (or pi/2 radians) counterclockwise.

```python
rotator_90 = get_rotation_matrix(np.pi / 2)
```

Once you have created a transformation matrix, you need to multiply the male data points with the transformation, which has been done using the following code.

```python
xrot = np.dot(rotator_90, X.T)
```

As you know, the height and weight of each male person will be in a row matrix format. You also need to get the transpose of this matrix to get the column vector matrix, and this is why you need to perform X.T before multiplying the transformation matrix.  
 

Now, when you plot the rotated male points and the original female points in a single scatter plot, you will get the following graph. 

![Scatter Plot Male vs Female](https://i.ibb.co/nmf8g42/Scatter-Plot-Male-vs-Female.png)

To get the covariance of the new dataset, let’s combine the rotated male data points and the original female data points in a single data frame called ‘newData’ and calculate the covariance matrix.

```python
newData = np.r_[xrot.T, Y]
np.cov(newData.T)
```

You get the following covariance matrix:  

![Covariance](https://i.ibb.co/YZXc5fz/Covariance.png)

In this matrix, you can see that the value of covariance decreases. Also, note the negative sign in the covariance, which shows that if one variable increases, then the other decreases.

Now, let’s compare the two scatter plots.

As you can see in the first scatter plot, the weight increases as the height increases. But in the second scatter plot, there is a very low linear relationship between the transformed weight and height. Hence, you can conclude that the value of covariance is high in the first scatter plot as compared to that in the second scatter plot.

You can refer to the following link to get more insight into the ‘dot’ operation in numpy.

[Dot product in numpy](https://numpy.org/devdocs/reference/generated/numpy.dot.html)
  
In the next segment, you will learn about basis.

#### Rotation

Qn: Suppose you have been given a vector in the form of an array ‘v’ in pandas. Now, when you rotate the vector ‘v’ by an angle of 45 degrees, you get the rotated vector ‘r’. What will be the correct code if you want to represent the vector ‘r’ in the form of a row matrix?

You also have been given a ‘get_rotation_matrix’ function to get the rotation matrix for an angle theta. The function is given below.

```python
def get_rotation_matrix(theta):  # in RADIANS!
    return np.array([[np.cos(theta), - np.sin(theta)],
                     [np.sin(theta), np.cos(theta)]])
```

- 
```python
rotator_45= get_rotation_matrix(np.pi / 4)
r = np.dot(v.T, rotator_45) 
```

- 
```python
rotator_45= get_rotation_matrix(np.pi / 4)
r = np.dot(v.T, rotator_45).T
```

- 
```python
rotator_45 = get_rotation_matrix(np.pi / 4)
r = np.dot(rotator_45, v.T)
```

```python
rotator_45 = get_rotation_matrix(np.pi / 4)
r = np.dot(rotator_45, v.T).T
```

Ans: C.

**Comprehension:**

Suppose you have been given a data set called ‘**exercise_data**’. This dataset contains only two columns ‘var-1’ and ‘var-2’. Suppose you read the dataset in the ‘df’ data frame. Now, based on this dataset, answer the following questions.

Download [Exercise data](exercise_data.csv)

#### Variance

Qn: Which of the following statements is true for var-1 and var-2?

- The variance of var-1 is greater than the variance of var-2.

- The variance of var-2 is greater than the variance of var-1.

- The variance of var-1 is equal to the variance of var-2.

- None of the above.

Ans: B.

Qn: What is the variance in ‘var-1’ and the covariance between ‘var-1’ and ‘var-2’?

- 631.88, 5.36

- 5.36, 3.15

- 3.15, 5.36

- 631, 3.15

Ans: B.