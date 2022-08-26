# Data Preparation - II

The next important concepts that you need to apply in the data preparation stage are outlier treatment and data standardisation. Let's watch the next video to recall these concepts.

**VIDEO**

Now, you will begin with the outlier treatment.

**VIDEO**

Now, let's complete the preprocessing part of data standardisation.

**VIDEO**

**Hopkins Statistics**

You learnt about the Hopkins statistics in the previous session; however, we have skipped its demonstration here. In Python, you can use the code snippet attached below to pass a data frame to the Hopkins statistic function in order to check whether or not the data set is suitable for clustering. For this, you can simply copy the code snippet and paste it in the main data set to analyse the Hopkins statistic value.

Download [Hopkins Statistic Code](Hopkins_Statistic.ipynb)

Keep the following points regarding the Hopkins Statistic in mind:

-   You do not need to know how the algorithm of the Hopkins statistic works. Since the algorithm is quite advanced, you should be able to interpret the value that it assigns to the data frame.
-   On multiple iterations of the Hopkins statistic, you will obtain multiple values. This is because the algorithm uses some level of randomisation in the initialisation part of the code. Therefore, it is recommended that you run it a couple of times before confirming whether the data is suitable for clustering or not.