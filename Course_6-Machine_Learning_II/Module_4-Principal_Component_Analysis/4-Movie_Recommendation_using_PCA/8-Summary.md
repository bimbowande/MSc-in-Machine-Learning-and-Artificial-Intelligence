# Summary

So, in this session, you applied all the concepts of PCA that you learnt in the previous three sessions. Some important learnings from this session are given below.

1.  Sometimes, when you consider the less number of principal components, which do not contain sufficient percentage of total variance, then this may hamper the results of the analysis. Hence, it is important to take an optimum number of principal components so that there is less information loss in terms of variance.
2.  In this session, you also learnt about the nearest neighbour algorithm. Then, you considered the following example to understand this concept better.

Imagine you are standing in an empty room, which is essentially a three-dimensional space. Suppose there are thousands of bubbles around you, which are stable. Now, can you identify the top five bubbles that are closest to your vision? This is what the nearest neighbour algorithm finds. It calculates the Euclidean distance of the point of interest to the points that lie in the n-dimensional space.

Then, you extended the three-dimensional space to the 500 dimensions (or 500 principal components) to find out the top five nearest neighbours for a particular movie. In this way,  you found the nearest top five movies (or top five nearest neighbours)                                     corresponding to a particular movie.

You can find the well-written codes in the below two notebooks:

Download [PCA Algorithm Notebook](PCA_Lab1_Analyze_Movie_Tags.ipynb)

Download [Movie Recommendation using PCA Notebook](PCA_Lab2_Content_Based_Recommendations.ipynb)

With this, you have completed this case study on the movie recommendation system.