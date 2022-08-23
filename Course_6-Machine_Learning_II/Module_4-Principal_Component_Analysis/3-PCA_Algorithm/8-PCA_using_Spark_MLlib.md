# PCA using Spark MLlib

In the previous two segments, you learnt how to perform PCA in Python. Now, in this segment, you will learn how to perform PCA using Spark MLlib.

For now, let’s start with a smaller data set, the ‘wine’ data set. This data set is the result of a chemical analysis of wines produced in Italy. The analysis determined the quantities of 13 constituents found in each of three types of wines.

So, in the next video, let’s load the data from ‘sklearn’ into the ‘df’ dataframe and start the analysis after starting the Spark context.

You can refer to the following commented notebook for the further discussion:

Download [PCA Spark Commented Notebook](pca_mllib.ipynb)

**VIDEO**

The first step is to create the Spark dataframe from the Pandas dataframe, as shown below:

```python
df = sqlContext.createDataFrame(df)
```

To get the RDD of the Spark dataframe, you need to write the following code:

```python
rdd = df.rdd
```

RDDs are not matrices and so, you need to convert them to row matrices. To convert the RDDs into row matrices, you need to import ‘RowMatrix’.

```python
from pyspark.mllib.linalg.distributed import RowMatrix
```

Row matrices are those matrices whose rows are distributed among multiple clusters of the same machine.

So, to convert the RDDs into a matrix, you need to first convert each row into vectors, and then from the vectors, convert into a matrix whose rows will be distributed on multiple executors of the same machine:

```python
from pyspark.mllib.linalg import Vectors
vectors = rdd.map(Vectors.dense)
matrix = RowMatrix(vectors)
```

Now, in the next step, you need to define the number of PCs that you want to get. To do this, you need to first get all the PCs of the ‘wine’ data set, as shown below:

```python
pc = matrix.computePrincipalComponents(len(df.columns))
```

Once you have printed ‘pc’, you will get a 13 X 13 matrix of all the PCs.

Now, to project the original data points on the PCs, you need to multiply the data with the PCs, as shown below:

```python
matrix_reduced = matrix.multiply(pc)
```

From this step, you will get the ‘matrix_reduced’ matrix, which is nothing but the projection of all the data points on the PCs. This matrix has a total of 13 columns, and the total number of rows is the same as that in the original data set.

Don’t you have doubt about why are we doing **_matrix.multiply(pc)_** instead of multiplying the _**inverse(pc)**_ by the transpose of the _**matrix**_ that we have done in our entire earlier discussions?

Let’s briefly learn the concept of orthogonality of a matrix to understand this better by solving the questions below.

#### Orthogonality

Qn: Suppose you have given a square matrix ‘A’ and its inverse matrix ‘B’ as below:

$A=\begin{bmatrix}3/7&2/7&6/7\\-6/7&3/7&2/7\\2/7&6/7&-3/7\end{bmatrix}$, $B=\begin{bmatrix}3/7&-6/7&2/7\\2/7&3/7&6/7\\6/7&?&-3/7\end{bmatrix}$

What will be the missing entry in the matrix ‘B’?

3/7

4/7

2/7

-2/7

Ans: C. *Simply multiply the matrix ‘A’ with ‘B’ and compare the result with the identity matrix ‘I’. (3/7)(-6/7)+(2/7)(3/7)+(6/7)(?)= 0 and you get the value 2/7.*

Qn: What is the result when you transpose the matrix ‘A’?  

$A=\begin{bmatrix}3/7&2/7&6/7\\-6/7&3/7&2/7\\2/7&6/7&-3/7\end{bmatrix}$

- The transpose of the matrix is equal to the matrix ‘A’.

- The transpose of the matrix is equal to the inverse of the matrix A. 
 
- Can not be determined.

Ans: B.

So, in the above example, you can see that the transpose of the matrix ‘A’ is equal to the inverse matrix of itself. This is one of the important properties of orthogonal matrices. So **if there is a orthogonal matrix ‘A’ then:**

