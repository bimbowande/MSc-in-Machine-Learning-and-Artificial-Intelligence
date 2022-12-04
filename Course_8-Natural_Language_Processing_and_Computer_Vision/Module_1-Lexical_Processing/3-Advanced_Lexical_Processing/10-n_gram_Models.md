# n-gram Models

When you use Google keyboard or gmail, do you realise that it recommends the next word to you. How does it know what word you might want to type next? 

Let’s first hear Mahesh describe the language models used in such predictive models. 

**VIDEO**

As Mahesh explained in this video, these models use probability distributions to determine the word that is most likely to come after the last word you have typed. Similar to all other machine learning models, the execution of this model is also split into two parts, which are as follows: 

1.  Model training using the training data
    
2.  Prediction and testing using the test data
    

In the next video, you will learn the training part of the language models. 

**VIDEO**

Training, in this case, comprises calculation of the probability of each word given the first word. Let’s summarise the example provided in this video. 

Suppose the last word you typed in the text was ‘come’. Now, you need to search the entire corpus of text and find the word ‘come’. 

![N-Gram Model 1](https://i.ibb.co/cQP90xP/N-Gram-Model-1.png)

Next, you need to find the probability of occurrence of each word that appears after ‘come’. This probability can be determined by taking the ratio of the total number of times a particular word appears after ‘come’ to the total number of documents that have the word ‘come’. For instance, in the given corpus, if you want to find the probability of the word ‘to’ to appear after the word ‘come’:

Probability = 2/9, considering the 9 documents shown above. 

Similarly, if you repeat the exercise for the rest of the words, you will obtain a probability distribution, as shown below:

![N-Gram Model 2](https://i.ibb.co/HXjwp8L/N-Gram-Model-2.png)

Now, you have a probability distribution for all the words available in corpus. The next step is to make some predictions that can be shown to the user. 

**VIDEO**

It is quite straight forward from here. You recommend the most probable word. If you need to recommend three words, you recommend the top three most likely words. 

![N-Gram Model 3](https://i.ibb.co/23DBYMm/N-Gram-Model-3.png)

Finally, there is one variation. Till this point, you have learnt how the recommendation process works when a single word is being considered to predict the next word. What if you want to take more than one word into consideration? Let’s take a look at how that is done in the upcoming video. 

**VIDEO**

The process of recommending subsequent words considering two or even three previous words is exactly the same as it is for one word. 

1.  Find all the documents with the given sequence of words. 
    
2.  Calculate the probability distribution of all the succeeding words. 
    
3.  Recommend the words with the maximum probability. 
    

If only one preceding word is considered, it is called the unigram model; for two words, it is called the bigram model; for three words, it is called the trigram model; and so on. For n preceding words, it is called the **n-gram** model. 

Only thing you need to be careful about is that more the number of words you need to consider for prediction, more amount of data is the data needed to find an acceptable probability distribution. 

Moreover, the use of probability distribution to predict the next word is just one way to build a word prediction model. You are encouraged to look for other better ways to build such models. 

#### Language Model

Qn: Use the text corpus given below to answer the following question. 

```
S1: John told you to come to the market.  
S2: Can you please come here?  
S3: Can you please come to meet Sofia?  
S4: I suggest you do not come to the party.  
S5: Please come with Harry.  
S6: May I come in?  
S7: Dreams come true.  
S8: Why don’t you come to the audition?  
S9: May I come help you?
```

What is the probability of the word ‘with’ occurring after the words ‘please come’?

0.5

0.25

0.33

0.63

Ans: C. *‘Please come’ occurs three times in the corpus. Out of those three, ‘with’ comes only once. So the probability is 1/3.*

That is a good introduction to the language models and lexical processing in general. In the next segment, let’s summarise what you have learnt till now.