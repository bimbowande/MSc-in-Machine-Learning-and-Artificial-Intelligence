# Decision Tree Optimisation in Spark

So far, you completed a detailed study on Decision Trees both theoretically and practically. In this segment, you will learn how Decision Trees work internally in Spark environments. In this next video, Sajan will introduce you to this concept:

**VIDEO**

Working with a dataset of large size may lead to a huge Decision Tree. Such a tree requires a lot of time to execute. In order to prevent this from happening, there are three main types of optimisations available in Spark:

1.  Level-Wise Training in Spark
2.  Binning
3.  Distributed Decision Trees

**Distributed Decision Trees**

You will be covering all these optimisations one by one, beginning with Distributed Decision Trees in Spark. In case of a distributed tree, the data is divided into partitions that run parallel with each other in worker nodes. All these worker nodes compute the statistics and send them to the drive node, which in turn, aggregates them and decides splitting criteria for the tree. The same process can be visualised in the image given below:

![Distributed Decision Trees](https://i.ibb.co/kMB8BZG/Distributed-Decision-Trees.png)

Working with distributed trees divides the load and data over different partitions which run parallel to each other and hence reduce the overall time as compared to a single tree that runs alone. 

**Level-Wise Training:**  
The next optimisation available is level-wise training in Spark. Sajan will explain the same in the upcoming video:

**VIDEO**

As the name suggests, level-wise training in parallel divides the data into different levels that run parallelly. Generally, while using a Decision Tree, you choose a root node and then decide splitting criteria and divide the data based on the splitting criteria as shown in the image given below:

![Spark Decision Trees](https://i.ibb.co/Yc2ZRz2/Spark-Decision-Trees.png)

However, when Spark uses level-wise training, then, rather than passing the data to one node at a time, it passes the data to all the nodes at the same level. Hence, you are reducing the number of data passes drastically, saving a lot of computation time and resources. Let’s now watch the following video to see how the performance of the cluster changes by using level-wise training in Spark:

**VIDEO**

In this video, you saw how the performance increased by using optimisation techniques, such as level-wise training. Therefore, these methods are beneficial while running a Decision Tree in Spark. The last method of optimisation that you are going to learn is Binning. Take a look at the upcoming video to understand it better:

**VIDEO**

**Binning:**

Binning comes into play while using Regression Decision Trees. While working with continuous values, mid-points are computed. If the number of columns having continuous variables is more, then the time required for computation increases drastically. At this point, binning comes into the picture. As the name suggests, bins are created rather than taking each value separately. Suppose you have the following points: [15,20,29,30,37,45,52,65]. You divide the points into bins of data. Take a look at the image given below to understand it better:

![Spark Binning](https://i.ibb.co/02wV05c/Spark-Binning.png)

Now, rather than computing splitting values for all of them, you can do the same for each bin. The parameter used in a Decision tree to decide which value is most optimal is maxBins. The optimal value of maxBins can be decided by hyperparameter tuning. The decision is made based on the following criteria: 

1.  If maxBins is less: less training time and accuracy can decrease
2.  If maxBins is large: more training time, and higher accuracy

#### Optimisation in Spark

Qn: Which of the following is an optimisation method for continuous variables in Spark?

- Binning

- Level-wise Distribution

- Distributed Decision Trees

- None of the above.

Ans: A. *Binning is the optimisation for continuous variables. Rather than considering each continuous value, bins of those values are created.*

You learnt about the Decision Trees and how they work. Now, let’s solve some graded questions based on your learnings.