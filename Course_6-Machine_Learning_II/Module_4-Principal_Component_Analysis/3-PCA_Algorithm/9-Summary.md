# Summary

You have now completed a very important session, which forms the backbone of PCA. In this session, we covered the following topics:

-   **Eigenvectors and eigenvalues:** In linear algebra, an **eigenvector** of a linear transformation (or a square matrix) is a non-zero vector that changes at most by a scalar factor when that linear transformation is applied to it. The corresponding **eigenvalue** is the factor by which the eigenvector is scaled.

Certain very important characteristics of eigenvectors are as follows:

1.  Eigenvalues and eigenvectors of a given matrix always occur in pairs.
2.  Eigenvalues and eigenvectors are defined only for square matrices, and it is not necessary that they will always exist. This means that there could be cases where there are no eigenvectors and eigenvalues for a particular matrix; or, in other words, there exist imaginary eigenvectors and eigenvalues.

-   **Diagonalisation of a covariance matrix:** Suppose there is a matrix ‘A’, which has ‘v1’ and ‘v2’ eigenvectors, and λ1 and λ2 eigenvalues, as shown below:  

	$A=\begin{bmatrix}3&1\\0&2\end{bmatrix}$

	$v_1=\begin{bmatrix}1\\0\end{bmatrix}$, $v_2=\begin{bmatrix}-1\\1\end{bmatrix}$

Let’s define the eigenvector and eigenvalue matrices, ‘V’ and ‘Λ’, 

$V=\begin{bmatrix}1&-1\\0&1\end{bmatrix}$, $\Lambda=\begin{bmatrix}3&0\\0&2\end{bmatrix}$

When you multiply matrix ‘A’ with matrix ‘V’, you get the same result as when you multiply matrix ‘V’ with matrix ‘Λ’:

$AV=V\Lambda$

When you **right multiply** both sides of the equation above, you will get the following result:  

$A=V\Lambda V^{-1}$

Or when you **left multiply** both sides of that same equation, you get the following result:

$V^{-1}AV=\Lambda$

If you see this equation, matrix ‘Λ’ is nothing but a diagonal matrix whose non-diagonal entries are simply 0.

So, using the analysis above, you can state that:

**Both A and 𝚲 represent the same linear transformation but in different basis vectors (i.e., original basis and eigenvector basis, respectively).** 

Suppose you have x' vector in an eigenvector basis and you want to calculate the transformed vector in a new eigenvector basis, A'x', which corresponds to the transformed matrix ‘A’ in the original basis. To do this, you first need to convert x' to x, and then x into Ax, and finally convert Ax to an eigenvector basis system. The image given below depicts the above process.

