# Data Set

In this segment, we will discuss the data set that we will use for the implementation of K-means clustering. You can download the data set from below.

Download [Music data](music_data.csv)

In the upcoming video, Sajan will explain the data set and its salient features.

**VIDEO**

As explained in the video above, the data set is of the UK-based music company Last.fm. Using this data set, we will perform clustering on the data of music artists based on their popularity in terms of the number of times people have listened to their songs. Such clustering can be used for the following purposes:

-   **Recommendation**: Recommending similar artists/songs to users
    
-   **Monetisation and business**: Releasing exclusive songs on the platform
    
-   **Solving a cold start problem**: Categorising a new artist’s songs in a cluster based on features such as popularity
    

The given data set contains the following features:

1.  **user_id**: Unique ID of each user playing the songs
    
2.  **artist_id**: Unique ID of each artist whose song is present in the data set
    
3.  **artist_name**: Name of the artist
    
4.  **plays**: Total number of times a user has listened to a particular artist’s song
    

Now that you are familiar with the features of the data set, let’s perform K-means clustering on the data set and cluster the artists based on their popularity. Let’s start by performing Exploratory Data Analysis (EDA) on the data set.