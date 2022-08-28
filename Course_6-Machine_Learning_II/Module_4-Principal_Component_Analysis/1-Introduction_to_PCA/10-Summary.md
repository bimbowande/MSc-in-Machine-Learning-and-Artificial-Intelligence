# Summary

You have completed the session. In this session you have gone through the following topics:

-   Low-rank Approximation.
-   Introduction to the PCA
-   Vectors 
-   Matrices
-   Covariance and Correlation Matrix

**Low-rank approximation:** In this segment, you have seen that the rank of a matrix is nothing but the number of linearly independent rows or columns in a matrix. Let’s consider the matrix below:

$$X=\begin{bmatrix}1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9\end{bmatrix}$$

Here you can see that (3rd column) = 2 X (2nd column) - (1st column). Hence, the rank of the square matrix ‘X’ is not 3 but it is 2 as there are only two columns which are linearly independent. This process is called the low-rank approximation where you reduce the rank of a matrix by not considering the linearly dependent columns or rows and you only concern about the independent columns or rows.

Jaidev has explained that, to reduce the dimensionality in many cases where there is no exact relationship among the variables you need to go with the variance instead of the rank. There are many algorithms like PCA which use variance to extract the low-rank decomposition of the dataset based on which component that maximises the variance of that particular dataset.

  
You will see this phenomenon at many places in machine learning model building, where you can’t express one feature with the exact linear combination of the other features but it does not mean that the features are not correlated to each other at all. In such cases, you can take the variance as the measure to decompose the data into the low rank.  
 

**Introduction to the PCA:** Here you have started the discussion with the importance of variance in a particular dataset. If a particular column has more variance in it then the importance of that variable is more as compared to the other columns in the dataset. In other words the more the variance more information that particular column has to build a ML model.

You have taken an example of salary and age and calculate the percentage of variance in each column as below:

![Salary vs Age](https://i.ibb.co/kg027g8/Salary-vs-Age.png)

**Percentage of variance in Age: 34%  
Percentage of variance in Salary: 66%**

As you can see here that both of the columns contain the significant amount of variance and hence, both of the columns are significant for the analysis.

Suppose somehow we are able to create two new columns, say PC1 and PC2 from the original set of columns i.e. age and salary, and the percentage of variance in PC1 is 99.8% and the percentage of variance in PC2 is 0.2%. Also, the covariance between the PC1 and PC2 is almost zero.

Here in this case as both PC1 and PC2 are uncorrelated with each other (covariance almost equals to zero) and almost 99% of the information i.e. variance is contained in PC1 hence, we can simply drop  PC2 as most of the information is contained in PC1.  
You can depict this process using the rotation of the axes, 

![PCA Rotation of Axis](https://i.ibb.co/HY7tSBZ/PCA-Rotation-of-Axis.png)

You have seen graphically how you can rotate the axes to get the maximum variance and least covariance between the variables in the previous segment. 

PCA converts possibly correlated variables to ‘Principal Components’ such that:

-   They are uncorrelated to each other.
-   They are the linear combinations of the original variables.
-   They capture maximum information in the dataset.

So, basically what PCA does is that it converts the data **by creating new features from old ones,** where it becomes easier to decide which features to consider and which not to.

The number of principal components is the same as the number of columns in the dataset. PCs are sorted in descending order of information content. Suppose you have a dataset with four columns then you get the four PCs and the first PC gets the maximum variance and the second PC gets the second maximum variance and so on.

![Principal Components and Variables](https://i.ibb.co/HX8PVMY/Principal-Components-and-Variables.png)

Hence, for further analysis like visualization, ML model building you can simply consider those PCs which contain maximum information or variance.  
 

**Vectors**:

-   An ordered collection of numbers. Note the word ‘ordered’, suppose you have a vector ‘x’ in n-dimensional space, then the elements in the vector ‘x’ will be in order.
-   A vector is used to represent a point in space. 

The basic purpose of understanding the vectors is to represent the data points of a dataset in the form of vectors. Let’s look at the following dataset of different patients, which contains two columns: one is the height (cm) and another one is the weight (kg).

![Vectors Patients](https://i.ibb.co/7yN858Q/Vectors-Patients.png)

You can represent this particular data in the form vectors on a 2-dimensional plane because it only contains 2 columns.

![Vectors Height Weight](https://i.ibb.co/0XSqFSF/Vectors-Height-Weight.png)

**Matrices**: 

-   An ordered collection of numbers just like a vector.
-   Matrix has more than one index, unlike vectors. It has numbers along its rows and also along with its columns. The order of a matrix is defined as:

           **Number of rows X Number of columns.**

Suppose you have matrix ‘X’, 

![Covariance Matrix](https://i.ibb.co/g7XVvck/Covariance-Matrix.png)

Then the order of this matrix is n X m.

-   **Addition of matrices: T**he addition of two matrices (X and Y) can only be performed if and only if.

**Number of col(X) = Number of col(Y) AND Number of rows(X) = Number of rows(Y).**

-   **Multiplication of matrices:**

The operation AXB is only possible if and only if:

**Number of col (A) = Number of rows (B)**

![Matrix Multiplication Operation](https://i.ibb.co/26VjR7b/Matrix-Multiplication-Operation.png)

  
**Matrix multiplication is a parallel process.**  
Suppose you want to multiply ‘A’ and ‘B’ then the process of multiplication of a row of matrix ‘A’ with the column of the other matrix ‘B’ is distributed on multiple executors.

**Covariance matrix**: The covariance refers to the measure of how two random variables in a data set will change together. 

  
A **positive covariance** means that the two variables are positively related, and they move in the same direction. A **negative covariance** means that the variables are inversely related, and they move in opposite directions.

  
The formula to calculate the covariance between the two variables ‘x’ and ‘y’ is similar to the variance formula:
$$\sigma^2_{xy}=E[(x-\mu_x)(y-\mu_y)]$$
where E is the mean operator.

You can depict the covariance matrix of ‘n’ column data in the format below:

![Covariance Matrix](https://i.ibb.co/g7XVvck/Covariance-Matrix.png)

The covariance matrix is a diagonal matrix and it is symmetric around its diagonal.

The correlation is closely attached to the covariance and The formula to calculate the correlation between ‘x’ and ‘y’  from the covariance is:

$$\rho_{xy}=\dfrac{E[(x-\mu_x)(y-\mu_y)]}{\sigma_x\sigma_y}=\dfrac{\sigma^2_{xy}}{\sigma_x\sigma_y}$$
The very basic difference between covariance and the correlation is that:

**'Covariance' indicates the direction of the linear relationship between variables. 'Correlation' on the other hand measures both the strength and direction of the linear relationship between two variables.**