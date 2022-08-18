# Problem Statement

Now that you have got an understanding of the sales funnel, in the following video, Sajan will walk you through the problem statement associated with the assignment.

**VIDEO**

As part of this assignment, you are expected to build a model that predicts whether or not a person purchases an item present in his or her cart. The assignment is based on the final stage of the funnel, where a customer purchases an item that has been loaded in the cart. However, you may be wondering how a company can benefit from this activity. Let’s watch the next video to understand the same.

**VIDEO**

Until now, you understood the inferences that can be drawn from this model and learnt how they can help the company to achieve higher revenue. Therefore, building such a model will be of great benefit to the company. However, before building any model, you must be aware of the information that you have to execute the required tasks. In the next video, Sajan will talk about the different attributes present in the dataset.

**VIDEO**

As explained by Sajan in this video, you will be provided with a data set that contains the following attributes:

-   **event_time**: Date and time when the user accesses the platform
-   **event_type**: Action performed by the customer
    -   View
    -   Cart
    -   Purchase
    -   Remove from cart
-   **product_id**: Unique number to identify the product in the event
-   **category_id**: Unique number to identify the category of the product
-   **category_code**: Stores primary and secondary categories of the product
-   **brand**: Brand associated with the product
-   **price**: Price of the product
-   **user_id**: Unique ID for a customer
-   **user_session**: Session ID for a user

Note that the dataset stores the activity on the e-commerce platform for the month of October 2019. It is stored in the following [path](https://mlc-c5-assignment.s3.amazonaws.com/2019-Oct.csv):

-   S3 Bucket: mlc-c5-assignment
-   Filename: 2019-Oct.csv

You are **not expected** to download or upload the data from the public S3 bucket. A copy has been put in the EC2 instance where you will be hosting PySpark. You will learn about this in detail in the next segment.