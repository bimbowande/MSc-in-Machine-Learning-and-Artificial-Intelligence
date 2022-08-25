# PCA Python Demonstration

Welcome to the hands-on demonstration of the PCA algorithm in Python. In the previous segments, you learnt about the concept of the PCA algorithm. Now, in this segment, you will learn how to implement the PCA algorithm in Python using the ‘**sklearn**’ Python library. You will be implementing PCA on the ‘iris’ data set in Python.

So, let’s get an understanding of the ‘iris’ data set first.

The ‘iris’ data set consists of 50 samples from each of three species of Iris (Iris setosa, Iris virginica and Iris versicolor). Four features, the lengths and the widths of the sepals and petals, were measured for each sample, in centimetres.

So, basically the ‘iris’ data set contains the following five columns:

1. Sepal length (cm)
2. Sepal width (cm)
3. Petal length (cm)
4. Petal width (cm)
5. Species type

In this demonstration, we will first build the PCA algorithm step-by-step and after that you will again build the PCA algorithm using the ‘PCA’ package of the ‘**sklearn**’ library. Once you will obtain both the results, you will see that both the procedures produce the same results.

So, let’s start the step-by-step procedure to perform principal component analysis. The very first step in PCA is to **normalise the data set and find the covariance matrix** of the data. Let's start the Python demonstration by loading the data and finding its covariance matrix.

You can refer to the following commented python notebook which will be helpful for further discussion.

Download [PCA Python- Iris datset](pca_algo.ipynb)

**VIDEO**

#### Normalization

Qn: What is it important to normalize the data set while doing the PCA?

Ans: *The reason for performing the normalization step is that the principal components are linear combinations of original variables and also that since the variance/ covariance is used to find the eigenvectors, all variables need to be brought down to the same scale.*

Let’s understand the steps implemented one-by-one:

In the very first part of the code, you need to import certain useful libraries. Some of the important libraries that you need to understand are as follows:

```python
from sklearn.datasets import load_iris
from sklearn.decomposition import PCA
```

- The ‘iris’ data is in-built in the ‘sklearn.dataset’ package. You just need to import it and load it into a dataframe or in an array.
- There is a ‘PCA’ package in the ‘sklearn.decomposition’ library from where you need to import this package.

Once you have loaded the data into an array, ‘X’, you need to normalise it. There are a total four numerical columns corresponding to the sepal and petal lengths and widths. So, to normalise each numerical column, you need to perform the following steps:

- First, you need to find the difference between each data point and the mean for each column, and then divide the result by the standard deviation of that particular column:

- `x_centered = X - X.mean(axis=0)`

- `x_scaled = x_centered / x_centered.std(axis=0)`

- In this way, you will get the normalised data into an array, i.e., _x_scaled_.

- If you take a look into the mean and the variance of this normalised data set, then you will notice that the mean is almost equal to 0 and the variance works out to be 1, which is true in the case of a normalised data set.

In the next step, you need to find out the covariance matrix of the normalised data set. To find the covariance matrix of the ‘iris’ data set, you need to first transpose the ‘_x_scaled_’ array and then implement the _‘np.cov(x_scaled.T)’_ .

Once you have obtained the covariance matrix of the data set, you will next have to create its heatmap after converting the covariance matrix array ‘C’ into a dataframe, as shown below:

