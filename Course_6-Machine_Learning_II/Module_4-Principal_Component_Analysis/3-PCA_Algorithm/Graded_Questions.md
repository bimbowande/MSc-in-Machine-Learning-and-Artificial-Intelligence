# Graded Questions

#### Graded questions

Qn: Which of the following principles is NOT a building block of principal component analysis?

- Covariance matrix

- Eigenvectors

- Non - Collinearity of principal components

- Non-linear dependence of principal components on the original data points

Ans: D. *The principal components are linearly dependent on the original data points.*

Qn: In which of the following options is the application of PCA justified as well as useful?

1. 95% of the variance was explained by 10 PCs when PCA was applied on a data set containing 25 variables.

2. 75% of the variance was explained by 23 PCs when PCA was applied on a data set containing 25 variables.

3. 90% of the variance was explained by 10 PCs when PCA was applied on a data set containing 25 variables.

- 1 and 3

- 1 and 2

- 1, 2 and 3

- 3

Ans: A. *In the first option, maximum variance, which is about 95%, is explained by the 10 PCs. Therefore, it is justified to use 10 PCs instead of 25 variables. Also, in the third option, the maximum variance, which is about 90%, is explained by the 10 PCs, and, hence, it is also justified to use 10 PCs instead of 25 variables.*

For the next exercise, you have been given a ‘housing’ data set, which contains a total of 16 columns, which are related to different aspects of houses, such as price, area of house, number of bedrooms, number of bathrooms, average area per bedroom etc.

Download [Housing dataset](newhousing.csv)

Based on the given data set, you need to answer the following questions, which are related to PCA analysis in Python for this data set.

#### Graded questions

Qn: Which of the following pairs of independent variables has the highest covariance?

- Number of bathroom and bbratio

- Number of bedrooms and number of stories

- area of house and area per bedroom

- parking and area of house

Ans: C. *The maximum covariance is between area of house and area per bedroom, which is 0.80, and you can find out this covariance after the normalisation step:*

```python
# read the data in dataframe.
housing = pd.read_csv('newhousing.csv')

#Normalization of the dataset.
x_centered = housing - housing.mean(axis=0)
x_scaled = x_centered / x_centered.std(axis=0)
print("Column-wise mean", x_scaled.mean(axis=0))
print("Column-wise variance", x_scaled.var(axis=0))

#convert the array into dataframe.
df = pd.DataFrame(x_scaled)

#calculate the covariance matrix of ‘df’
df.cov()
```

Qn: What is the range of percentage of maximum variance that can be explained by a single PC (i.e., PC0)?

- Less than 70% of the variance

- Greater than 85% of the variance

- Less that 80% of the variance

- Less than 85% of the variance

Ans: B. *First, build a PCA model using sklearn, and then calculate the cumulative variance ratio. Refer to the following lines of code:*

```python
#convert the dataframe into array
X = housing.to_numpy()

#build the PCA model
pca = PCA()
x_lr = pca.fit_transform(X)
# find the cumulative variance percentage
np.cumsum(pca.explained_variance_ratio_)

#find its eigenvectors and eigenvalues.
w, v = np.linalg.eig(C)
```
