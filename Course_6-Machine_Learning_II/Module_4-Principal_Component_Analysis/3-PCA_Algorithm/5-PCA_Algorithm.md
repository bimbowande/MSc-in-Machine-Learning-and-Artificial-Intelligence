# PCA Algorithm

In this segment, you will apply all your learnings gathered so far and understand the PCA algorithm.

But first, let’s revise the points given below, which form the basis of the PCA algorithm. 

PCA converts possibly correlated variables to ‘Principal Components’ such that:

-   They are uncorrelated to each other.
-   They are linear combinations of the original variables.
-   They capture maximum information in the data set.

The uncorrelated features can be obtained only when you diagonalise the covariance matrix.

Now, let’s watch the upcoming video and learn about the PCA algorithm.

**VIDEO**

Let’s summarise the steps of PCA algorithm one-by-one:

-   Suppose you have an original data set with **‘M’ rows and ‘N’ columns**. Then you will have a **covariance matrix of order ‘N X N’** for this data set.
-   After getting the covariance matrix for the data set, find its eigenvectors, which will be the new basis vectors.
-   Once you have obtained the eigenvectors, simply arrange them in the form of a matrix. This eigenvector matrix will be the **‘change of basis matrix’**.
-   After getting the **‘change of basis matrix’**, multiply each data point in the original basis system with the inverse of **‘change of basis matrix’** to get the new data points in the **eigenvector basis system.**
-   In this way, you represent all the data points of the original basis system in the eigenvector basis system so that you can obtain the uncorrelated features as the covariance matrix has now been diagonalised. 

One point that you should remember is that the **‘eigenvectors of the covariance matrix are the new directions in which you represent the data in order to get uncorrelated features; or, in other words, the eigenvectors are the new principal components’.**

So, if you look back at where we started our discussion on PCA using the ‘Salary’ and ‘Age’ example.

![PCA Rotation of Axis](https://i.ibb.co/HY7tSBZ/PCA-Rotation-of-Axis.png)

You find the maximum variance along the blue axis, The blue and the green lines are nothing but the eigenvectors of the covariance matrix.

The image given below summarises the PCA algorithm:

![PCA Algorithm](https://i.ibb.co/8zHSxqc/PCA-Algorithm.png)

In the next two segments, you will see hands-on coding demonstrations of the PCA algorithm using Python and Spark.

#### PCA

Choose the correct statement(s) from the options given below:

1.  The PCA algorithm needs the data to be highly correlated to work properly.
2.  The PCA algorithm does not need the data to be highly correlated to work properly, although PCA is necessary and becomes useful only when the data is highly correlated.

- 1

- 2

- Both 1 and 2

- None of the above

Ans: B. *PCA is a technique that is used to convert correlated features to uncorrelated features. Hence, whether or not PCA needs highly correlated data is of no consequence.*

Qn: You are given a data set that has 540 unique variables (n). Based on this information, which of the following options shows the correct number of principal components (k) that are chosen for the final model?

1.  539
2.  345
3.  565

- 1

- 2

- 1, 2

- 1, 2, 3

Ans: C. *Number of principal components (k) <= Number of variables (n).*

Qn: Refer to the following statements:  
a. Find the eigenvectors of the covariance matrix  
b. Find the covariance matrix of the data set  
c. Find the inverse of the eigenvector matrix  
d. Normalize and standardise the data points  
e. Arrange the eigenvectors in a matrix (eigenvector matrix) in decreasing order of the corresponding eigenvalues  
f. Multiply each original data point with the inverse of the eigenvector matrix  
   
Arrange the statements in the correct order of the steps in PCA.  
 
- d, b, c, e, a, f

- a, e, c, f, d, b

- f, d, b, a, e, c

- d, b, a, e, c, f

Ans: D.
