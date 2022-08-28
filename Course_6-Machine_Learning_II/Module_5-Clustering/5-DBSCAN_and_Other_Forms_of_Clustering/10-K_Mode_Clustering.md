# K-Mode Clustering

The K-means clustering algorithm is undoubtedly one of the most widely used partitional algorithms for numerical data or continuous data, but it cannot handle categorical data, and the reason for this is the difference in the dissimilarity measure the algorithm uses.

The k-modes clustering algorithm is based on the K-means paradigm but eliminates the numeric data limitation and preserves its efficiency.

In this upcoming video, Ankit will explain this algorithm in detail.

**VIDEO**

Let’s go through all the steps involved in the k-mode algorithm. Similar to the K-means algorithm, you will first need to specify the number of clusters, K, that will be present in your result.

-   The algorithm first selects K objects randomly to act as initial cluster centres. These objects are called cluster centroids or means. 
    
-   You need to assign the remaining objects to their closest centroids. The distance matrix is calculated by evaluating the dissimilarity between the cluster centroid and each point.
    
-   After you have assigned the objects to their respective centroids, the algorithm recalculates the cluster centroids. The centroids are calculated by the modes of each feature.
    
-   After this recomputation, you need to recheck the observations to determine whether or not they might be closer to a different cluster. Next, you have to reassign the objects to centroids accordingly. 
    
-   You need to continue repeating these steps until assigning clusters stops. This means that you stop repeating the iterations when the clusters formed in an iteration are the same as the ones in their previous iteration. 
    

We have provided a simple case study on the implementation of k-mode in Python.

For implementing k-mode in Python, you need to install an additional library. You may download the Kmode library by following the steps mentioned in this [document](https://pypi.org/project/kmodes/).

Remember that to use KModes in Anaconda, you need to install KModes using the conda installer in Anaconda Prompt.

You can also install the kmodes library directly through pip using the following command:

'**pip install kmodes**'

**You can download the data used for Python Lab from below.**

Download [Bank Marketing Data Set](bankmarketing.csv)


**You can go through the Python code given below for the implementation.**

Download [K-modes Clustering](K_Mode_Bank_Marketing.ipynb)

Kmodes can be initialised using two main methods namely, 'Hunag' and 'Cao'. 

You can read about the 'Huang' initialisation technique by going through this [document](https://pdfs.semanticscholar.org/d42b/b5ad2d03be6d8fefa63d25d02c0711d19728.pdf).

You may also read about the 'Cao' initialisation technique [here](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.474.8181&rep=rep1&type=pdf).