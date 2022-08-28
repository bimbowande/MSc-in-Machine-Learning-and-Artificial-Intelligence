# Matrices

In the previous segment, you learnt about vectors. In this segment, you will learn about matrices. Let’s take the example of patients data set from the previous segment to understand the matrix.

![Vectors Patients](https://i.ibb.co/7yN858Q/Vectors-Patients.png)

As you can see in the table given above, each row can be depicted in the form of a vector (a column matrix), i.e., the vector representation of the data points on an n-dimensional space. 

What if we can represent the vectors of all the points in a single-grouped manner, as shown below?

$$\begin{bmatrix}165&155&165&160&160\\55&71&81&105&94\end{bmatrix}$$

Here, each column represents a vector, and there are five vectors in the form of a matrix.

Let’s hear from Jaidev as he talks about matrices.

**VIDEO**

The features of a matrix can be summarised as follows:

-   A matrix is an ordered collection of numbers, just like a vector.
-   Unlike vectors, matrix has more than one index. It has numbers along its rows and columns. The order of a matrix is defined as:

**Number of rows** × **Number of columns.**

Suppose you have the matrix ‘X’, as shown below.

![Matrix](https://i.ibb.co/4Y6bvJW/Matrices-1.png)

The order of this matrix is **m × n**.

-   A matrix can also be considered a collection of vectors. Let’s take the matrix ‘X’ again. As you can see below, each column of the matrix has a vector such that x1,x2,x3 and so on. So, basically, the matrix ‘X’ is a collection of ‘n’ vectors and each vector has ‘m’ dimensions, as shown below. 
    
    ![Matrix](https://i.ibb.co/v4M2x0r/Matrices-2.png)
    

**Matrix addition operation**

The addition of two matrices (X and Y) can only be performed only if the following condition is fulfilled

**Number of col(X) = Number of col(Y) AND Number of rows(X) = Number of rows(Y).**

#### Matrix Addition

What will be the resultant matrix when you add the matrix ‘A’ and ‘B’?  
  
$A=\begin{bmatrix}1&2\\3&4\end{bmatrix}$,  $B=\begin{bmatrix}1&2&-1\\-2&-5&3\end{bmatrix}$

- $\begin{bmatrix}2&4&-1\\1&-1&3\end{bmatrix}$

- $\begin{bmatrix}1&3&1\\-2&-2&7\end{bmatrix}$

- $\begin{bmatrix}2&2&1\\1&-5&7\end{bmatrix}$

- The matrix cannot be determined. 

Ans: D. *The addition of ‘A’ and ‘B’ cannot be determined, as both matrices have different orders.*

#### Vector Operations

Qn: Suppose you have two vectors, ‘v1’ and v2’. What will be the resultant vector when you multiply ‘v1' with two and subtract it from five times ‘v2’?  
  
$v_1=\begin{bmatrix}2\\1\end{bmatrix}$, $v_2=\begin{bmatrix}-3\\-2\end{bmatrix}$

- $\begin{bmatrix}-11\\-8\end{bmatrix}$

- $\begin{bmatrix}19\\12\end{bmatrix}$

- $\begin{bmatrix}-5\\-3\end{bmatrix}$

- $\begin{bmatrix}-19\\-12\end{bmatrix}$

Ans: D. *Calculate $5(v_2) - 2(v_1)$*

In the next video, you will learn about the multiplication operation of matrices.

**VIDEO**

**Matrix multiplication operation**

The matrix multiplication operation is an ordered operation, which means that A×B is not equal to B×A. Also, two matrices can be multiplied if the number of columns in the first matrix is equal to the number of rows in the second matrix. 

  
The operation AB is only possible if the following condition is fulfilled:

**Number of col (A) = Number of rows (B)**

![Matrix Multiplication Operation](https://i.ibb.co/26VjR7b/Matrix-Multiplication-Operation.png)

As you can see in the image above, if you multiply the 5×4 matrix with the 4×6 matrix, you will get the 5×6 matrix. The multiplication (A×B) occurs when a row of matrix ‘A’ is multiplied by a column of matrix ‘B’.

For example, you will obtain the (1, 1) element of the resultant matrix after multiplying the first row of matrix ‘A’ with the first column of matrix ‘B’.

This brings us to an important aspect of the matrix multiplication: **parallelisation**.

Suppose you have two matrices, ‘A’ and ‘B’, which have the following entries:

$A=\begin{bmatrix}2&3&4\\1&4&5\end{bmatrix}$, $B=\begin{bmatrix}2&3\\5&1\\4&2\end{bmatrix}$

When you multiply the two matrices (A×B), the resultant matrix will have the order 2 × 2. So, basically, you need to multiply the rows of matrix ‘A’ with the columns of matrix ’B’, and if this process occurs serially, then it will take time to compute the multiplication matrix. Similarly, if 

there are thousands/millions of rows and columns, then it will be quite time-consuming to compute the multiplication. 

Therefore, matrix multiplication is a parallel process because all the values in the resultant matrix are independent of one another. Suppose you want to multiply matrix ’A’ with matrix ‘B’. The process multiplying a row of matrix ‘A’ with a column of matrix B is distributed among multiple executors, as shown in the diagram given below.

![Matrix Multiplication Operation Spark Execution](https://i.ibb.co/N3jf4ys/Matrix-Multiplication-Operation-Spark-Execution.png)

Here, the columns of matrix ‘B’ are distributed among two different executors so that they can be multiplied with the rows of matrix ‘A’, and each thread will result into each element of the resultant matrix, i.e., matrix ’R’. Hence, matrix ’R’ will be represented as follows:

$R=\begin{bmatrix}35&17\\42&17\end{bmatrix}$
 
Here, each element in matrix 'R' is obtained parallelly and simultaneously. The concept of parallelism is covered in the previous modules.

#### Multiplication

Qn: Fill in the blank. "If the matrix dimensions of two matrices are given, say, matrix A = a1 x a2 (dimensions) and matrix B = b1 x b2 (dimensions), then the matrix multiplication is valid only if \_\_\_\_\_."

- a1 = b1

- a1 = b2

- a2 = b1

- a2 = b2

Ans: C. *The operation AXB is possible only if the following condition is fulfilled:  
Number of columns (A) = Number of rows (B)*

#### Matrix multiplication

Qn: Suppose you have two matrices, ‘A’ and ‘B’. Now, you multiply the matrix ’A’ with matrix ’B’ and get the resultant matrix ‘R’.

![Matrix Multiplication Question](https://i.ibb.co/kX0F4gM/Matrix-Multiplication-Qn.png)

Now, the matrix ‘R’ has a value of 20. Can you identify which row and column of matrix ‘A’ and matrix ‘B’, respectively, should be multiplied to get the value 20 in matrix ‘R’

- The second row of matrix ‘A’ should be multiplied with the third column of matrix ‘B’.

- The second row of matrix ‘A’ should be multiplied with the second column of matrix ‘B’.

- The first row of matrix ‘A’ should be multiplied with the second column of matrix ‘B’.

- The second row of matrix ‘A’ should be multiplied with the fourth column of matrix ‘B’.

Ans: B. *This is the correct answer. You can get the value 20 by performing the following calculation:*   $3*2 + 4*3 + 1*2 = 20$.

Qn: Suppose you are given a matrix ‘A’, as shown below.  
$$A=\begin{bmatrix}0.6&-0.7\\-0.2&0.4\end{bmatrix}$$
When you multiply matrix ‘A’ with matrix ‘B’ you get the identity matrix ‘I’ whose diagonal entries are 1 and non-diagonal entries are 0, as shown below.
$$I=\begin{bmatrix}1&0\\0&1\end{bmatrix}$$

What is the matrix ‘B’?

- $\begin{bmatrix}-4&7\\2&6\end{bmatrix}$

- $\begin{bmatrix}4&-7\\2&6\end{bmatrix}$

- $\begin{bmatrix}4&7\\2&6\end{bmatrix}$

- $\begin{bmatrix}-4&-7\\-2&-6\end{bmatrix}$

Ans: C. 

#### Vectors

Qn: You are given a vector ‘v’ and a matrix ‘M’ with the following entries:  

$v=\begin{bmatrix}-3\\2\end{bmatrix}$, $M=\begin{bmatrix}2&0\\0&2\end{bmatrix}$

Considering you multiply matrix ‘M’ with vector ‘v’, i.e., **M X v**, what will be the output? (Note: More than one option may be correct.)

- $2v$

- $4v$

- $\begin{bmatrix}-6\\4\end{bmatrix}$

- $\begin{bmatrix}-12\\8\end{bmatrix}$

Ans: A & C. *The multiplication of ‘M’ with ‘v’ will give you the value 2v. Multiply the matrix and the vector using the matrix multiplication rule.*

Qn: You are given a point in terms of vector ‘v’, which lies in II quadrant on the x-y plane, and a matrix ‘M’ with the following entries:  

$v=\begin{bmatrix}-3\\2\end{bmatrix}$, $M=\begin{bmatrix}1&0\\3&-1\end{bmatrix}$

Note:  
I Quadrant: Where both x and y are positive  
II Quadrant: Where x is negative, but y is positive  
III Quadrant: Where both x and y are negative  
IV Quadrant: Where x is positive, but y is negative

Considering you multiply matrix ‘M’ with vector ‘v’, i.e., M X v, in which of the following quadrants will the resultant point lie?

- I

- II

- III

- IV

Ans: C. *When you perform the operation M X v, you get the $\begin{bmatrix}-3\\-11\end{bmatrix}$ vector, which is lying in the III quadrant.*
