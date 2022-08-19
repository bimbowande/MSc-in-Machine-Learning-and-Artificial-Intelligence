# Introduction to PCA -II

In the previous segment, you learnt that PCA is fundamentally a dimension-reduction technique. In this segment, you will learn how to get the projected data points on the newly created axes, i.e., PC1 and PC2.

**VIDEO**

So, in the previous segment, you saw how you can rotate the axes graphically to get the maximum variance and the minimum covariance between the variables.

In the video above, you saw how you can get the new data points using the transformation matrix. Note that your main concern is to find the difference between the covariance matrix of the two data sets, not how you get the transformation matrix. You will learn about this matrix later in the module.

The original data set and the transformed dataset have the following covariance matrices, respectively:

$$\begin{bmatrix}386.27 & 447.22 \\ 447.22 & 750.57\end{bmatrix}$$

$$\begin{bmatrix}2.396 & -1.48367e^{-10} \\ -1.48367e^{-10} & 0.00395\end{bmatrix}$$

Note: There is a dedicated segment on the calculation of the covariance matrix in the latter part of this session. Hence, here you need to only understand that the value of covariance shows how much two variables are linearly correlated with each other.

The following points can be observed from the two covariance matrices given above:

-   The first covariance matrix is corresponding to the original data set. As you can see in this covariance matrix, the values of variance in the Salary and Age columns are 386.27 and 750.57, respectively. Both the values of variance are high, which means that both variables are relevant. Also, the values of covariance between the variables are 447.22, which means that salary and age variables are highly correlated with each other which will create problems in modelling.
-   On the other hand, in the covariance matrix of PC1 and PC2 (which are the projected points of the original data points on the new axes), you will notice that there is high variance (99.8%) in PC1 and negligibly small variance (0.8%) in PC2. 
-   There is almost zero covariance between PC1 and PC2.

Let’s watch the next video to understand exactly what the PCA algorithm does.

**VIDEO**

As you learnt in the video above, PCA converts possibly correlated variables into new features that are known as ‘Principal Components’ in such a way that:

-   They are uncorrelated with each other,
-   They are the linear combinations of the original variables, and
-   They capture maximum information in the data set.

Note that the number of principal components is the same as that of the columns in the data set. PCs are sorted in descending order of information content. For example, if you have a data set with four columns, then you will get four PCs, and the first PC will have the maximum variance, the second PC will have the second maximum variance and so on.  
 

![Principal Components and Variables](https://i.ibb.co/HX8PVMY/Principal-Components-and-Variables.png)

As you can see in the image above, the original data set contains four variables with significant variance in each variable. Once you find the PCs of this data set, you can get most of the variance (around 92% of the information) in the top two PCs. So, you can discard PC3 and PC4, which would lead to dimensionality reduction in the dataset without losing too much of the information. Note that this can change with the use case. In case you need to capture 100% variance, you would use all the 4 features.

#### PCA

Qn: Consider the scatter plot given below, and select the best possible principal component for the distribution out of the red, green and blue lines.

![PCA Question](https://i.ibb.co/JmR8vZ4/PCA-Question.png)

- Red

- Green

- Blue

Ans: C. *This is the correct principal component, as it is aligned in the direction that captures the maximum variance in the data set as compared with the other two lines.*

This simple manipulation helps in the following ways:

-   Data visualisation and EDA: It helps in data visualisation and EDA because you have few variables in the data set that carry maximum information. Plotting the scatter plot of two variables is easier than analysing multiple variables at a time.
-   The predictive model set-up: When there are many correlated features in a data set, it leads to the problem of multicollinearity. Removing features iteratively is time-consuming and also leads to information loss.
-   For creating uncorrelated features that can be input to a prediction model: With fewer uncorrelated features, the modelling process can be faster and more stable.

  
Now, the aforementioned definition introduces some new terms and phrases, such as **‘linear combinations’** and **‘capturing maximum information’.** To understand these phrases and terms, you need to have some knowledge of linear algebra concepts along with **vectors and matrices,** which are the building blocks of PCA. In the next segment, you will be introduced to vectors and matrices.

You may feel that we are diverting from our main discussion on PCA while learning about vectors and matrices. However, it is extremely important to understand vectors and matrices before moving on to the PCA algorithm. 

#### PCA

Qn: When can (or should) you use PCA?

- When the attributes of your data are highly correlated

- When better data visualisation is possible using fewer dimensions

- When the number of dimensions needs to be reduced

- All of the above

Ans: D.

#### Multicollinearity

Qn: Which of the following statements regarding multicollinearity is **not true**?

- Multicollinearity generally occurs when the correlations between two or more predictor variables are high.

- In the case of multicollinearity, some of the predictor variables can be used to predict some other predictor variables.

- The multicollinearity between the variables can be detected by calculating the correlation coefficients of the variables. 

- Multicollinearity helps in better convergence of a regression problem.

Ans: D. *Multicollinearity leads to incorrect estimates of the model parameters. Hence, it does not help in better convergence of a regression problem*

#### PCA

Qn: Which of the following regarding PCA is true?

- Principal component analysis is an unsupervised technique.

- Principal components are the linear combinations of original variables.

- Principal components are constructed to capture the maximum information using independent features

- All of the above

Ans: D.