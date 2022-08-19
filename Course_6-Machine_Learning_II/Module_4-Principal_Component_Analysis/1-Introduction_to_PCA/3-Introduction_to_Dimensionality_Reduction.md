# Introduction to Dimensionality Reduction

Let’s start by understanding what a low-rank matrix  means. Suppose you have a data set that contains information related to the employees of a particular company. This data contains three columns: ‘**Salary**’, ‘**Expenditure**’ and ‘**Savings**’. Note that another way of finding the savings of a particular person is by simply calculating the difference between their salary and their expenditure.

Now, suppose you want to build a linear regression model to predict the savings of a person relative to the corresponding salary.

Do you require all three features to build this linear regression model?

Well, no because the third feature is a combination of the other two features. So, only two features are sufficient to build the model. In the next video, you will understand this concept in a more detailed manner.

**VIDEO**

As you saw in the video above, the rank of a matrix is nothing but the number of linearly independent rows or columns in a matrix; whichever is lower. Let’s consider the following matrix:

$$X=\begin{bmatrix}1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9\end{bmatrix}$$

Here, **(Third column) = 2 X (Second column) - (First column).** Hence, the rank of the square matrix ‘X’ is not 3 but 2 because there are only two columns that are linearly independent. This process, where you reduce the rank of a matrix by not considering the linearly dependent columns or rows and only consider the independent columns or rows, is called low-rank approximation.

Now, let’s slightly change the value ‘1’ to  ‘1.001’.

$$Y=\begin{bmatrix}1.001 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9\end{bmatrix}$$

As you can see above, in the ‘Y’ matrix, you cannot write the third column as a linear combination of first and second columns, or any columns as a linear combination of other columns. This matrix is called a **full rank matrix**, and the rank of this matrix is 3.

Now, suppose you want to build an ML model using the three columns of the matrix ‘Y’ as the features. Although there is no dependency of any column on another column, there is a high correlation (or covariance) among the columns, which means that there is some linear dependency of column 3 on column 1 and column 2. The correlation coefficient (which can be interpreted as covariance) between the columns represents the extent to which they are linearly related to one another.  
 

So, as Jaidev explained in the previous video, in order to reduce the dimensionality when there is no explicit relationship among the variables, you need to consider the variance rather than the rank. Similar to PCA, there are many algorithms that use variance to extract the low-rank decomposition of the data set based on which the component maximises the variance of that particular data set.

You will notice this phenomenon at many instances in machine learning model building, wherein you cannot express one feature with the exact linear combination of the other features because the noise in the data set fluctuates the data points, but it does not mean that the features are not correlated to one another at all. In such cases, you can use the variance as the measure to decompose the data into low rank and consider only those components/features that maximise the variance.

As discussed in the video, apart from PCA, there are other low-rank approximation techniques that do not necessarily consider the assumption of a linear combination of columns. These techniques are as follows:

1.  Random projections
2.  Kernel PCA
3.  ISOMAP
4.  T-SNE/Manifold learning

Note that the aforementioned techniques will not be covered in this module. In the next segment, you will be introduced to principal component analysis (PCA) and learn how exactly PCA will be used in this module.

#### Low-Rank Decomposition

Qn: Suppose you are given a data set with two columns: ‘Salary’ and ‘No_of_pushups’.  
**Salary**: This column contains the monthly salary of a particular person.  
**No_of_pushups**: This column contains the number of push-ups a particular person can do in one minute.

Now, you have noticed that as the salary increases, the number of push-ups that a person can do decreases.

Considering the scenario above, select the correct option from below.

- To build an ML model, you can reduce the dimensionality of the data set because there is some relation between the two columns.

- You can use variance and covariance as parameters to look into the problem because there is no exact relation between the two columns.

- Since there is a correlation but no causation between the columns, inferring any relation between two the columns is not advised.

- None of the above

Ans: C.

Qn: Suppose you have a data set with 1000 columns and 15000 rows with all the numerical entries. suppose there is high covariance between the following columns:

- Column- 1 and column-2

- Column- 3 and column- 10

But there is no column which can be represented as the linear combination of the other columns. What will be the rank of this data set?

- 1000

- 998

- 996

- None of the above

Ans: A. *This is the correct answer as there is no linear relation among any column. there can be covariance between the columns but it does not affect the rank of the matrix. The rank of a matrix only varies if there is an exact linear combination between the columns.*
