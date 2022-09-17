# Matrix Operations - I

In the previous section, you learnt the basics of matrices, how to create them, and some terminology related to them. In this section, we will revisit some basic matrix operations (addition, multiplication, etc.). If you are already familiar with these, you can just skim through the page.

## Matrix Addition

Adding two matrices simply means to add the individual entities **element-wise**, that is, to add up the corresponding i, j elements of both the matrices.

For example, if we have the following two matrices, 
$$\large{A=\begin{bmatrix}4&2&3&2\\3&1&5&4\\1&8&1&2\end{bmatrix},\ B=\begin{bmatrix}6&2&8&9\\2&6&8&1\\0&3&0&2\end{bmatrix}}$$

Then their sum (A + B) would be equal to:
$$\large{A=\begin{bmatrix}10&4&11&11\\5&7&13&5\\1&11&1&4\end{bmatrix}}$$
 Note that **not all matrices can be added to each other.** Since the addition is done element-wise, you can only add matrices that have the **same dimensions**, i.e. the exact same number of rows and columns. Also, the matrix that you get by adding two m x n matrices will also be an m x n matrix.

## Matrix Multiplication

For a quick recap of matrix multiplications, you can watch the following videos.

## Video

Here are some videos, courtesy Khan Academy, that talk about matrix multiplication. If you already know this, so you skip the videos and move ahead - the important points are summarized in the text.

- [Matrix multiplication - Part 1](https://www.youtube.com/watch?v=aKhhYguY0DQ)
- [Matrix multiplication - Part 2](https://www.youtube.com/watch?v=OAh573i_qn8)

Let's now summarize what you learned in these videos.

Firstly, note that **not all matrices can be multiplied with each other.** For the matrix multiplication AB to be valid, the **number of columns in A** should be equal to the **number of rows in B.** In other words, if you have two matrices **A** and **B** with the dimensions (a1,a2) and (b1,b2) respectively. Then:

- AB exists if and only if a2=b1
- BA exists if and only if b2=a1

For example, the following examples show a valid and an invalid multiplication. You **can** multiply a (3x2) matrix with a (2x3) matrix, but you **cannot** multiply a (3x2) matrix with a (3x2)
matrix:
$$\large{\begin{bmatrix}4&2\\3&2\\4&5\end{bmatrix}*\begin{bmatrix}5&4&10\\3&2&9\end{bmatrix}\ -\ ✓}$$ $$\large{\begin{bmatrix}4&3&4\\2&2&5\end{bmatrix}*\begin{bmatrix}5&4&10\\3&2&9\end{bmatrix}\ -\ ╳}$$
In machine learning problems, even though the actual matrix multiplications will be almost always done by libraries (such as Numpy), it is extremely helpful to check that the sizes of your inputs and outputs are what you expect them to be. For example, if you have two large arrays of sizes (1000, 1500) and (1500, 3000), you should verify that the product is of shape (1000, 3000). These 'sanity checks' help you in verifying that the code you are writing does not contain any mistakes.

The **matrix multiplication process** can be broken down into computing vector dot products - the (i, j) element of the output matrix is the **dot product** of the **ith row** of the first matrix and the **jth column** of the second matrix.

![Matrix Dot Product](https://cdn.upgrad.com/UpGrad/temp/ba27becc-c0c1-40bf-bee4-4b7a55252b53/11.png)


For example, if: 
$$\large{A=\begin{bmatrix}2&3\\4&0\end{bmatrix},\ B=\begin{bmatrix}1&2&0\\5&-1&0\end{bmatrix}}$$
then A∗B is given by:
$$A*B=\begin{bmatrix}2&3\\4&0\end{bmatrix}*\begin{bmatrix}1&2&0\\5&-1&0\end{bmatrix}=\begin{bmatrix}17&1&0\\4&8&0\end{bmatrix}$$
Also, note that A∗B is not necessarily equal to B∗A, i.e. **matrix multiplication is not commutative.**

#### Matrix Addition

Consider the following two matrices:
$$A=\begin{bmatrix}3&2\\0&3\end{bmatrix},\ B=\begin{bmatrix}4&-2\\2&-3\end{bmatrix}$$
Qn: What is the result of the sum of the matrices?
- $A+B=\begin{bmatrix}7&0\\2&0\end{bmatrix}$

- $A+B=\begin{bmatrix}7&2\\0&0\end{bmatrix}$

- $A+B=\begin{bmatrix}12&-4\\0&-9\end{bmatrix}$

- $A+B=\begin{bmatrix}7&-2\\2&0\end{bmatrix}$

Ans: A. *This is the matrix that results from adding all the individual values in equivalent positions of the two matrices. $A+B=\begin{bmatrix}7&0\\2&0\end{bmatrix}$.*

Qn: What's the result of the product of the two matrices?

- $A*B=\begin{bmatrix}12&-16\\-6&-9\end{bmatrix}$

- $A*B=\begin{bmatrix}16&-12\\6&-9\end{bmatrix}$

- $A*B=\begin{bmatrix}6&-12\\6&9\end{bmatrix}$

- $A*B=\begin{bmatrix}-16&12\\0&9\end{bmatrix}$

Ans: B. *For position \[i, j], the value will be equal to the dot product of row 'i' of A and column 'j' of B. $A*B=\begin{bmatrix}16&-12\\6&-9\end{bmatrix}$*

## Matrix Operations in Numpy

You can use the **np.dot()** method to do matrix multiplication in Numpy, as shown below. To add two matrices A and B, you can simply use A+B:

```python
import numpy as np

A = np.array([[1, 2], 
             [2, 0]])
B = np.array([[0, 1], 
             [-1, 2]])

# matrix addition
print(A+B)

# matrix product
print(np.dot(A, B))
```
