# SubTask: Clustering

In the previous segment, you learnt about the various EDA, visualisation and feature engineering tasks that you need to perform. Your next task is to apply Clustering as a feature generation step. You have already learnt about two clustering algorithms, the K-means algorithm and the hierarchical clustering algorithm. However, for this Capstone Project, you will have to use another algorithm known as the **DBSCAN algorithm**, which is a density-based clustering technique.

**VIDEO**

As you learnt in the video above, you can utilise the latitude and longitude data to generate new features that are able to capture hidden information. Another feature engineering technique involves using clusters as features for building your model. This means that you can use Clustering to group the data points that are in close proximity and use the clusters' information as a feature in the data set. From the geospatial plot, you can observe that points in high-density regions are similar to each other and hence can be clustered together. Therefore, you may use a density-based clustering technique known as DBSCAN.

In this Capstone Project, you are expected to use the DBSCAN algorithm to cluster the latitude and longitude data. To run DBSCAN on the latitude and longitude data, you need to use the [haversine](https://en.wikipedia.org/wiki/Haversine_formula) metric and the [ball tree](http://scikit-learn.org/stable/modules/neighbors.html#ball-tree) algorithm to calculate great-circle distances between the data points.

Here, the data may have different device ids with the latitude and longitude information appearing zero in the data set. You can simply ignore them in the clustering exercise and assign different cluster ids to these device ids. Once you have the clusters ready, you can explore the cluster ids as a feature during the model development phase.

You can use the following code snippet to execute the DBSCAN algorithm:

```python
kms_per_radian = 6371.0088
epsilon = __/kms_per_radian
db = DBSCAN(eps= epsilon, min_samples= _, algorithm = ‘ball_tree’, metric = ‘haversine’).fit(np.radians(coords))
```

In the next segment, Arihant will explain the final data preparation steps that you need to complete before building your model.