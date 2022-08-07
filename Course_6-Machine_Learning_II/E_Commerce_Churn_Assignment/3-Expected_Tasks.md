# Expected Tasks

You are now well-versed with the end objective of the assignment. You are supposed to build a model that best predicts the churn of a customer who has a product in the cart. Now, let’s watch the following video to get a broad overview of the tasks expected in the assignment.

**VIDEO**

There are four major tasks that you need to perform to complete the assignment as mentioned below.

1.  Task 1: Data Exploration
	- Slice and dice data to understand each column
	- Generate plots to understand the distribution
2.  Task 2: Feature Engineering
	- Advanced EDA & Feature Engineering for model building 
3.  Task 3: Model Selection
	- Logistic Regression
	- Decision Tree
	- Random Forest
4.  Task 4: Model Inference
	- Interpretation fo results 

Before you begin, you will need an environment to host the PySpark environment for executing all the required tasks mentioned above. Therefore, you are expected to work with the following EC2 instance:

-   AMI name - **spark-jupyter**
-   AMI ID - **ami-0437a7d30763297af**
-   Instance type - **m4.xlarge**
-   EBS volume size - **50 GB** (General purpose)

The following document describes all the steps required to launch the instance with the required configuration.

Download [EC2-Instance-Launch](Docs/Amazon_Web_Services/EC2_Instance_Launch.pdf)

Once you have the instance ready, you will find the data in the instance under the '**inputdata'** folder. You can check the directory using the `ls`command after launching the instance. Therefore, you must not load the data again. However, you must upload the notebooks from the link provided below.

Jupyter Notebooks

Download

Moreover, to optimise the process in Spark, you must follow the steps mentioned below.

-   Set the driver memory for Spark as 14 GB (default is 2 GB). Since the dataset is huge (>5GB ), Spark will need larger memory to execute all the operations without any error.
-   Instead of working with the entire dataset, you can generate a sample to experiment and come up with the required code. You can then replicate the steps on the entire dataset.
-   You must save the dataframe in parquet format and relaunch the EC2 instance at different stages in the assignment. This will prevent you from performing the same steps multiple times and also save the driver memory, resulting in faster execution as well.

Now, let's proceed with the required steps under each task.

## Task 1

We will understand each of them in detail. Let’s start with task 1, Data Exploration.

**VIDEO**

In the first task, you are provided with a set of subtasks that must be performed in order to explore the given data for the month of October 2019. In the process, you are expected to load the data and use the required libraries (Python/Spark) to perform the expected tasks in PySpark.

The visualisation libraries (Matplotlib and Seaborn) are not installed on the instance. You can use the pip command on the EC2 terminal to install them before proceeding with the steps:

-   `pip3 install matplotlib`
-   `pip3 install seaborn` 

![Task 1 - Data Exploration](https://i.ibb.co/B3W5tYt/Task-1-Data-Exploration.jpg)

(Popularity is measured by the frequency of all the activities recorded for the product - view, cart, purchase and remove.)

**Important Note**: The results and inferences can be submitted in a separate report explaining your inferences at each step.

You should also perform additional tasks to gain a better understanding of the dataset. However, you must be careful that they do not affect the results of future tasks. Also, the resources offered are limited, and due to the large size of data, you must think before running any transformation or action on the data.

## Task 2

Now, let's watch the video given below to understand the second task.

**VIDEO**

As mentioned in this video, the next task involves feature engineering where you are expected to build different columns to predict the customer churn better.

![Task 2 - Feature Engineering](https://i.ibb.co/WxQ52jt/Task-2-Feature-Engineering.jpg)

As mentioned by Sajan in the video provided above, you will require window functions to generate some of the attributes from the given data. You can read about it from the links provided below.

-   Link 1: [Official Spark documentation](http://spark.apache.org/docs/latest/api/python/pyspark.sql.html?highlight=window#pyspark.sql.Window)
-   Link 2: [Databricks explanation](https://databricks.com/blog/2015/07/15/introducing-window-functions-in-spark-sql.html)

Also, this section holds one of the key steps in the entire process of solving the assignment. You must generate the target variable from the given data as explained in the following image:

![Generate Target Variable](https://i.ibb.co/7rpCJL5/Generate-Target-Variable.jpg)

Every purchase will involve multiple steps. The customer will first view the product, then, add it to the cart, and finally, make the decision of buying or removing it from the cart. Since the model is based on the items that were bought from his/her cart, you must generate the column ‘**is_purchased**’, which reflects that the user has purchased the item that was present in his/her cart. Note that once the column is generated, you must drop all the additional rows associated with that item to remove redundancy in the dataset. For example, if you have purchased a particular item, you need to remove the multiple entries of that product for that user by taking a look at the column ‘event’.

## Task 3

After task 2, you will have the data ready for model building. Here, you are expected to build multiple models and select the best one to generate the prediction. Let’s gain an understanding of the steps associated with this task.

**VIDEO**

The image given below summarises the steps for task 3.

![Task 3 - Model Selection](https://i.ibb.co/dsNLKFm/Task-3-Model-Selection.jpg)

You must remember that you are expected to compare the best models generated from the three algorithms after performing feature selection and hyperparameter tuning. You must keep a note of the following elements in different models:

-   Logistic Regression:
    -   Feature selection is justified.
    -   Multiple models are built after different optimisations.
    -   The threshold value for the prediction is justified.
    -   The chosen metric for the comparison of models is apt and justified.
-   Decision Trees and Random Forest:
    -   Hyperparameter tuning is performed using [ParamGridBuilder](http://spark.apache.org/docs/2.4.5/ml-tuning.html) from the Spark library. (Refer to the SGC sessions for more information.)
    -   The chosen metric for the comparison of models is apt and justified.

You must also suggest how the chosen model is the best fit for the problem. Now, let’s move on to the next task.

**Important Note**: The results and inferences can be submitted in the same report explaining your inferences at each step.

## Task 4

Once the final model is ready, you must use this model to draw inferences. In the next video, let’s hear from Sajan about this task.

**VIDEO**

![Task 4 - Model Inference](https://i.ibb.co/N7mMLF8/Task-4-Model-Inference.jpg)

In the final task, you must draw inferences from the model by providing the most important features that affect the churn of a customer. Also, you must try to visualise how these attributes affect the final prediction.

**Important Note**: The results and inferences can be submitted in the same report explaining your inferences.

The next segment will help you understand the evaluation scheme for the assignment.