# Recommendation System

In the previous segment, you learnt how to normalize the data points and also learnt that the two principal components contain a 16% variance, which is very less. However, when you use 500 PCs, then the percentage of variance comes out to be around 91%.

In this segment, you will learn how to recommend the top movies by finding the nearest neighbour for a particular movie by using more number of principal components.

Let’s start this segment by performing some ready steps which we have covered until now.

**VIDEO**

In this video, a total of 500 PCs have been considered. In the next video, you will learn how to find the top five closest movies (or neighbour) for a particular movie in the 500 PCs’ dimensions.

**VIDEO**

The steps performed in this video are summarised below.

-   First, you need to get the projected data points of 500 principal components. You can write the following lines of code to get the projected data points of 500 principal components.

```python
# get the matrix of projected data points on 500 PCs.
pc = matrix.computePrincipalComponents(500)
matrix_reduced = matrix.multiply(pc)

# Convert ‘matrix_reduced’ into a numpy array.
import numpy as np
X = matrix_reduced.rows.map(np.array).collect()
X = np.array(X)

# get the titles of the movies into ‘title’.
titles = df.select('title').toPandas()

# prepare a single dataframe with 500 columns of newly projected data points.
import pandas as pd
pdf = pd.DataFrame(X, index=titles['title'])
```

-   In the next step, you have to apply a nearest neighbour algorithm. Let’s consider the following example so that you understand this better.

 Imagine you are standing in an empty room, which is essentially a three-dimensional space. Suppose there are thousands of tennis balls around you, which are stable means they are not moving. Now, can you identify the top five tennis balls that are closest to your eyes? This is what the nearest neighbour algorithm finds. It calculates the Euclidean distance of the point of interest to the points that lie in the n-dimensional space.

Now, extend the three-dimensional space to the 500 dimensions and try to find out the top five nearest neighbours for a particular movie. 

In order to find out the top five movies (or top 5 nearest neighbours) for a particular movie using 2 PCs, you can perform the following lines of code.

```python
from sklearn.neighbors import NearestNeighbors
n_pcs = 2
nn = NearestNeighbors()
nn = nn.fit(X[:, :n_pcs])
neighbors = nn.kneighbors(pdf.loc['Toy Story (1995)'].values[:n_pcs].reshape(1, -1), return_distance=False)
pdf.index[neighbors.ravel()].tolist()
```

Now, you need to import the ‘NearestNeighbours’ class from Sklearn. Here, you will find the top five neighbours corresponding to the movie Toy Story (1995). Then, you will get the following five movies:

-   Toy Story (1995)
-   Dirty Laundry
-   Empire of Dreams
-   The Ten Commandments
-   The Blood of Heroes

You saw that no movie is similar to the movie Toy Story (1995) when only two principal components are considered.

Now, let’s run the same code with 10, 100 and 500 principal components.

**VIDEO**

Now, when you find the nearest neighbours corresponding to the movie Toy Story (1995) using 10 principal components, then you get the following top five movies:

-   Toy Story (1995)
-   Finding Nemo
-   Monster
-   A Bug's Life
-   Ratatouille

Here, you saw that you are getting all the animated movies when you consider 10 PCs.

When you find the nearest neighbours corresponding to the movie Toy Story (1995) using 100 principal components, then you get the following top five movies.

-   Toy Story (1995)
-   Toy Story 2
-   Monsters
-   Toy Story 3
-   A Bug’s life

Here, you saw that you are getting Toy Story 2 and Toy Story 3 as well.

Hence, as the number of principal components increases, the nearest movie prediction will give better results.   
 

So, instead of using thousands of features in the original dataset, you can recommend movies to the users using only 100 features, which are essentially the principal components. But there is an interesting point to note here. We get more or less good results with 10 PCs also. Hence, considering a larger number of PCs is not necessary. There are 2 key points:

1.  The variance captured need not be a metric to decide the number of PCs to be used but the final output metric which is the quality of recommendation should be considered to decide the number of PCs.
2.  It is preferred to have a lower number of PCs because as the number of PCs increase, the computational power required increases and one of the primary aims of PCA is to reduce the number of features to be used for future modelling.

**Additional reading**

[K- Nearest Neighbour algorithm](https://www.youtube.com/watch?v=HVXime0nQeI)