![Iris Dataset Covariance](https://i.ibb.co/xqQ6227/Iris-Dataset-Covariance.png)

Here, you can see that there are high covariances of about 0.82, 0.88 or 0.97 between the features.

Now, can you recall what the next step is once you have obtained the covariance matrix of the data set? Well, the next step is to find out the eigenvectors and eigenvalues of the covariance matrix and represent the original data points in the eigenvector basis system.

**VIDEO**

So, to calculate the eigenvectors and eigenvalues of the covariance matrix, you need to write the following code:

```python
w, v = np.linalg.eig(C)
```

Here, ‘w’ will get the eigenvalues and the array ‘v’ will get the eigenvectors of the covariance matrix ‘C’, as shown above:

```python
ix = np.argsort(w)[::-1]
v_sorted = v[:, ix]
```

#### PCA

Qn: Suppose there are four eigenvalues in ‘w’ which are as follows:  
w= [2.3, 1.4, 5, 0.1]  
What will the array ‘ix’ contain when you perform the below operation:

```python
ix = np.argsort(w)[::-1]
```

- `ix= [5, 2.3, 1.4, 0.1]`

- `[2, 0, 1, 3]`

Ans:B. *This is the correct answer as this code will return the index values only not the actual values.*

This step is essential to arrange the eigenvectors in ascending order of their eigenvalues. But why is it an important step? Let’s try and understand now.

In the first session of this module, you learnt that PCs are arranged in decreasing order of their variances. The first PC has the maximum variance (information), the next PC has the second highest variance, and so on. Therefore, to arrange the PCs in order of decreasing variance, you need to arrange the eigenvectors in decreasing order of their corresponding eigenvalues.

If you want to dig more deep into the concept of eigenvalues related to PCA, then there is an interesting fact. Do you remember that the diagonalized covariance matrix in eigenvectors’ basis is nothing but the eigenvalues matrix ‘Λ’ ? 

The diagonalized covariance matrix $= \Lambda=\begin{bmatrix}\lambda_1&0\\0&\lambda_2\end{bmatrix}$

So, the variance in each PC is $\lambda_1$ and $\lambda_2$ respectively and if you want to calculate the percentage of variance in each principal component then you can do this using the following formula.

Percentage of variance explained by the eigenvector- 1 (PC1) which is corresponding to the $\lambda_1$ will be:

$\lambda_1/(\lambda_1+\lambda_2)$

Percentage of variance explained by the eigenvector- 2 (PC2) which is corresponding to the $\lambda_2$  will be:

$\lambda_2/(\lambda_1+\lambda_1)$

And hence, it is necessary to arrange the eigenvectors in the decreasing order of their eigenvalues.

So, there are a total four variables in the ‘iris’ data set, and, therefore, you will get a total of four PCs in decreasing order of their variances. For now, let's take only two PCs for further analysis.

Next, you need to determine the values of the data points in the newly obtained eigenvector basis system. To do that, you need to multiply the **inverse of the eigenvector matrix** with the **original data points.**

Let’s examine the shape of a single row of the scaled ‘iris’ data set:

|       | Sepal length    | Sepal width | Petal length | Petal width |
| ----- | --------------- | ----------- | ------------ | ----------- |
| Row-1 | -9.00681170e-01 | 1.01900435  | -1.34022653  | -1.31544430 |

A single row is a row matrix; but to multiply the data points with the eigenvector matrix, you need to have a column matrix. Therefore, you need to transpose the entire ‘x_scaled’ array to multiply it with the inverse of the eigenvector matrix.

To calculate the inverse of the ‘v_sorted’ array, you need to perform the following operation:

v_inv = np.linalg.pinv(v_sorted)

Before moving to the next step, let’s briefly understand the transpose of a matrix-

The transpose of any matrix can be obtained by converting its rows into columns or in other words converting the columns into rows. You will have a better understanding of this using the example below. 

$A=\begin{bmatrix}1&2&3\\4&5&6\end{bmatrix}$,  $A^T=\begin{bmatrix}1&4\\2&5\\3&6\end{bmatrix}$

So, once you get the inverse of the eigenvector matrix, you next need to multiply the transpose of each data point in row format by the inverse of the eigenvector matrix, as shown below:

Let’s understand the following code.

```python
x_lr = np.dot(v_inv, x_scaled.T).T
```

In order to understand the transposes we have performed, let’s consider the following two basis vectors v1 and v2 and you want to represent the point [a, b] (in x-y plane) in the new basis system then you can use the following formula to get the result.  
 

$\begin{bmatrix}c\\d\end{bmatrix}=\begin{bmatrix}v_1&v_2\end{bmatrix}^{-1}\begin{bmatrix}a\\b\end{bmatrix}$

Where [c, d] is the representation of the point [a, b] in the v1 and v2 basis. Note that in the numpy format [a, b] and [c, d] are represented as a row vectors and not column vectors. Hence, we need to take 2 transposes.

- So, basically each row of the dataset is a vector which is not in column vector format and hence, to convert it into column matrix from row matrix it is important to transpose it that’s why it is important to perform ‘_x_scaled.T’._
- The output of _np.dot(v_inv, x_scaled.T)_ will be a column matrix and, hence, you need to transpose it again to get the results in row format.

So, finally, we are focusing on two PCs only. Next, to get the reduced data corresponding to the two PCs only, you need to perform following step:

```python
x_lr_reduced = x_lr[:, :N],
where N= 2
```

When you plot the two PCs on a scatter plot, you will get the following graph:

![PCs Scatter Plot](https://i.ibb.co/Fq0wsfW/PCs-Scatter-Plot.png)

In the graph, you can see that the three classes of Iris species are indicated with violet, blue and yellow. You can see that with 2 linear separators, you are able to classify most of the data points correctly.

In the next segment, you will perform PCA analysis using the pca package of _‘sklearn.decomposition’._