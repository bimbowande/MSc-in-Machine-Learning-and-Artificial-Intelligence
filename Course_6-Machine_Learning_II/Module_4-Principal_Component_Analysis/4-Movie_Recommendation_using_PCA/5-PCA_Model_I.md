# PCA Model- I

In the previous segment, you normalized your dataset. In this segment, you will learn how to build a PCA model. 

**VIDEO**

-   After performing the normalization step, you need to read the data into RDDs.

```python
rdd = df.select('normFeats').rdd
```

-   Then, you need to import ‘RowMatrix’ and ‘Vectors’ from the MLlib library of PySpark.

```python
from pyspark.mllib.linalg.distributed import RowMatrix
from pyspark.mllib.linalg import Vectors
```

-   Next, you need to get the RDD data into vectors and then convert the vectors into a matrix form. You already learnt about this particular step in the previous session, where you performed the PCA analysis using MLlib on a smaller data set.
    
```python
from pyspark.mllib.linalg.distributed import RowMatrix
from pyspark.mllib.linalg import Vectors
```
    
And finally, you need to have a matrix for the entire normalized dataset, where each row contains the name of a movie and each column contains a tag.  
     
    
-   Once you get the principal components, you need to multiply the ‘matrix’ with the principal components to get the corresponding points in the principal component basis system.    

```python
matrix_reduced = matrix.multiply(pc)
```

So, the ‘matrix_reduces’ will be in the order of **Number of movies X 2**, as you can consider only two principal components.

In the next step, you need to plot a scatter plot for all the data points of these two principal components. 

```python
import numpy as np
x_red = np.array(matrix_reduced.rows.collect())
import matplotlib.pyplot as plt
%matplotlib inline
plt.scatter(*x_red.T)
```

![PCA Model Scatter](https://i.ibb.co/DMBR42p/PCA-Model-Scatter.png)

-   The plot above did not give much insight into the two PCs.

**VIDEO**

In this video, you saw that the scatter plot of the two PCs did not give any insight into the dataset. So, in order to get some useful information from the dataset, you need to plot a biplot.  
As there are more than 1,000 features in this particular dataset, you cannot plot each vector corresponding to each tag for the movies. So, let’s take the top five tags having the maximum variance to plot their loading vectors on this scatter plot.

So, to get the top five features (or tags) you need to understand the lines of code given below.

```python
from pyspark.ml.stat import Summarizer
summarizer = Summarizer.metrics("variance")
variance = df.select(summarizer.summary(df.features))
variance.show()
```

To get the summary of the columns, you can select a class called ‘Summarizer’ in ml.stat of PySpark. You can pass any statistical moment such as mean, median, variance and standard deviation to get the values corresponding to each column. 

Here, in this case, you have passed ‘variance’ as a summary parameter. The variances of each column will be stored in ‘variance’. Now, to unpack this structure, you need to convert it into an RDD.

```python
x = variance.take(1)[0]
variance = x.asDict()['aggregate_metrics(features, 1.0)'].asDict()['variance']
ix = variance.toArray().argsort()
ix = ix[::-1]
```

In the first line of code given above, you have taken the 1st row and 0th element of ‘variance’ and stored it in the array ‘x’. Then, in the second line of code, you have converted the variance into the dictionary ‘variance’. Next, you have sorted the dictionary ‘variance’ in the descending order of the variances corresponding to each column of the movie dataset.

Now, to get the first five entries from the sorted dictionary ‘variance’, let’s run the following code.

```python
sortedCols = []
for i in ix[:5]:
    sortedCols.append((i, df.columns[i]))
```

Here, in the ‘sortedCols’ list, you got the variances of the top five columns and their positions in the original dataset.

Now, for calculating the variances of these top five columns, you need to plot the loading vectors on the scatter plot of the two principal components. Take a look at the following diagram.

![PCA Scatter Vectors](https://i.ibb.co/sPm9SXr/PCA-Scatter-Vectors.png)

In the loading vectors diagram above, which is built only on the scatter plot of the two principal components, you see that the tags ‘colourful’ and ‘horrible’ seem to be highly correlated, as the loading vectors of both the tags are in the same direction.

Do you think it is possible for a particular movie to contain both ‘horrible’ and ‘colourful’ tags simultaneously?

Let’s take a look at the relationship between these two tags in the next segment. 

#### PCA

Qn: Consider the two codes given below.  
              
(a) `pc = matrix.computePrincipalComponents(2)`
(b) `matrix_reduced = matrix.multiply(pc)`

Which of the following statements is true regarding these two codes?

- (a) will provide you the final projected data points on the basis of eigenvectors.

- (a) will provide you the eigenvectors corresponding to the covariance matrix of the dataset.

- (b) will provide you the eigenvectors corresponding to the covariance matrix of the dataset.

- (b) will provide you the final projected data points on the basis of eigenvectors.

- ‘matrix’ is the matrix that contains the original data points and if you multiply the original data points with ‘pc’, then you will get the projected data points on the basis of  eigenvectors.

Ans: B, D & E.

- *When you compute ‘pc’ using this code, you get the eigenvectors or axes corresponding to the PCs and not to the projected data points.*

- *If you multiply the original data points, i.e., ‘matrix’ with ‘pc’, i.e., eigenvectors, then you will get the projected data points.*

- *The array ‘matrix’ contains the original data points, and, if you multiply them with ‘pc’, i.e., eigenvectors, then will you get the projected data points.*

