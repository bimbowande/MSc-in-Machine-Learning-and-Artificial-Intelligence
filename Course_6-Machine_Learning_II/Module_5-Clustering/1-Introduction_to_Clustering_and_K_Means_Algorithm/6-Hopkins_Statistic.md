# Hopkins Statistic

Before applying any clustering algorithm to the given data, it is important to check whether the data has some meaningful clusters or not, which, in general, means that the given data is not random. The process of evaluating data to check whether it is feasible for clustering is known as the clustering tendency of the given data.

Any clustering algorithm will return clusters even if the data does not have any meaningful clusters. So, before proceeding with clustering, you should remember to not apply the clustering method carelessly and to check the clustering tendency at the same time.

In the next video, you will learn how to interpret the Hopkins statistic.

**VIDEO**

The Hopkins statistic is used to measure the clustering tendency by measuring the probability that the given data is generated using uniform data distribution. If the value of the Hopkins statistic is close to 1, then it implies that the dataset is clusterable. 

#### Hopkins Statistic

Qn: A certain dataset has the following scatter plot.

![Hopkins Statistic Question](https://i.ibb.co/4pLwTFg/Hopkins-Statistic-Question.jpg)

Which of the following statements is true? (H = Hopkins statistic)

- H > 0.75

- 0.5 < H < 0.75

- H < 0.5

Ans: A. *The dataset has a very high cluster tendency. Therefore, the Hopkins statistic will also be very high, i.e., close to 1.*

In the previous segments, you got a basic idea of the concept of clustering. As a data scientist, you will be required to perform clustering regularly. There are different types of clustering algorithms available, and you should be well-versed in using them. In the upcoming segments, we will discuss a popular clustering algorithm known as K-means clustering.

## Additional Link

[Validating cluster tendency using Hopkins statistic](https://stats.stackexchange.com/questions/332651/validating-cluster-tendency-using-hopkins-statistic)