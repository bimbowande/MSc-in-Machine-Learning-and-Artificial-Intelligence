# Module Summary

You have completed this module on Principal Component Analysis. Although PCA is not a machine learning technique, it is useful to build an optimised machine learning model.

Let’s first gather what all you have learnt in the introductory session of PCA.

-   **Variance as a measure of information**: There are many algorithms such as PCA that use variance to extract the low rank decomposition of a data set based on the component that maximises the variance of that particular dataset.

          You will see this phenomenon at many places in machine learning model building, where            you cannot express one feature with the exact linear combination of the other features                because of some noise in the dataset that leads to a fluctuation in the data points.                            However, this does not mean that the features are not correlated to each other at all. In                such cases, you can take the variance as the measure to decompose the data into a low                  rank and consider only those components/features that maximise the variance.

-   **What PCA does:** PCA converts possibly correlated variables to principal components such that:

1.  They are uncorrelated to each other.
2.  They are the linear combinations of the original variables.
3.  They capture maximum information in the dataset.

-   The number of principal components is the same as the number of columns in the dataset. PCs are sorted in descending order of information content (i.e., in the descending order of the percentage of variance). Suppose you have a data set with four columns and you consider four PCs. The first PC gets the maximum variance and the second PC gets the second maximum variance, and so on.

       ![Principal Components and Variables](https://i.ibb.co/HX8PVMY/Principal-Components-and-Variables.png)

In the image above, you can see that in the original dataset, there are four variables with some significant variance in each variable. Once you find the PCs of this dataset, you get the most of the variance (around 92% of the information) in the top two PCs only. Hence,            you can ignore PC3 and PC4, which leads to the dimensionality reduction in the dataset without losing too much information. 

However, keep in mind that the number of PCs relevant to be considered depends on the case in terms of how much information is required to predict accurately from an ML model.

**Tools to understand the PCA algorithm:** To understand the PCA algorithm in detail, you need to learn about the following three tools.

1.  **Summary Statistics:** Mean, median, mode, variance, standard deviation and covariance
2.  **Vectors:** Vector operations such as addition, scalar multiplication and vector representation of data
3.  **Matrices:** Representation of vectors in the form of a matrix, matrix operations, basis and change of basis

-   **Covariance:** Covariance refers to the measure of two random variables in a data set that changes together.

          Covariance is a measure of linearity between two variables. 

1.  **Positive covariance:** It means that if one variable increases, then the other will also increase.
2.  **Negative covariance:** It means that if one variable increases, then the other will decrease.
3.  **Zero covariance:** It means that there is no linear relation between the two variables.
4.  Also, the covariance of variable 1 with respect to variable 2 is the same as the covariance of variable 2 with respect to variable 1.

Note that the **covariance of ‘x’ with respect to ‘y’ is the same as the covariance of ‘y’ with respect to ‘x’.**

-   **Basis:** The change of basis is summarised in the following format.

1.  ‘Basis’ is a unit that is used to express vectors.
2.  Vectors in any dimensional space or matrix can be represented as a linear combination of basis vectors.
3.  The basic definition of basis vectors is that they are a certain set of vectors whose linear combination is able to explain any other vector in that space.

-   **Change of basis:** In this concept, you learnt to change the basis using the **‘change of basis matrix’**. The main idea behind the change of basis is discussed in the example below.

Suppose you have a point, say (4, 3) in x-y basis. Now, if you want to represent the same point in the v1 (-1, 3) and v2 (2, -1) basis, then you need to represent the (4, 3) point as a              linear combination of v1 and v2. So, the coefficient of the linear combination, i.e., (2, 3)                will be the new representation of the same point in the v1 and v2 basis. 

          This is depicted in the image below.

![Change of Basis](https://i.ibb.co/6BCg9wP/Change-of-Basis2.png)

-   **Eigenvectors and eigenvalues:** In linear algebra, an **eigenvector** of a linear transformation (or a square matrix) is a non-zero vector, which changes the most by a scalar factor when that linear transformation is applied to it. The corresponding **eigenvalue** is the factor by which the eigenvector is scaled.

           Some important characteristics of eigenvectors are:

1.  Eigenvalues and eigenvectors of a particular matrix always occur in pairs.
2.  Eigenvalues and eigenvectors are defined only for square matrices, and they do not always exist. This means that there could be a case where there are no eigenvectors and eigenvalues for a particular matrix or in other words, and there exists only imaginary eigenvectors and eigenvalues.

-   **Diagonalisation of the covariance matrix:** Suppose there is a matrix ‘A’, which has ‘v1’ and ‘v2’ eigenvectors and λ1 and λ2 eigenvalues.

$A=\begin{bmatrix}3&1\\0&2\end{bmatrix}$

Eigenvectors:   $v_1=\begin{bmatrix}1\\0\end{bmatrix}$ and  $v_2=\begin{bmatrix}-1\\1\end{bmatrix}$

Eigenvalues:  $\lambda_1=3$,   $\lambda_2=2$
    

Let’s define an eigenvector and eigenvalues matrices ‘V’ and ‘Λ’, respectively.

$V=\begin{bmatrix}1&-1\\0&1\end{bmatrix}$,   $\Lambda=\begin{bmatrix}3&0\\0&2\end{bmatrix}$

When you multiply matrix ‘A’ with matrix ‘V’, then you get the same results as when you multiply matrix ‘V’ with matrix ‘Λ’.

$AV=V\Lambda$

When you **right multiply** both sides of the equation above, then you get the following result.

$A=V\Lambda*V^{−1}$

Or, when you **left multiply** both sides of the equation above, then you get the following result.

$V^{−1}AV=\Lambda$

In this equation, matrix ‘Λ’ is a diagonal matrix whose non-diagonal entries are simply zero.

So, using the analysis above, the following can be stated.

**Both A and 𝚲 represent the same linear transformation but in different basis vectors (i.e., original basis and eigenvector basis, respectively).** 

Suppose you have vector **x’** in an eigenvector basis, and you want to calculate the transformed vector in a new eigenvector basis, i.e., **A’x’**, which corresponds to the transformed matrix **‘A’** in the original basis, then you first need to convert **x’** into **x** and then **x** into **Ax** and then finally convert **Ax** into an eigenvectors basis system. This process is depicted in the following image.

![Eigenvector Transformation](https://i.ibb.co/gzDhkGr/Eigenvector-Transformation1.png)

Hence, you can say that **Both A and 𝚲 represent the same linear transformation but in different basis vectors (i.e., original basis and eigenvector basis, respectively).**

**In other words, you can diagonalise matrix ‘A’ by representing it into a new eigenvectors basis system because matrix ‘A’ will become ‘Λ’ in the eigenvectors basis system.** 

**Hence, an important result that you obtain here is that you can diagonalise the covariance matrix only when you represent the data points into an eigenvectors basis system.**

-   **Eigendecomposition of the covariance matrix:** Eigendecomposition of the covariance matrix refers to finding the eigenvectors of the covariance matrix so that you can represent all the data points of the original basis system into an eigenvectors basis system.
-   **PCA Algorithm:** Let’s summarise the steps of PCA algorithm one by one.

1.  Suppose you have an original dataset with **‘M’ rows and ‘N’ columns.** Then, you will have a **covariance matrix of the order of ‘N X N’** for this dataset.
2.  After getting the covariance matrix of the dataset, you have to find its eigenvectors, which will be the new basis vectors to represent each data point of the original dataset to get the **diagonalised covariance matrix** in the new eigenvector basis system.
3.  Once you get the eigenvectors, you can arrange them in the form of a matrix. Now, this eigenvector matrix will be the **‘change of basis matrix’**.
4.  After getting the **‘change of basis matrix’**, multiply each data point in the original basis system with this **‘change of basis matrix’** to get the new data points in the **eigenvectors basis system.**
5.  In this way, you can represent all the data points of the original basis system in an eigenvector basis system so that you get the uncorrelated features, as the covariance matrix has been diagonalised. 

-   **Spark MLlib demonstration of PCA:** In the Spark MLlib demonstration, you have seen that you can convert the RDDs into a matrix form and then apply PCA on it. You can refer to the following code to learn about the transformation of RDDs into a matrix.

You can also load the data from ‘Sklearn’ into a ‘df’ data frame and begin the analysis after starting SparkContext.

The first step is to create the Spark data frame from the pandas data frame.

```python
df = sqlContext.createDataFrame(df)
```

Before proceeding with building the PCA algorithm in PySpark, you need to normalize the dataset.

```python
from pyspark.ml.feature import VectorAssembler
from pyspark.ml.feature import StandardScaler

assembler = VectorAssembler(inputCols=df.columns, outputCol='features')
scaler = StandardScaler(inputCol='features', outputCol='normFeatures', withMean=True)

df = assembler.transform(df)
scalerModel = scaler.fit(df)
df = scalerModel.transform(df)
```

To get the RDD of the Spark data frame, you need to write the following code:

```python
rdd = df.select('normFeatures').rdd
```

RDDs are not matrices, so you need to convert the RDDs into row matrices. To do so, you need to import:

```python
from pyspark.mllib.linalg.distributed import RowMatrix
```

Row matrices are matrices whose rows are distributed in multiple clusters of the same machine.

So, to convert the RDDs into a matrix, you first need to convert them into vectors and then from vectors into a matrix.

```python
from pyspark.mllib.linalg import Vectors
vectors = rdd.map(Vectors.dense)
matrix = RowMatrix(vectors)
```

Now, in the next step, you need to define the number of principal components that you want to consider. So, you first need to get all the principal components.

```python
pc = matrix.computePrincipalComponents(len(df.columns))
```

Once you print the ‘pc’, you get a 13 X 13 matrix (in case your data contains a total of 13 numerical columns) of all the PCs (i.e., eigenvectors).  
Now, to project the original data points on to the PCs, you need to multiply the data (‘matrix’) with the PCs.

```python
matrix_reduced = matrix.multiply(pc)
```

From here, you get the ‘matrix_reduced’, which is a projection of all the data points on the PCs. In this matrix, there are 13 columns (In case you have a total of 13 columns in the dataset) and the total number of rows will be the same as that in the original dataset.

Now, you need to convert the ‘matrix_reduced’ matrix into a NumPY array so that you can plot the scatter plot of the first two PCs in two dimensions.

```python
import numpy as np
x_red = np.array(matrix_reduced.rows.collect())
```

With this, you have learnt about the PCA algorithm and also learnt how to perform PCA in PySpark.