![Eigenvector Transformation](https://i.ibb.co/HXhzVXR/Eigenvector-Transformation.png)

![Eigenvector Transformation](https://i.ibb.co/X547PSx/Eigenvector-Transformation2.png)

Hence, we can say that **both A and 𝚲 represent the same linear transformation but in different basis vectors (i.e., original basis and eigenvector basis, respectively).**

**Or, in other words, you can diagonalise matrix ‘A’ by representing it in a new eigenvector basis system, because matrix ‘A’ will become ‘Λ’ in the eigenvector basis system.** 

**Thus, a very important point that you have learnt here is that you can diagonalise a covariance matrix only when you represent the data points in an eigenvector basis system.**  

**Eigendecomposition of a covariance matrix:** Eigendecomposition of a covariance matrix is nothing but finding the eigenvectors of the covariance matrix so that you can represent all the data points of the original basis system in the eigenvector basis system.

-   **PCA algorithm:** 

Let’s summarise the steps of the PCA algorithm one-by-one:

1.  Suppose you have an original data set with ‘M’ rows and ‘N’ columns. You will get a covariance matrix of order ‘N X N’ for this data set.
2.  After getting the covariance matrix for the data set, find its eigenvectors, which will be the new basis vectors to represent each data point of the original data set to get the diagonalised covariance matrix in the new eigenvector basis system.
3.  Once you have obtained the eigenvectors, simply arrange them in the form of a matrix. Now, this eigenvector matrix will be the ‘change of basis matrix’.
4.  After getting the ‘change of basis matrix’, multiply each data point in the original basis system with this ‘change of basis matrix’ to get the new data points in the eigenvector basis system.
5.  In this way, you represent all the data points of the original basis system in the eigenvector basis system so that you get the uncorrelated features as the covariance matrix has now been diagonalised. 
    
    ![PCA Algorithm](https://i.ibb.co/8zHSxqc/PCA-Algorithm.png)
    

One point that you should remember is that the **“eigenvectors of a covariance matrix are the new directions in which you represent the data to get uncorrelated features; or, in other words, the eigenvectors are the new principal components”.**

-   **Python demonstration of PCA algorithm:** In the Python demonstration, you performed all the steps of the PCA algorithm one-by-one in Python.
-   **Scree plot:** A scree plot visually depicts the percentage of variance in each PC using a histogram.
-   **Spark MLlib demonstration of PCA:** In the Spark MLlib demonstration, you converted the RDDs into matrix form and then applied PCA. You can refer to the codes given below to learn about the transformation of RDDs to a matrix.

You load the data from ‘sklearn’ into the ‘df’ dataframe and start the analysis after starting the Spark context.

The first step is to create the Spark dataframe from the Pandas dataframe, as shown below:

```python
df = sqlContext.createDataFrame(df)
```

Before proceeding further and building the PCA algorithm in PySpark, you need to normalise the data set:

```python
from pyspark.ml.feature import VectorAssembler
from pyspark.ml.feature import StandardScaler

assembler = VectorAssembler(inputCols=df.columns, outputCol='features')
scaler = StandardScaler(inputCol='features', outputCol='normFeatures', withMean=True)

df = assembler.transform(df)
scalerModel = scaler.fit(df)
df = scalerModel.transform(df)

To get the RDD of the Spark dataframe, you need to write the following code:
rdd = df.select('normFeatures').rdd
```


RDDs are not matrices and so, you need to convert them to row matrices. To convert RDDs to row matrices, you need to import RowMatrix.

```python
from pyspark.mllib.linalg.distributed import RowMatrix
```

Row matrices are those matrices whose rows are distributed among multiple clusters of the same machine.

So, to convert the RDDs to a matrix, you need to first convert them into vectors and then transform the vectors to a matrix, as shown below:

```python
from pyspark.mllib.linalg import Vectors
vectors = rdd.map(Vectors.dense)
matrix = RowMatrix(vectors)
```

Now, in the next step, you need to define the number of PCs that you want to get. To do this, you first need to get all the PCs of the ‘wine’ data set:

```python
pc = matrix.computePrincipalComponents(len(df.columns))
```

Once you have printed ‘pc’, you will get a 13 X 13 matrix (in case your data contains a total of 13 columns) of all the PCs.

Now, to project the original data points onto the PCs, you need to simply multiply the data (‘matrix’) with the PCs, as shown below:

```python
matrix_reduced = matrix.multiply(pc)
```

From this step, you will get the ‘matrix_reduced’ matrix, which is nothing but the projection of all the data points on the PCs. This matrix has a total of 13 columns (in case there are a total of 13 columns in your data set), and the total number of rows will be the same as that in the original data set.

Now, let’s convert the ‘matrix_reduced’ matrix to a NumPy array so that you can make the scatter plot of the first two PCs in two dimensions. You can do this as follows:

```python
import numpy as np
x_red = np.array(matrix_reduced.rows.collect())
import matplotlib.pyplot as plt
plt.scatter(x_red[:, 0], x_red[:, 1], c=wine.target)
```

![](https://images.upgrad.com/fb331695-9868-473c-94b0-64fc7b23e3ed-2.png)

With this, you have learnt about PCA in Python as well as in Spark. In the next session, you will go through an end-to-end case study on recommendation systems using PCA.

Please find the well-coded Python and PySpark notebooks below:

- [PCA Python Iris Data](pca_algo.ipynb)

- [PCA Spark](pca_mlib.ipynb)

