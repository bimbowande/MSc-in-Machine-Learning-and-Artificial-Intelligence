# Covariance Matrix

Until now, you have a basic understanding of a matrix and its operations. Let’s now understand a special type of matrix i.e. covariance matrix which is used in the PCA algorithm. 

Let’s take the dummy dataset which we used earlier in which the salary is varying with the age as shown in the figure.

![Salary vs Age](https://i.ibb.co/kg027g8/Salary-vs-Age.png)

![Salary vs Age Graph](https://i.ibb.co/dLPSWYK/Salary-vs-Age-Graph.png)

As you can see that, as the age increases the salary also increases. Can we have a measure to quantify the relationship between the variables? 

To measure the associations between the variables we have covariance. Let’s understand the term covariance and correlation in the next video.

**VIDEO**

Let’s summarise the above video:

-   You already know that the variance is the spread of the data points around its mean, the more variance means that the points are far from the mean of the data points. Or in other words the variance is the tendency to fluctuate the data points around its own mean.
-   The covariance refers to the measure of how two random variables in a data set will change together. 
-   A **positive covariance** means that the two variables are positively related, and they move in the same direction. A **negative covariance** means that the variables are inversely related, and they move in opposite directions.
-   The formula to calculate the covariance between the two variables ‘x’ and ‘y’ is similar to the variance formula:
$$\sigma^2_{xy}=E[(x-\mu_x)(y-\mu_y)]$$
where E is the mean operator.

Now let’s come to the covariance matrix concept. Suppose you have been given a dataset with 3 columns ‘col-1’, ‘col-2’ and ‘col-3’. Can you identify the number of combinations among the three columns of the dataset so that you can find the covariance between them?

The number of combinations is three which are (col-1, col-2), (col-2, col-3) and (col-1, col-3). Also there are three values of variances corresponding to each column in the dataset. If you arrange them in the form of a matrix then this matrix is called the covariance matrix. 

In the covariance matrix- the diagonal entries are the variances corresponding to each variable and the non diagonal entries are the covariance of the variables. One thing you should keep in mind is that the **covariance of ‘$x$’ with respect to ‘$y$’ is the same as the covariance of ‘$y$’ with respect to ‘$x$’.**

So, in the above example, where there are three columns the size of the covariance matrix will be 3X3. You can depict the covariance matrix of ‘n’ column data in the below format:

![Covariance Matrix](https://i.ibb.co/g7XVvck/Covariance-Matrix.png)

As you can see that the covariance matrix is a symmetric matrix along its diagonal because the $\sigma^2_{(x_2,\ x_1)}$ is equal to the $\sigma^2_{(x_1,\ x_2)}$ and so on.

The next concept that you need to understand is the correlation matrix.

The formula to calculate the correlation between ‘x’ and ‘y’  from the covariance is:

$$\rho_{xy}=\dfrac{E[(x-\mu_x)(y-\mu_y)]}{\sigma_x\sigma_y}=\dfrac{\sigma^2_{xy}}{\sigma_x\sigma_y}$$

Where $\sigma_x$ and $\sigma_y$ are the standard deviations of the ‘$x$’ and ‘$y$’ individually. 

Correlation also depicts the dependency between the two variables. But the very basic difference between covariance and the correlation is that:

**'Covariance' indicates the direction of the linear relationship between variables. 'Correlation' on the other hand measures both the strength and direction of the linear relationship between the two variables.** 

The value of the correlation lies between -1 to +1.

-   +1 represents the perfect linear relation between the two variables and if one variable increases then the other variable also increases.
-   -1 represents the perfect linear relation between the two variables but in the opposite sense means, if one variable increases then the other variable decreases.
-   0 correlation represents that there is no linear relationship between the variables.

In this way, you have understood the basic tools like vectors, matrices and covariance matrices. In the next session, you will learn about the basis and the change of basis. Also, you will have hands-on coding to perform the vector and matrix operations in python.

#### Covariance

Qn: Consider the following three graphs:

![Covariance Question](https://i.ibb.co/0YD2whb/Covariance-Qn.png)

Now based on the above graph please qualitatively select the correct options from below:

- Graph- I have a positive and near to 1 correlation.

- Graph- III has 0 correlation as one variable increases the other decreases.

- Graph- II has a negative and near to -1 correlation as no variable is increasing or decreasing if the other variable varies.

- Graph- II has 0 correlation.

Ans: A & D. 

- *As one variable increases the other one also increases hence, there is a positive correlation between the variables.*

- *The last option is correct, as no variable is increasing or decreasing if the other variable varies hence, there is 0 correlation between the variables.*

Qn: Consider the following three graphs:

![Covariance Question](https://i.ibb.co/f4L3YZZ/Covariance-Qn2.png)

Based on the discussion on covariance and correlation, select the correct statements from below.

- The highest correlation of variable-1 with respect to the variable-2 is in graph-III.

- The correlation of variable-1 with respect to the variable-2 is higher than the correlation of variable-2 with respect to the variable-1 in graph-III.

- The least correlation between the variables is in the graph-II.

- The correlation between the two variables is more positive in graph-I as compared to graph-III.

Ans: A & C. 

- *There is a highest linear relation between the variables in graph- III hence, the highest correlation of variable- 1 with respect to the variable-2 occurs in graph- III.*

- *The least linear relationship between the variables occurs in graph-II only hence, the correlation is least in graph-II.*
