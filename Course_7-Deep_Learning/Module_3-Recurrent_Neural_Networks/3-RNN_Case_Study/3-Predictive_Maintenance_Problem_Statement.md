# Predictive Maintenance - Problem Statement

The first car that ran on its own source of power was created by Karl Benz in 1885. Yes and that is where Mercedes - Benz got its name. But why are we talking about Mercedes Benz here? You already know that cars run on engines, some really advanced than the rest. Now, consider that you are driving a car and it breaks down somewhere. You will have the time to call the mechanic and get it fixed. Now, replace that vehicle with an aeroplane and answer if you can still do the same? The answer is no. Therefore, aeroplanes need special attention towards the maintenance of their turbo engines. Let’s hear more from the professor about it.

**VIDEO**

As technology becomes more and more advanced, sensors are being used everywhere to track and fix anomalies. Similarly, a lot of sensors are placed around the engine to observe various kinds of data. One other thing you should keep in mind is that every engine is set to a particular configuration setting before taking off.

In the predictive maintenance case study, you will have a data set containing 21 sensor data and three configuration setting values. The problem statement can be any of the following:

1.  After how many cycles (number of flights) is the engine going to fail?
2.  If the engine is going to fail before a certain number of cycles c.
3.  If the engine is going to fail between a certain period of cycles c1 and c2?

For ease of understanding, we will be solving the second problem statement. You are encouraged to solve the other two problems at the end of this demonstration.

We will be using the below attached notebook for code demonstration.

Download [Predictive Maintenance Case Study Notebook](Predictive_Maintenance_Use_Case.ipynb)

Let’s start with importing the required libraries and loading the data set.

**VIDEO**

We have loaded the training, testing and ground truth data into our notebook, which uses the popular read_csv() function of pandas library. An important observation on the dataset is that the number of cycles itself is the source of the target variable considering that the engines fail after running till the maximum number of cycles given in the dataset.

For example if engine 1 has run till maximum cycle number 192, it has failed after that point. You will learn how we derive the target variable out of this column in the next segment along with the other data preprocessing steps.