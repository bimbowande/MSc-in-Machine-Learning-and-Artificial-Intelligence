# Graded Questions

#### K-Means Algorithm

Qn: Select the problem sets on which the k-means clustering algorithm can be applied.

- Weather forecast for the next week, given the data set of weather information for the last five years

- Given an e-commerce company’s customer details, the products they purchased and the amount spent. The company wants to group its customers based on their buying behaviour.

- Predict whether a new customer would respond to a bank’s new product based on their historical information

- All of the above

Ans: B. *This is the correct option. The other options are predicting the response based on independent variables.*

Qn: Select the correct statement from below.

- The clusters formed by the K-means algorithm do not depend on the initial selection of cluster centres.

- The results of the K-means algorithm are impacted by outliers and the range of the attributes.

- The K-means algorithm can be applied to both categorical and numerical variables.

- K-means clustering automatically selects the most optimum value of K.

Ans: B. *Depending on the initial selection of centres, the clusters formed might be different. The value of K has to be decided by the user*

#### Silhouette Score Method

In the Silhouette Score Method, which of the following would be the most appropriate number of clusters for the K-means clustering algorithm?

- Global minima

- Global maximum

- Both of the above

- None of the above

Ans: B. *A high silhouette score indicates that the clusters are more distinct. Usually, the value of K with the highest silhouette score suggests the optimal number of clusters for clustering the data set.*
  
![Silhouette Score Optimal K](https://i.ibb.co/L8r2Xbz/Silhouette-Score-Optimal-K.png)

*The graph given above indicates the silhouette scores for different values of K and you can see that the global maximum is at k = 3, indicating the point for optimal clusters.*

**Comprehension**

Download the data set on the batting figures of batsmen in ODI matches attached below and analyse the data.

Download [Cricket](Cricket.csv)

Choose Strike Rate and Average as the two factors on which you will cluster the data. You do not need to clean the data. Just scale the data using the scale command and create the clusters.

**Points to considers before you proceed further**

-   **Standardise** all parameters using the standard_scaler.fit_transform() function and save the output to a variable before you proceed. (check the K-means code.)
-   **Choose random_state=100** for running K-means in Python with SKLearn.

#### Cricket

Qn: Select the number of clusters as 4. Who falls in the same cluster as Virat Kohli?

- S T Jayasuriya

- S R Tendulkar

- C H Gayle

- Yuvraj Singh

Ans: B. 

Qn: Based on the clustering, choose the correct statement, given that the clusters formed are (high SR, high Ave) - A, (low SR, low Ave) - B, (High SR, Low Ave) - C, (Low SR, High Ave) - D.

- IVA Richards and S R Tendulkar both belong to Group A.

- R Dravid is in Group C.

- Chris Gayle belongs to Group B.

- M J Guptill belongs to Group D.

Ans: A. *You can even plot the graph after scaling for better separation of points and more intuitive visualisation.*

