# PCA Python Demonstration - sklearn and scree plot

In the previous segment, you learnt how to perform PCA from scratch. Now, in this segment, you will learn how to perform PCA analysis using the pca package of ‘sklearn.decomposition’. Let’s watch the upcoming video to learn about it from our expert.

**VIDEO**

So, as you saw in the video, it is quite easy to perform PCA using sklearn, and within three steps, you get a scatter plot that is similar to the graph that you saw in the previous segment.

```python
#Step- 1, To start the PCA process.
pca = PCA()
```

```python
#Step- 2, To transform the data into scaled form.
x_lr = pca.fit_transform(X) 
```

```python
#Step- 3, Plot the scatter plot of 2 PCs.
plt.scatter(x_lr[:, 0], x_lr[:, 1], c=y)
```

Now, let’s try and understand the scree plots.

**Scree plot:** It visually depicts the percentage of variance for each PC using a histogram.

So, to make a scree plot of the PCA analysis, you need to simply write the following lines of code. Here, you will get the ratio of the variances of each PC:

```python
pd.Series(pca.explained_variance_ratio_).plot(kind='bar')
plt.xlabel('PCs')
plt.ylabel('Variance')
```

![Ratio of Variance](https://i.ibb.co/HLv16wZ/Ratio-of-Variance.png)

In the scree plot given above, you can see that about 90% of the variance is contained in PC0, while the rest is contained in PC1, PC2 and PC3.

Now, suppose you want to plot the cumulative variance ratio. To do this, you can simply write the following code:

```python
plt.plot(np.cumsum(pca.explained_variance_ratio_), '-o')
plt.xlabel('Number of PCs')
plt.ylabel('Cumulative Variance Ratio')
```

![Cumalative Variance Ratio](https://i.ibb.co/6mLgnqT/Cumalative-Variance-Ratio.png)

You can draw quite an interesting insight from the scree plot given above. You can observe that about 98% of the variance can be explained with the help of two PCs only, PC0 and PC1.

Now, let’s learn about bi-plots.

So, as you saw in the video, the loading vectors show the increasing directions of the original variables on the principal component axes. In this example, the covariance between petal length and petal width is high (about 0.97; please refer to the covariance matrix of the iris dataset) and, hence, both of them are varying in the same direction, as depicted in the figure given below.

![PCs Graph](https://i.ibb.co/5RgbR4h/PCs-Graph.png)

In this figure, the red vectors are called the loading vectors and they are the increasing directions of the corresponding features on the PCs.

You will learn about the application of loading vectors in the case study session.

### Comprehension

Suppose you have been given a ‘breast_cancer’ data set that you can load from the ‘sklearn’ package as shown below:

```python
from sklearn.datasets import load_breast_cancer
bc = load_breast_cancer()
X = bc.data
df = pd.DataFrame(X, columns=bc.feature_names)
df.head()
```

Based on this data set, answer the following question.

#### Number of PCs

Qn: How many PCs will you obtain after performing PCA analysis on this data set?

- 10

- 15

- 25

- 30

Ans: D. *The number PCs is the same as the number of variables in the data set.*

#### Variance

Qn: After performing PCA analysis on the data set, what would be the percentage of variance that can be explained by two PCs?

- Greater than 99%

- Less than 99%

- Less than 80%

- Less than 85%

Ans: A. *Plot the cumulative scree plot of the PCs and you will get the answer:*

```python
from sklearn.decomposition import PCA
pca = PCA()
x_red = pca.fit_transform(X)
plt.plot(np.cumsum(pca.explained_variance_ratio_), '-o')
```

Qn: How many PCs are required to explain more than 99% of the variance?  
 
- 1

- 2

- None of the above

Ans: B. *Plot the cumulative scree plot of the PCs and you will get the answer.*

```python
from sklearn.decomposition import PCA
pca = PCA()
x_red = pca.fit_transform(X)
plt.plot(np.cumsum(pca.explained_variance_ratio_), '-o')
```