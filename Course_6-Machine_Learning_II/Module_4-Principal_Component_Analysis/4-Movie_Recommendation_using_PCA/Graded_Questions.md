# Graded Questions

You performed Spark implementation on the movie dataset and built a recommendation system using PCA. Now, you will solve the following graded question, which are based on the case study that you solved. 

#### Movie recommendation

Qn: Suppose there is a movie ‘Interstellar (2014)’, and you build a recommendation system for this particular movie after considering 300 principal components. Which of the following movies are included in the top five nearest neighbours corresponding to the  ‘Interstellar (2014)’ movie?

- The Martian (2015), Sunshine (2007), Space (1985)

- Arrival (2016), The Martian (2015), Gravity (2013)

- Lucy (2014), Sunshine (2007), Space (1985)

- X-Men (2000), Lucy (2014), Space (1985)

Ans: B. *Refer to the following code to get the answer.*

```python
n_pcs = 300
nn = NearestNeighbors()
nn = nn.fit(X[:, :n_pcs])
neighbors = nn.kneighbors(pdf.loc['Interstellar (2014)'].values[:n_pcs].reshape(1, -1), return_distance=False)
pdf.index[neighbors.ravel()].tolist()
```

#### Graded questions

Qn: The most popularly used dimensionality reduction algorithm is the Principal Component Analysis (PCA). Which of the following statements is true about PCA?  
a. It is an unsupervised method.  
b. It searches for the directions where data has the largest variance.  
c. The total number of principal components is equal to the number of features in the data set.  
d. All principal components are orthogonal to each other.

- a and b

- a and c

- b and c

- All the statements are true.

Ans: D. *All the statements are correct*

Qn: Which of the following projections do you consider for PCA on the dotted line?

![PCA Projections](https://i.ibb.co/gr1WcRt/PCA-Projections-Question.png)

- Graph- 1

- Graph- 2

- It does not matter whether you select either Graph 1 or Graph 2

- None of the above

Ans: B. *This option is correct, as the new axes are the principal components, and the orthogonal projection is the correct way to get the transformed points on the principal components axes.*

Qn: Suppose you obtain the eigenvalues λ1 ≥ λ2 ≥ • • • ≥ λN. Consider ‘M’ as the first ‘M’ principal components and ‘D’ as the total number of features in the dataset. 

The percentage of variance in the first ‘M’ principal components can be defined as follows:

Percentage of variance:

![](https://images.upgrad.com/1e559205-07f1-4db2-b990-0edcd5c75e0d-pca%203.4.9%202.png)

![](https://images.upgrad.com/4300791b-8dfc-45a4-9072-8576d4850f2b-pca%203.4.9%203.png)

Which of these graphs shows a better performance of PCA?

- Graph I

- Graph II

- Any of the two

- None of the above

Ans: A. *Graph I shows better performance of the PCA algorithm, as the percentage of variance in the first ‘M’ principal components increases and becomes saturated as ‘M’ increases.*
