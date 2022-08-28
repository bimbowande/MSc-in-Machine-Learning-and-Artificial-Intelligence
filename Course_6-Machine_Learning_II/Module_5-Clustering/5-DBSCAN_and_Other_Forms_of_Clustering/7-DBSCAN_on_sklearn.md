# DBSCAN on sklearn

In this segment, you will learn how to implement the DBSCAN algorithm using the sklearn library. We will be working with the famous iris data set and attempt to: 

1.  Obtain an optimal value of EPS,
    
2.  Generate good clusters using the DBSCAN algorithm, and
    
3.  Identify noise points/outliers using this value of EPS.  
    **Note**: Since the data is in 4 dimensions, we will use PCA to reduce the dimensions and visualise the clusters
    

The notebook for the demonstration is attached below.

Download [DBSCAN Python Demonstration](DBSCAN_on_Iris_dataset.ipynb)



Let’s watch the upcoming video and learn how to implement the DBSCAN algorithm using the sklearn library from our expert Ankit.

**VIDEO**

In the video above, you learnt how to use the iris data set to generate clusters and visualise them using PCA. For the demonstration, we have used sklearn's DBSCAN function. You can find the documentation for this in the [link](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.DBSCAN.html). The main model building code used in the demonstration is given below. The two parameters that are required to be provided by the user are EPS and MinPts or min_samples.

```python
from sklearn.cluster import DBSCAN

model = DBSCAN(eps = 0.6,  min_samples = 5).fit(dataset)
```

In the next segment, we will summarise your learnings from this session.

**Additional Resources**

Python demonstration of DBSCAN on soccer players: [Read Here](https://towardsdatascience.com/grouping-soccer-players-with-similar-skillsets-in-fifa-20-part-3-dbscan-b23389a08cc7)