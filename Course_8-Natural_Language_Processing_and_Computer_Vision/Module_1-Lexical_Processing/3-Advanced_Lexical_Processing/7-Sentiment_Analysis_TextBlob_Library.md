# Sentiment Analysis: TextBlob Library

The TextBlob library is a pre-trained language model that can be used to classify text on the basis of sentiments. 

Let’s first take a look at a demonstration of building a classification model using the TextBlob library. 

**VIDEO**

As you saw in this video, there was no training phase involved. The training is already done and the coefficients for each unique token are stored in the library.   
 
```python
from textblob import TextBlob
  
 #Create a function to get the polarity
def getPolarity(text):
    return TextBlob(text).sentiment.polarity
 
def getAnalysis(score):
    if score < 0:
        return "negative"
    else:
        return "positive"
    
imdb["textblob"] = imdb["review"].apply(getPolarity)
imdb["textblob_flag"] = imdb["textblob"].apply(getAnalysis)
```

By executing the above-mentioned code, you are using the pre-trained TextBlob model to predict the sentiment of the review. TextBlob is a language model based on neural networks; going deep into the working of textbooks is out of the scope of this module. Let’s focus on its execution. It takes a document as input and assigns a sentiment score to it. Then, a threshold of 0 is set. If the score is above 0, mark the review as positive, else mark it as negative. Quite simple, right? 

Let’s now take a look at the performance of the TextBlob model whn implemented for the IMDB data. 

```python
#Classification report predictions from TextBlob
textblob_report=classification_report(test_sentiments,imdb["textblob_flag"][8000:],target_names=['Positive','Negative'])
print(textblob_report)
```

To make an ‘apples to apples’ comparison, you have used the same set of reviews ‘8001 to 10000’. Given below are the evaluation metrics of the TextBlob model. 

![TextBlob Model Metrics](https://images.upgrad.com/edba1682-780a-4bbc-9067-de11207440f7-29.png)

Compared to the TFIDF model, the TextBlob model is poorer in performance with respect to almost all the metrics. If that is the case, then why do we even bother with such models? 

The answer is ‘generalisability’. The TextBlob model is generalisable. What you need to understand is that the TFIDF model was explicitly trained on the IMDB dataset. Suppose you use the same TFIDF model on a sports tweets dataset, what do you think will be the model performance? Most probably, the TextBlob will perform well in that case because there will be many tokens that the TFIDF model has not even seen before. 

With that, you have reached the conclusion of the sentiment analysis case study.

**VIDEO**

In this video, Mahesh recapped the entire case study and the important learnings from it.

#### Pretrained Model

Qn: What are the advantages of using a pre-trained model for language processing? More than one option might be correct.

- Easy setup 

- Quick execution time 

- Generalisability

- Simple code

Ans: All of the Above. *You can install most of the pre-trained models using simple pip commands. Since the training is already done, the model is directly used to make predictions. Consequently, the computational effort is low too. Most of the pre-trained models are built such that they can be applied to most cases. The execution code is as simple as importing the model and using it as a function.*

What are the three most important things that you learned from this case study?