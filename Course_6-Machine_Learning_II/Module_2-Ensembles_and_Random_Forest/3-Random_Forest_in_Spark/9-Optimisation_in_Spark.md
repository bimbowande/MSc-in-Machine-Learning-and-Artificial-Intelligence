# Optimisation in Spark

You are now enriched with both theoretical and practical concepts of the random forest algorithm. You learnt how to build a basic model in the PySpark environment. However, it has been emphasised multiple times that a model must be optimised before it is implemented in a distributed environment. 

You learnt about multiple optimisation techniques that are associated with tree models as part of the previous module:

-   Level-wise training in Spark
    
-   Binning
    
-   Distributed decision trees
    

This segment will help build over the methods that were discussed earlier for you to learn how the algorithm can be further optimised in the Spark environment.

**VIDEO**

As mentioned in the video, the algorithm can be optimised in two ways:

-   Data-based optimisation
    
-   Task-based optimisation
    

## Data Parallel Optimisation

This optimisation is derived from ways in which data can be stored for processing in the Spark environment. The following two methods have been described in the video:

-   **Data multiplexing:** Data multiplexing helps optimise the use of the Spark memory by preventing the creation of multiple copies of the entire dataset for computation over bootstrapped samples. It creates metadata associated with the samples and stores the index of the rows associated with each sample in the form of the Data sampling index (DSI) table. The entire data is broadcasted, and then, Spark can use the DSI table to fetch only the required rows for building the decision tree on the bootstrapped sample. 

![Data Multiplexing](https://i.ibb.co/f44pT0z/Data-Multiplexing.jpg)

You will learn about the second technique along with other optimisation techniques in the following video.

**VIDEO**

-   **Vertical data partitioning:** This method exploits the feature of parallelism associated with the tree models. Here, the data set is split into smaller partitions that store one independent variable along with the target variable. Since the computation of information gain or Gini index for one variable is independent of another, the data can be split and shared across multiple executors for parallel computation. It can prove to be highly useful, as it helps in parallel computation and prevents the creation of multiple copies of the entire data for deciding the splitting criteria.

![Vertical Data Partitioning](https://i.ibb.co/HKYD4H7/Vertical-Data-Partitioning.jpg)

## Task Parallel Optimisation

In this section, you will learn about the second type of optimisation - task-parallel optimisation. The computation of each tree in the algorithm is independent of others. The data associated with each tree can be distributed over different executors and processed parallelly. Higher the parallelism, more optimised is the execution. Once you have built all the trees, results from each tree can be sent to the driver to combine and give the final result.

All the optimisations mentioned in the segment have resulted in a higher performance of the model in the Spark environment. As mentioned in the video, they are part of the Parallel Random Forest or PRF algorithm. You can read more about it in the research paper mentioned below:

### IEEE Paper Citation
J. Chen _et al_., "[A Parallel Random Forest Algorithm for Big Data in a Spark Cloud Computing Environment](https://arxiv.org/pdf/1810.07748.pdf)," in _IEEE Transactions on Parallel and Distributed Systems_, vol. 28, no. 4, pp. 919-933, 1 April 2017, doi: 10.1109/TPDS.2016.2603511.

#### Data Parallel Optimisation

Qn: Which of the following is true in the context of Random Forest's Data-Parallel Optimisation?

- If the data set contains (M-1) input features and 1 target variable, the number of splits will be M-1.

- In this optimisation, we are taking advantage of Random Forest algorithm's independence of feature variables.

- In data multiplexing, we do not copy the sampled data but just note down their indexes into a Data-Sampling-Index.

- If the dataset contains (M-1) input features and 1 target variable, the number of splits will be M.

Ans: A, B & C. *In Vertical Data Partitioning, each of the (M-1) input variables will be combined with the target variable to create (M-1)  feature subsets, which is then loaded as an RDD object. In the data multiplexing method, we are modifying the traditional sampling method. In each sampling period, we do not copy the sampled data but just note down their indexes into a Data-Sampling-Index (DSI) table. Then, the DSI table is allocated to all slave nodes together with the feature subsets (produced through Vertical Data Partitioning).*

#### RF Algorithms

Qn: Which of the following algorithms have least execution time when used with large data sets?

- Random Forest

- Parallel Random Forest

- Spark ML-Random Forest

- All have the same execution times

Ans: B. *PRF has the least execution time.*

This marks the end of the segment. The next segment will help you summarise the learnings from the session.