$A^T=A^{−1}$

Now, one of the very important facts that you should keep in mind is that **the eigenvector matrix is also an orthogonal matrix. An orthogonal matrix is a matrix whose columns and rows are perpendicular to each other.** In other words, the pairwise dot product of the column vectors is 0; same for the rows. This helps us realise that the vectors in the eigenvector matrix are perpendicular or orthogonal to each other. This is one interesting property that you should remember about the eigenvectors. We won’t go into the derivation of this.

Suppose you have a data point in **‘row vector’** format ‘x’ and you want to find its corresponding point in the eigenvector basis and get the result into **‘row matrix’** format only then the operation that you will perform will be-

$x'=\begin{bmatrix}v_1&v_2\end{bmatrix}^{-1}x^T$

Where v1 and v2 are the eigenvectors of the covariance matrix. This will give the x’ in column matrix format and to get the x’ in row matrix format then you need to transpose it again.

$x_{final}= {(x')}^T$

Now let’s try to find the transpose of  $x'=\begin{bmatrix}v_1&v_2\end{bmatrix}^{-1}x^T$.

$$(\begin{bmatrix}v_1&v_2\end{bmatrix}^{-1}x^T)^T=(\begin{bmatrix}v_1&v_2\end{bmatrix}^Tx^T)^T=x\begin{bmatrix}v_1&v_2\end{bmatrix}$$

Because the eigenvector matrix is an orthogonal matrix and hence, its transpose is equal to its inverse. Please keep in mind that $(AB)^T=B^TA^T$.

And hence, you can directly perform the step below without doing inverse or transpose. Pretty interesting, right!

Now, let’s convert the ‘matrix_reduced’ matrix to a numpy array and make the scatter plot of the first two PCs:

```python
import numpy as np
x_red = np.array(matrix_reduced.rows.collect())
import matplotlib.pyplot as plt
plt.scatter(x_red[:, 0], x_red[:, 1], c=wine.target)
```

![PCA Spark](https://i.ibb.co/jzJcPtX/PCA-Spark.png)

Let’s perform PCA with Python sklearn and compare the results obtained with the Spark MLlib procedure.

**VIDEO**

So, the scatter plot that you obtained with this method has a different scale of the axes, as you saw in the previous scatter plot. Let’s go through the next video.

**VIDEO**

So, before performing PCA analysis in Spark, you need to normalise the data. So, you need to normalise the data set and add the following lines of code:

```python
from pyspark.ml.feature import VectorAssembler
from pyspark.ml.feature import StandardScaler

assembler = VectorAssembler(inputCols=df.columns, outputCol='features')
scaler = StandardScaler(inputCol='features', outputCol='normFeatures', withMean=True)

df = assembler.transform(df)
scalerModel = scaler.fit(df)
df = scalerModel.transform(df)
```

Now, once you have normalised the data set, the next steps are the same as the ones that we performed earlier to build the PCA model.

#### PCA

Qn: What are the first step before performing PCA and why (assume the data is clean and all the values are numerical in nature)?

- Scaling and standardising the data so that variables of differing magnitudes fall in the same range.

- There are prerequisites before performing PCA. You can directly go ahead and perform PCA.

- The data needs to be checked to ensure all the values are positive.

- None of the above

Ans: A. *This should be the very first step in the PCA process.*

Qn: You are given a data set that contains many variables. Some of these variables are highly correlated and you know about it. Your manager has asked you to run a PCA on this data set. Would you remove the correlated variables first? If yes, then why?

Ans: *Removal of correlated features is not a good option as it may lead to loss of information. Instead, you should perform PCA on this data set to get the uncorrelated features from the correlated ones. In this way, you may build a highly optimised machine learning model.*

**Additional Link:**

[Orthogonal matrix wiki page.](https://en.wikipedia.org/wiki/Orthogonal_matrix#:~:text=In%20linear%20algebra%2C%20an%20orthogonal,is%20the%20identity%20matrix.)