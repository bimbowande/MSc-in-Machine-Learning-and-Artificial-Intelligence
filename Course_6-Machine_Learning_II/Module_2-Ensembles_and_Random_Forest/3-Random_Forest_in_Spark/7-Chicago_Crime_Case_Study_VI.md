# Chicago Crime Case Study - VI

In this segment, we will be creating a variable to store the sequential steps for executing the pipeline. In the upcoming video, Sajan will explain how to use a variable to store the mentioned steps.

**VIDEO**

In this video, we created a new variable ‘stages’. Now, we will use this variable for storing the ML pipeline that prepares the variables for the model by encoding and creating vectors from these values. Let’s see how to do that in the next video.

**VIDEO**

In the video, all the categorical variables are encoded using the OneHotEncoderEstimator. Finally, all the steps were combined into the stages variable and displayed in the notebook.

When training an RF model, you cannot pass the dataframe columns as they are. They need to be converted into the vector format. In the next video, you will see how to create a combined vector for all the features including the continuous and categorical features and add this step to the pipeline variable ‘stages’.

**VIDEO**

You can now club the four steps sequentially in the variable ‘stages’. In the next video, you will see how to import the Pipeline library from pyspark.ml and pass our stages variable in its constructor.

**VIDEO**

In the above video, you have applied the steps in the pipeline on the dataframe using pipeline.fit(‘df’). Now that the data transformation is complete, we will continue the process of model building by splitting the dataset into testing and training sets in the next segment.g