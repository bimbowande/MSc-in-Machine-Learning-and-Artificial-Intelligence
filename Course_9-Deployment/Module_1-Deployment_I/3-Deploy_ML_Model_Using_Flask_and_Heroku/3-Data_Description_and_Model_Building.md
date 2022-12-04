# Data Description and Model Building

In this segment, you will learn about the deployment of an ML model. Also, this segment includes a case study on house price prediction based on a linear regression model. You will perform the end-to-end model deployment steps in this case study.

Before we begin, the forthcoming video will help you to understand the dataset and its features.

**VIDEO**

The dataset and all relevant files are provided here.

Download [Deployment Files](home_price_pred.zip)

Descriptions of the dataset’s features can be found in the file named dataset_description attached below.

Download [newhousing_description](newhousing_description.xlsx)

You are also provided with all code files so that you can run them along with the videos.

Here, price will act as the output, and the other features will act as the input features for the linear regression model. 

In the next video, you will see the description of the data and the building of the linear regression model.

**VIDEO**

You are now well aware of the linear regression model and some of the preprocessing steps on the dataset. Mithun has dropped some of the features, which were irrelevant, and retained only nine features.

You learned that when you put the input features in the form of an array as:   
`[5500, 3, 2, 2, 1, 0, 1, 1833.22, 0.667]`

Then, the output will be predicted as ? 6026937.94. 

In the next segment, you will learn how to save this linear regression model on disk, which is also known as the encapsulation of an ML model. To save the ML model, you will use “pickle.” You will learn this in detail in the next segment.

#### Model Selection

Qn: Can you explain why a linear regression model has been selected for this particular case study?

Ans: *As you know, the dataset is about house price prediction. It has multiple columns, which work as features, and the output column is the “price” of a house. The price of a house is a continuous numerical variable. And to predict a continuous numerical variable, such as price, you need to have a linear regression model as the baseline model.*
