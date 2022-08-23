# Diagonalisation of a Covariance Matrix

So, in the previous segment, you learnt about eigenvectors and eigenvalues. Now, in this segment, you will learn about the application of eigen discussion to diagonalise a covariance matrix using eigenvectors.

But first, you will need to have an understanding of what is actually meant by diagonalisation of a covariance matrix.

In the very first session of this module, you saw the following data set and its covariance matrix:

![Sample Dataset and Covariance Matrix](https://i.ibb.co/5T6YNLr/Sample-Dataset-and-Covariance-Matrix.png)

In the first table, the value of covariance is quite high, which means ‘Salary’ and ‘Age’ are correlated with each other. But when you represent the same data in a new basis system, you get newly transformed data. 

Using these new transformed data points, the value of the covariance is found to be negligible, which is, almost zero, and the variance is distributed in such a way that PC1 has the highest variance (or information), 2.396, PC2 has the next highest variance, 0.00395.

So, when the diagonal elements of a covariance matrix become 0, it is called a diagonalised covariance matrix. A diagonalised covariance matrix represents non-correlated features, which is the requirement we need to fulfil using PCA.

**So, basically, our task is to transform each original data point to a new basis system such that the covariance matrix of the transformed data set becomes a diagonal matrix in the new basis system.**

So, in the process of diagonalisation of the covariance matrix, or, in general, a matrix, the eigenvectors and eigenvalues play a very magical role. Let’s watch the upcoming video and try and understand the role of eigenvectors, and learn how they are useful in diagonalising a given matrix.

**VIDEO**

There are a lot of transformations performed in the above video. Let’s try to understand these step by step.

Suppose there is a matrix ‘A’, which has ‘$v_1$’ and ‘$v_2$’ eigenvectors, and ‘$\lambda_1$’ and ‘$\lambda_2$’ eigenvalues, as shown below:

$A=\begin{bmatrix}3&1\\0&2\end{bmatrix}$

Eigenvectors:   $v_1=\begin{bmatrix}1\\0\end{bmatrix}$ and  $v_2=\begin{bmatrix}-1\\1\end{bmatrix}$

Eigenvalues:  $\lambda_1=3$,   $\lambda_2=2$

Let’s define the eigenvector and eigenvalue matrices, ‘V’ and ‘Λ’, respectively, as shown below:

$V=\begin{bmatrix}1&-1\\0&1\end{bmatrix}$,   $\Lambda=\begin{bmatrix}3&0\\0&2\end{bmatrix}$

When you multiply matrix ‘A’ with matrix ‘V’, you get the same results as when you multiply matrix ‘V’ with matrix ‘Λ’:

$AV=V\Lambda$

When you **right multiply** both sides of the equation above with inv(V), you will get the following result:

$A=V\Lambda*V^{−1}$

Or when you **left multiply** both sides of that same equation, you get the following result.

$V^{−1}AV=\Lambda$

Now, if you see this equation, matrix ‘Λ’ is nothing but a diagonal matrix whose non-diagonal entries are simply 0.

So, based on the analysis above, you can state that:

**Both A and 𝚲 represent the same linear transformation but in different basis vectors (i.e., original basis and eigenvector basis, respectively).** 

Let’s try and understand the statement above.

Consider you have an original basis, i.e., x–y plane, and you have a vector ‘x’ in the same basis. Also, you have a transformation matrix ‘A’ as shown below:

  
$x=\begin{bmatrix}-1\\2\end{bmatrix}$,   $A=\begin{bmatrix}3&1\\0&2\end{bmatrix}$

When you transform the same vector ‘x’ using the transformation matrix ‘A’, you get the following result:

$Ax=\begin{bmatrix}-1\\4\end{bmatrix}$

Now, suppose you want to represent vector ‘$x$’ in a new basis system – which is supposed to be an eigenvector basis this time – which means you need to represent vector ‘$x$’ as a linear combination of the eigenvectors of matrix ‘A’. You can represent the linear combination as follows:

The eigenvectors of ‘A’ are:

$v_1=\begin{bmatrix}1\\0\end{bmatrix}$ and  $v_2=\begin{bmatrix}-1\\1\end{bmatrix}$

Therefore, 

Let’s represent the ‘x’ in terms of a linear combination of eigenvectors.

$x=\begin{bmatrix}-1\\2\end{bmatrix}=1\begin{bmatrix}1\\0\end{bmatrix}+2\begin{bmatrix}-1\\1\end{bmatrix}=\begin{bmatrix}1&-1\\0&1\end{bmatrix}\begin{bmatrix}1\\2\end{bmatrix}$

$\begin{bmatrix}1\\2\end{bmatrix}=\begin{bmatrix}1&-1\\0&1\end{bmatrix}^{−1}\begin{bmatrix}1\\2\end{bmatrix}$

$\begin{bmatrix}1\\2\end{bmatrix}=V^{−1}x$

$x'=V^{−1}x$

**This means point x(-1, 2) can be represented as x'(1, 2) in the eigenvector basis and the change of the basis matrix will be ‘$V^{−1}$’. This is one of the key steps in understanding PCA.** Using this, we shall proceed to prove that A and lambda are transformation matrices in the 2 basis.

$V^{−1}=\begin{bmatrix}1&-1\\0&1\end{bmatrix}^{−1}$

Now, think the other way around: suppose you have vector **x'** in an eigenvector basis and you want to calculate the transformed vector in a new eigenvector basis, **A'x'**, which corresponds to the transformed matrix **‘A**’ in the original basis. To do this, you first need to convert **x'** to **x**, and then x to **Ax**, and finally convert Ax to an eigenvector basis system.

So let’s convert **x'** to **x** first, as shown below:

$x=Vx'$

Now, let’s apply the transformation to **x**, i.e. ‘**Ax**’:

$y=Ax=AVx'$

Now, let’s convert ‘**y**’, which is ‘**Ax**’, to an eigenvector basis again, that is, **y'**:

$y'=V−1y=V−1AVx'$

Or, in other words:

$y'=\Lambda x'$  because  $\Lambda=V^{−1}AV$

**So, as you can see here, A' comes out to be ‘Λ’, which is the transformation matrix in the new basis system, and ‘Λ’ is a diagonal matrix.**

You can refer to the following summary image to understand the process better.

![Eigenvector Transformation](https://i.ibb.co/HXhzVXR/Eigenvector-Transformation.png)

![Eigenvector Transformation](https://i.ibb.co/X547PSx/Eigenvector-Transformation2.png)

**Therefore, we can say that both A and 𝚲 represent the same linear transformation but in different basis vectors (i.e., original basis and eigenvector basis, respectively).**

**Or, in other words, you can diagonalise matrix ‘A’ by representing it in a new eigenvector basis system, because matrix ‘A’ will become ‘Λ’ in the eigenvector basis system.** 

Now let’s try to understand the above concept for the covariance matrix-

**VIDEO**

What if matrix ‘A’ is the covariance matrix of the data set in the original basis; for example, let’s consider the following data set: 

![Salary vs Age](https://i.ibb.co/kg027g8/Salary-vs-Age.png)

The covariance matrix of this data set would be:
$$\begin{bmatrix}386.27&447.22\\447.22&750.57\end{bmatrix}$$
Now, when you apply the following operation on the covariance matrix, you will get a diagonalised covariance matrix, as shown below: 

Diagonalised Covariance Matrix: $V^{−1}AV$

Here, ‘V’ is the eigenvector matrix.

**Thus, a very important point that you have learnt here is that you can diagonalise a covariance matrix only when you represent the data points in an eigenvector basis system.**

**Eigendecomposition of a covariance matrix:** Eigendecomposition of the covariance matrix is nothing but finding the eigenvectors of the covariance matrix so that you can represent all the data points of the original basis system in the eigenvector basis system.

  
In this way, you have learnt the overall concept of the PCA algorithm. So, the overall algorithm of PCA can be summarised in the following way:

-   The original data points may not be uncorrelated to each other  and hence one of the ways to tackle this problem is to drop the least significant column. The other way is to generate the new features, the PCs which are uncorrelated to each other. Hence, you first calculate the covariance matrix of the original data points and try to diagonalise it which means that they should have near to zero covariance.
-   The diagonalization of the covariance matrix happens when you represent all the original data points in the eigenvector basis. 
-   The eigenvalues along the diagonal will be of the covariance matrix of the original data points.

In the next segment, you will apply all the conceptual learnings gathered so far and understand the PCA algorithm.

**Comprehension:**

Suppose you have a matrix ‘A’ whose eigenvectors are as follows:
$$v_1=\begin{bmatrix}2\\-3\\1\end{bmatrix},\ v_2=\begin{bmatrix}2\\-1\\1\end{bmatrix}\ and,\ v_3=\begin{bmatrix}1\\6\\16\end{bmatrix}$$
Following are the eigenvalues of the matrix:
$$\lambda_1=-5,\ \lambda_2=3\ and,\ \lambda_3=6$$
When you multiply the transformation matrix ‘A’ with a vector ‘**a**’, it gives you a vector ‘**b**’ in the x–y plane. Suppose there is a vector **a**' in the eigenvector basis system that corresponds to vector **a** in the x–y plane, and, in the same way, there is a vector **b'** in the eigenvector basis system that corresponds to vector b in the x–y plane. 

Now based on the above scenario, try to answer the following questions.

#### Diagonalization

Qn: The diagonalised matrix corresponding to matrix ‘A’ is matrix ‘B’:

$B=\begin{bmatrix}-5&0&0\\0&3&0\\0&0&6\end{bmatrix}$

Select whether the statement above is true or false.

- True

- False

Ans:A. *The statement is true since the representation of the transformation matrix ‘A’ in an eigenvector basis system will be a diagonalised matrix, which will be the eigenvalue matrix of the transformation matrix ‘A’.*

Qn: What would be the change of basis matrix if you want to obtain **a'** from **a** in the x–y plane?

- $\begin{bmatrix}2&2&1\\-3&-1&6\\-1&1&16\end{bmatrix}$

- $\begin{bmatrix}2&2&1\\-3&-1&6\\-1&1&16\end{bmatrix}^{-1}$

- $\begin{bmatrix}-5&0&0\\0&3&0\\0&0&6\end{bmatrix}^{-1}$

- $\begin{bmatrix}-5&0&0\\0&3&0\\0&0&6\end{bmatrix}$

Ans: B. *The inverse of the eigenvector matrix will be the change of basis matrix in this case.*

Qn: What would be the transformation matrix to get vector **b'** from vector **a**' in an eigenvector basis system?

- $\begin{bmatrix}2&2&1\\-3&-1&6\\-1&1&16\end{bmatrix}$

- $\begin{bmatrix}-5&0&0\\0&3&0\\0&0&6\end{bmatrix}^{-1}$

- $\begin{bmatrix}-5&0&0\\0&3&0\\0&0&6\end{bmatrix}$

- $\begin{bmatrix}2&2&1\\-3&-1&6\\-1&1&16\end{bmatrix}^{-1}$

Ans: C. *Matrix A and Cap(lambda) represent the same transformation but in a different basis, the eigenvector basis.*

Qn: Select the correct statements from the options given below. Multiple options can be correct.

- Diagonalisation of a covariance matrix is possible in its eigenvector basis system.

- The eigenvectors of a covariance matrix are the new basis system in which you need to represent all the data points in order to get the uncorrelated features.

- The data points in the eigenvector basis system will be linear combinations of the original data points.

Ans: All of the Above.

- *As you learnt in the theory part, diagonalisation of a matrix is possible in its eigenvector basis system.*

- *If you represent all the data points in the eigenvector basis system, then the covariance matrix that you obtain from these newly created data points will constitute the diagonalised covariance matrix.*
- *The points in the eigenvector basis system are linear combinations of the original data points as you are simply performing matrix multiplication with the data point vector.*
