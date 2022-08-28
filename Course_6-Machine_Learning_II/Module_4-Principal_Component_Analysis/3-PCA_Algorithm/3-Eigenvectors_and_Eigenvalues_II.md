# Eigenvectors and Eigenvalues- II

In the previous segment you have revised a very important concept of transformation of a vector by multiplying the vector with a particular matrix.

Now in this segment, you will learn about the eigenvectors and eigenvalues. Let’s start the segment with the next video.

**VIDEO**

Let’s assume a transformation matrix ‘A’, which is shown below.

$A=\begin{bmatrix}3&1\\0&2\end{bmatrix}$

Note: In the x–y plane, the unit magnitude vectors in the direction of the x and y axes are simply denoted by ‘^i’ and '^j', respectively, which can be represented in matrix form as shown below:

$\hat{i}=\begin{bmatrix}1\\0\end{bmatrix}$ and  $\hat{j}=\begin{bmatrix}0\\1\end{bmatrix}$

Now, suppose you have two vectors ‘x’ and ‘^i’, as shown below:

$x=\begin{bmatrix}-1\\1\end{bmatrix}$ and  $\hat{i}=\begin{bmatrix}1\\0\end{bmatrix}$

Let’s transform these two vectors using the transformation matrix ‘A’ and examine what the new transformed vectors would be in this case:

$Ax=\begin{bmatrix}3&1\\0&2\end{bmatrix}\begin{bmatrix}-1\\1\end{bmatrix}=\begin{bmatrix}-2\\2\end{bmatrix}=2\begin{bmatrix}-1\\1\end{bmatrix}$ and $A\hat{i}=\begin{bmatrix}3&1\\0&2\end{bmatrix}\begin{bmatrix}1\\0\end{bmatrix}=\begin{bmatrix}3\\0\end{bmatrix}=3\begin{bmatrix}1\\0\end{bmatrix}$

An interesting point that you should note here is that when you transform the ‘x’ and ‘^i’ vectors using the matrix ‘A’, you get new vectors that are simply the scaled vectors of the original vectors, or, in other words, the transformed vectors are parallel to the original vectors. At the same time when you transform the ‘x’ and ‘^i’  vectors using the transformed matrix ‘A’, you get the vectors, ‘2x’ and ‘3^i’, respectively. 

So, in this case, multiplying the vectors ‘x’ and ‘^i’ with the matrix ‘A’ has the same effect as simply multiplying them by the scalars 2 and 3 respectively.

Hence, the vectors ‘x’ and ‘^i’ are called the eigenvectors of matrix ‘A’, and the scalars ‘2’ and ‘3’, respectively, by which these vectors get scaled are called the eigenvalues of matrix ‘A’.

  
In linear algebra, an eigenvector of a linear transformation (or a square matrix) is a non-zero vector that changes at most by a scalar factor when that linear transformation is applied to it. The corresponding eigenvalue is the factor by which the eigenvector is scaled.

Please note that we are not introducing the mathematical calculation to find out the eigenvectors and eigenvalues of a particular matrix. If you understand the fundamentals of the eigenvectors and eigenvalues, then it would be quite easy for you to understand the calculation of eigenvectors and eigenvalues.

Now, in the next video, you will learn about the properties of eigenvectors.

**VIDEO**

#### Transformation Matrix

Qn: What will be the eigenvectors (v1 and v2) of a 2X2 matrix ‘M’ that rotates any vector by an angle of 90 degree counterclockwise.

- The eigenvectors came out to be real vectors.

- The eigenvectors came out to be imaginary vectors.

- Can not be determined.

Ans: B. *The eigenvectors of the matrix ‘M’ will be imaginary. Try to find out the eigenvectors using the following line of codes.*

```python
M= [[0, -1], 
        [1, 0]]
np.linalg.eig(M)
```

So, let’s list down some of the interesting properties of eigenvectors:

-   Eigenvalues and eigenvectors of a given matrix always occur in pairs
-   Eigenvalues and eigenvectors are defined only for square matrices, and it is not necessary that they will always exist. This means there could be cases where there are no eigenvectors and eigenvalues for a given matrix, or, in other words, there exist imaginary eigenvectors and eigenvalues.

#### Eigenvectors and Eigenvalues

Qn: Suppose you have a square matrix. The number of eigenvectors of this matrix would be the same as the order of the matrix.

- True

- False

Ans: A. *The number of eigenvectors and the number of eigenvalues are the same as the order of the square matrix.*

In the next segment, you will learn how to diagonalise a matrix.

**Additional reading**

You can refer to the additional reading links given below to know more about the calculation of eigenvectors and eigenvalues.

[Eigenvectors and eigenvalues-1](https://www.youtube.com/watch?v=PFDu9oVAE-g)

[Eigenvectors and eigenvalues- 2](https://www.mathsisfun.com/algebra/eigenvalue.html)
