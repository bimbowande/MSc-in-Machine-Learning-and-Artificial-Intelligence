# Session Summary

With this, you have reached the end of this session. In this session, you learnt how to implement the K-means clustering algorithm using PySpark. 

The common syntax used for applying the algorithm is as follows:

```python
from pyspark.ml.clustering import KMeans

# Loads data.
dataset = spark.read.format("libsvm").load("data/mllib/sample_kmeans_data.txt")

# Trains a k-means model.
kmeans =KMeans(k=10, seed=1)  
model = kmeans.fit(dataset)

# Make predictions
predictions = model.transform(dataset)
```

After training the model, you can compute the cost using the following block of code:

```python
model.computeCost(model_data)
```

After training the model, you can find the model accuracy by calculating the silhouette coefficient score of the model.  In order to do so, you need to first define a clustering evaluator, as shown below.

```python
evaluator = ClusteringEvaluator()
```

You can calculate the score using the .evaluate() method, as shown below.

```python
silhouette_score = evaluator.evaluate(output)
print("silhouette_score = " + str(silhouette_score))
```

You can also determine the optimal number of clusters using the elbow method. In this method, you calculate the cost function values for different K-values in the present model using the following block of code:

```python
ks = [k1, k2, k3, k4] # where k1, k2, k3, k4 are your different values of K

costfunction = []
for k_num in ks:

    # build kmeans model with k as no of cluster
    print("K :  ",k_num)

    model_k = KMeans(k=k_num , seed=1)

    # train the model
    model = model_k.fit(model_data.select('features'))

    # Append costfunction to list of costfunction
    costfunction.append(model.computeCost(model_data))
```

After finding the cost function values for the different values of K, you need to plot the curve and pick the elbow of the curve as the optimal number of clusters.

You can access the summary notes for this module by clicking on the link below.

Download [Clustering - Lecture Notes](../Clustering_Lecture_notes.pdf)
