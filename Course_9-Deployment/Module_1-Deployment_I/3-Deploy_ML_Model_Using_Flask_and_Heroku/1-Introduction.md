# Introduction

In the previous session, you understood what a web application is and how Flask is used to build a web application. You also learned that Flask works as an orchestration between the back end and the front end. 

In this session, you will learn how to deploy a machine learning (ML) model using Flask and Heroku. Let us consider the example of the house price prediction model that you built using a linear regression algorithm. Suppose there are nine features that contribute to the prediction of a particular house's price, which are as follows:

-   Area
-   Number of bedrooms
-   Number of bathrooms
-   Number of stories
-   Number of guest rooms
-   Does the house have a basement?
-   Is there parking available in the house?
-   Average area per bedroom
-   **BBratio:** Bathroom-to-bedroom ratio

The price of a house can be predicted using a linear regression model. Suppose you want to build a front-end application, as shown below, where a user can enter the aforementioned nine features and get the predicted price of a house based on a linear regression model that has been trained at the back end.

![Predict House Price](https://i.ibb.co/yNGX0Xc/Predict-House-Price.png)

To build this web application, you need to develop an HTML page and also have to deploy an ML model so that users can get the predicted/estimated price of a house with this application. 

To build the application, you will use Flask as a tool, which can act as an orchestration between the back end and the front end.  
 
**In this session**

Here is what this session will cover:

1.  Steps to create an end-to-end ML pipeline
2.  A case study on house price prediction using Flask and Heroku
3.  Hands-on with front-end HTML codes
4.  How to create a local web application using Flask
5.  How to create a public web application using Heroku

## **People you will hear from in this module**

[**Abhay Raj Singh**](https://www.linkedin.com/in/abhay263/)  
**Machine Learning Engineer, Quantiphi**

Abhay is working as a machine learning engineer with Quantiphi. He graduated from VIT University and is an analytical professional with more than 3 years of in-depth experience solving multiple business problems across the retail and technology domains for Fortune 500 companies. Currently, Abhay's work mostly revolves around computer vision and MLOps. He has been teaching data science for the past 2 years across multiple platforms located in India and the US. 

[**Mithun Kumar S. R.**](https://www.linkedin.com/in/mithunkumarsr/)

**Engineering Manager, Uber R&D**

Mithun is an engineering manager at Uber R&D. Alongside work, he is working on his PhD research on deep learning from BITS Pilani. Previously, he worked at Disney, Amazon, and Flipkart, among other companies. Mithun's work focuses predominantly on NLP and CV currently, especially around sparsely labeled datasets.