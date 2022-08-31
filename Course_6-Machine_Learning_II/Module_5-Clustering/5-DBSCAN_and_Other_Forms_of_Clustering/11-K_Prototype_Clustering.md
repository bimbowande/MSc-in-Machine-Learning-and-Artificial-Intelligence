# K-prototype Clustering

If your data set contains both numerical and categorical variables, then you can use the K-prototype algorithm, which is a combination of K-means and K-modes. In the next video, you will learn about the K-prototype algorithm.

**VIDEO**

In K-prototype clustering, you combine K-means and K-modes to handle both continuous data and categorical data. The similarity measure is calculated as the sum of the numerical dissimilarity and the categorical similarity. For K-prototype, the distance function is given by the following equation:
$$\large d(x, y)=\sum_p^{j=1}(X_j-Y_j)^2+\gamma\sum_{j=p+1}^M\delta(X_j-Y_j)$$

where $\gamma$ is the weighting factor that determines the relative importance of numerical categorical attributes.

Depending on the attributes, you can provide a weightage to the categorical features compared with the numerical features. For example, if you wish to assign a higher weightage to categorical features, then you can assign a value that is greater than 1.

A sample implementation of the K-prototype algorithm is given below. The data set used for this case study is provided below.

[https://archive.ics.uci.edu/ml/datasets/Blood+Transfusion+Service+Center](https://archive.ics.uci.edu/ml/datasets/Blood+Transfusion+Service+Center)

For K-Prototype Python Lab, we used the RFMTC marketing model (a modified version of RFM). The data contains 748 donor details, and each one includes R (Recency: months since the last donation), F (Frequency: the total number of donations), M (Monetary: the total blood donated in cc), T (Time: months since the first donation) and a binary variable representing whether they donated blood in March 2007 (1 indicates that they donated blood, and 0 indicates that they did not donate blood).

Refer to the notebook attached below to understand the implementation of the K-prototype algorithm.

Download [K-prototype Clustering](K_Prototype_Clustering.ipynb)

K-Prototype clustering uses ‘Huang’ and ‘Cao’ initialisations, and you may read more about this in this [document](https://grid.cs.gsu.edu/~wkim/index_files/papers/kprototype.pdf).