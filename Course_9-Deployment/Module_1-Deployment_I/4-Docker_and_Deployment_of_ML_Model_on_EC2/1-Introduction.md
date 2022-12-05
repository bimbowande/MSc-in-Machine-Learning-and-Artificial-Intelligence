# Introduction

In the previous session, you learned about Flask and Heroku. You worked on the house price prediction linear model deployment case study. Lastly, you were introduced to APIs and REST.

In this session, you will learn how to deploy models in Docker using Flask.

Suppose you work as a machine learning engineer in a company and need to deploy an ML model using Python 3.7-slim and Flask 1.1.2. Once the application is developed, it needs to be tested by the tester. The tester will set up the same environment from scratch to test the web application. Suppose everything works well, and the application needs to be deployed on a production server. The production will need the same environment versions to host the web application. Now, this approach results in the following issues:

-   Too much time consumption due to the installation of environments at each level of the process
-   A possibility of version mismatch while installing environments at each step, which will cause an error

To avoid these issues, you can use Docker.   

**In this session, we will cover the following topics:**

-   Introduction to Docker
-   Various terminologies associated with Docker
-   Installation of Docker
-   Hello_world implementation using Docker and Flask
-   Docker command-line interface and relevant commands
-   House price prediction model deployment using Docker and Flask

## People you will hear from in this module:

[**Abhay Raj Singh**](https://www.linkedin.com/in/abhay263/)  
**Machine Learning Engineer, Quantiphi**

Abhay is a machine learning engineer with Quantiphi. He graduated from VIT University. He is an analytics professional with 3+ years of in-depth experience solving multiple business problems across retail and technology domains for Fortune 500 companies. Currently, Abhay's work mostly revolves around computer vision and MLOps. He has been teaching data science for the last two years on multiple platforms in India and the US. 

[**Mithun Kumar S.R.**](https://www.linkedin.com/in/mithunkumarsr/)

**Engineering Manager, Uber R&D**

Mithun is an Engineering Manager at Uber R&D. Alongside work, he is currently working on his Ph.D. research in deep learning from BITS Pilani. He previously worked with Disney, Amazon, and Flipkart, among other companies. Currently, his work predominantly focuses on NLP and CV, especially around sparsely labeled data sets.