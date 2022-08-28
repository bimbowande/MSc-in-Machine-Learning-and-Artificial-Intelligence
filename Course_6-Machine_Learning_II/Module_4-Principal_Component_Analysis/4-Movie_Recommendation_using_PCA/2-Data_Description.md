# Data Description

Let’s begin the session by describing the dataset that will be used throughout the session to build an end-to-end movie recommendation system. Note that the process described here is one of the ways to provide the recommendation. There are many ways to create a recommendation system, one of which you have seen earlier, using the ALS algorithm.

You can read the data from the S3 folder below to run your own code.

**s3a://sparkdemonstration/movielens-tag-relevance.csv**

The size of the dataset is about 250MB. It consists of around 13,000 movies in rows and about 1,000 tags in columns. Let’s first learn about the meaning of ‘tags’ by using an example of a movie, which is as given below.

Suppose there is a movie named Conjuring. We all know that it is a horror movie. Suppose you have three tags for this movie, termed as horror, romantic and action. Now, a score out of one corresponds to each tag, say 0.9 for horror, 0.05 for action and 0.05 for romantic, which represents the weightage of each tag for the movie ‘Conjuring’. 

Similarly, there are 1,000 tags corresponding to the 13,000 movies in the dataset that have a specific score out of one corresponding to each tag.

**VIDEO**

So, in this segment, you learnt about the dataset. In the next segment, you will learn how to perform the normalisation of the dataset.