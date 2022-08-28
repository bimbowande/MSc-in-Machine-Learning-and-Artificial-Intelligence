# Introduction

Welcome to the fourth session of the module on the Principal Component Analysis (PCA). In the previous session, you learnt about the concepts of eigenvectors and eigenvalues. You also learnt how eigenvectors and eigenvalues lead to the diagonalisation of the covariance matrix. Next, you learnt that the eigenvectors of the covariance matrix are the directions of the least covariance among the features. Then, you learnt about eigendecomposition of the covariance matrix and, ultimately, you were able to stitch all the concepts together and understood the PCA algorithm.

Apart from this, you also learnt how to perform PCA in Python and Spark using ‘sklearn’ and ‘MLlib’, respectively.

Now, in this session, you will be introduced to an end-to-end case study on PCA. This case study is about a movie recommendation system, where the focus will be on reducing the dimensions of the movie tags (or genres). You will have sufficiently large data and have hands-on experience of Spark to perform PCA for big data.

The broad flow of this case study is as follows:

1.  Describing the movie dataset 
2.  Building a PCA model
3.  Selecting the required number of principal components (PCs)
4.  Building a movie recommendation system using the nearest neighbour technique

As you will perform all the PCA and movie recommendation steps on pyspark, you are required to create an EMR cluster with the following specifications:

-   M4.large with 1 master and 1 slave.
-   Add Spark 2.4.5 as an application while creating the cluster.

You are expected to run an EMR cluster and code simultaneously with the videos. There are some graded questions in the end which you won't be able to answer if you will not code with the videos.

## People you will hear from in this session

**Subject Matter Expert**

[Jaidev Deshpande](https://www.linkedin.com/in/jaidevd/)

Senior Data Scientist, Gramener  
With over 10 years of experience in data science and predictive analytics, Jaidev has worked with multiple firms, including Springboard, iDataLabs and Cube26. He has received his bachelor’s degree in Electrical and Electronics Engineering from Vishwakarma Institute of Technology, Pune. He is currently working as a Senior Data Scientist at Gramener, a leading data science consulting company, which advises clients on data-driven leadership.