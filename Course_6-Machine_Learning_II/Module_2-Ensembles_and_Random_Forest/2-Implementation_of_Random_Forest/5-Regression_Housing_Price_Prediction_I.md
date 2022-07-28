# Regression: Housing Price Prediction - I

In the previous segment, you learnt how to use the random forest model to build a classification model. Now, you will learn how to run a regression model using the random forest. For this, you will use the housing data set to predict house prices based on various factors such as area, number of bedrooms and parking space, which you have already seen in the previous modules. Let's first understand the problem statement.

You can download the data set and the Python code file given below.

Download [Housing Data](Housing.csv)

Download [Random Forest Regression Python](RF_Housing_Case_Study.ipynb)

With this, let's move on to understanding the problem statement and loading the data set.

**VIDEO**

The aims of this problem statement are as follows:

-   Know the variables that significantly contribute to predicting house prices
-   Create a random forest regressor that quantitatively relates house prices with variables, such as area, the number of rooms, and number of bathrooms

Now that you have understood the problem and loaded the data set, the next step is to explore the data set and visualise the numerical and categorical variables. We will do this with the help of a pair plot.

**VIDEO**

In the previous video, we used the pairplot function to visualise all the numeric variables. In the next video, we will visualise the categorical variables.

**VIDEO**

Now that you have read and inspected the data, let's move on to visualising it. It will help in interpreting the data well and identifying the variables that can turn out to be useful in building the model.

Now that you have enough understanding of the data, the next step involves the preparation of data for applying the regression problem. Let's take a look at it in the next segment.

#### Missing values

Qn: How would you deal with the missing values in the case of housing price data set?

- Imputation of missing values

- Deleting the rows

Ans: A. *You must use the imputation method as you are working with a very small data set. Hence, you cannot afford to lose any data point.*