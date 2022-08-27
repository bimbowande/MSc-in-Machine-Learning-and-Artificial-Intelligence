# Model Building

Now that we have performed EDA on the given data set and have the final DataFrame ready, we can start building the model. Let’s hear from Sajan as he explains the process.

**VIDEO**

After importing the libraries, you need to define the K-means object using the following command:

```python
kmeans = KMeans(k=7, seed=1)
```

Here, k=7 signifies the number of clusters to be formed. You can start training the model using the following block of code:

```python
model = kmeans.fit(model_data.select('features'))
```

After training the model, you need to compute the cost using the following block of code:

```python
model.computeCost(model_data)
```

The output of the clustering model above can be visualised using the following block of code:

```python
output = model.transform(model_data)
output.show(100)
```

In the output table, the model appends one more column named ‘prediction’, wherein the predicted values of the model (cluster ID of the artist) are displayed. To ascertain the centres of the cluster, you can use the following block of code:

```python
centers = model.clusterCenters()
print("Cluster Centers: ")
for center in centers:
   print(center)
```

If you want to print the names of artists whose total plays is greater than 100 (or any other number) along with their cluster IDs, you will need to create a temp view first. The step involves writing an SQL query, as shown below.

```python
output.createTempView('output_view')
spark.sql("select artist_name, plays_sum, prediction from output_view order by output_view.plays_sum desc limit 100").show()
```

Now, the model is ready. But we need to determine its accuracy. So, in the next segment, you will learn how to evaluate the model's performance.

#### Temporary View

Qn: State whether the following statement is true or false.

“A .createTempView() is required to run an SQL query on DataFrame ”

- True

- False

Ans: A. *Correct. .createTempView() will create a temporary view of the table on the memory, which can be used to run SQL queries.*
