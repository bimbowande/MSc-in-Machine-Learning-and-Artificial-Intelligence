# Model Evaluation

In the previous segment, after training the data set, you built the model. Now, let’s determine the model's accuracy. In the next video, Sajan will explain the model evaluation process.

**VIDEO**

As explained in the video above, the silhouette coefficient score indicates the accuracy of the K-means model. To calculate the silhouette coefficient score of the model, you need to first define a clustering evaluator, as shown below.

```python
evaluator = ClusteringEvaluator()
```

Next, you need to calculate the score using the .evaluate() method, as shown below.

```python
silhouette_score = evaluator.evaluate(output)
```

To print the score, you can use the following command:

```python
print("silhouette_score = " + str(silhouette_score))
```

After calculating the silhouette score, you can use another important metric to find the K- value: the elbow method. You calculate the cost function values for different K-values in the present model using the following block of code:

```python
ks = [3,7,10]

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

Now, the block of code given above calculates the cost function for k=[3,7,10]. To plot the elbow curve, you can use the following block of code: 

```python
import matplotlib.pyplot as plt

%matplotlib inline

# Plot k vs cost_function
plt.plot(ks, costfunction, '-o')
plt.xlabel('number of clusters, k')
plt.ylabel('cost function')
plt.xticks(ks)
plt.show()
```

As you can see in the figure given below, K=7 is the optimal value for the number of clusters for this data set.

![Elbow curve](https://i.ibb.co/Fb1Mjyd/Elbow-Curve.png)

