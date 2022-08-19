# Graded Questions

#### Graded Question

Qn: Which axis captures more variance in the following plot between Age and Weight?

![Graded Question - Age vs Weight](https://i.ibb.co/CPSs75C/Graded-Question-1.png)

- Age

- Weight

- Both carry equal variance.

Ans: A. *When the farthest points of the data are projected on the axis, the length of the projection becomes proportional to the variance. In the given image, the length of the projection of the farthest points of data on the Y-axis is more than the length of the projection on the X-axis.*

Qn: Assume there is a dataset which has three numerical columns in it. When you plot the scatter plot of this dataset in 3 - dimensional space, then you get a scatter plot in which points are uniformly distributed in the volume of the sphere. Also if you see the percentage of variance in each column then it comes out to be 33.33% for each column.  
Now based on the above scenario can you select the correct option from below?

- You can’t find the new axes where you can maximise the variance in one axis.

- The original axes act as the principal component here because the data is uniformly distributed and each axis has 33.33% of the variance.

- If you shift the origin to the centre of the sphere without aligning the axes then you can maximise the variance in one particular direction.

- Both A and B.

Ans: D.

Qn: PCA is a method used to reduce the number of variables in your data by extracting important features from a large pool. It reduces the dimension of your data with the aim of retaining as much information as possible. In other words, this method combines highly correlated variables together to form a smaller number of an artificial set of variables which is called “principal components” that account for most variance in the data.

  
Suppose you plot the cumulative percentage of variance that each PC (total 70 PCs) contains in it. What are the optimum number of principal components that can be used for an analysis from the below figure?

![Graded Question - Cumulative Percentage of Variance of each PC](https://i.ibb.co/L8vS32y/Graded-Question-2.png)

- 10

- 30

- 40

- 70

Ans:B. *We can see in the above figure that the number of components = 30 is giving the highest variance with the lowest number of components. After 30 , it seems more or less to be constant Hence this option is the right answer.*

Qn: What is the order in which you’ll multiply the four matrices A, B, C, D given the following dimensions?  
The dimension of A is 3X4  
The dimension of B is 5X6  
The dimension of C is 6X10  
The dimension of D is 4X5

- $A * C * B * D$

- $B * C * D * A$

- $A * D * B * C$

- $C * C * B * A$

Ans: C. *This is the correct sequence of multiplication and the final order of the resultant matrix will be 3x10.*
