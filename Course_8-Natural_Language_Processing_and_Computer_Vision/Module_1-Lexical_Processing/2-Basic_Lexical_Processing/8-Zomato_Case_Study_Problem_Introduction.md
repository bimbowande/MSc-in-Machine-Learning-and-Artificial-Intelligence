# Zomato Case Study: Problem Introduction

So far in this session, you have learnt about the following text preprocessing steps: 

1.  Text encoding (ASCII, Unicode, etc.)
    
2.  Converting to lowercase
    
3.  Removing symbols and punctuation marks
    
4.  Handling numbers
    
5.  Removing stop words 
    
6.  Tokenisation
    
7.  Stemming and lemmatisation
    

In this segment, let's apply all these techniques to a real-life data set. You will be using the Zomato reviews data set. The objective of this case study is to process the data and bring it to a stage where feature extraction can begin. 

In the next video, Mahesh will introduce the data set. You can find the link to the Notebook being used in the demonstration below. It is recommended that you code along with our faculty member. 

Download Zomato Reviews [Dataset](Restaurant reviews.csv) + [Notebook](Lexical_Processing-Zomato_Reviews.ipynb)

**VIDEO**

In this video, Mahesh demonstrated the data that you will be working on. The data has multiple columns, but for this exercise, you will consider only the Review column.

![Review Sample](https://i.ibb.co/h2vXStj/Review-Sample.png)

Next, let’s hear Mahesh explain the problem statement. 

**VIDEO**

As explained in the video, the objective of this demonstration is to process the reviews. To that end, you will be using all the techniques that you have learnt so far in this session. Let's get started. 

The first step in any Notebook-based demonstration is to import all the necessary libraries. Let’s watch the next video to see which libraries you may need for this case study. 

**VIDEO**

As you saw in this video, in addition to the necessary libraries such as Pandas and NumPy, we imported the NLTK library and downloaded stop words as well. The reviews data was read into a Pandas data frame, and you saw a few samples of how people write reviews. 

  
In the next segment, let’s begin processing the reviews data.