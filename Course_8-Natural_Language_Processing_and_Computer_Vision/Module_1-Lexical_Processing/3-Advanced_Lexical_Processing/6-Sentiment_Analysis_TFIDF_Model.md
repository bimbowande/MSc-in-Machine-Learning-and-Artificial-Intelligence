# Sentiment Analysis: TFIDF Model

Now, let’s repeat the entire model building process with only one change: using TFIDF to extract features from the text. In the next video, let’s take a look at a demonstration of the process. 

**VIDEO**

As you learnt from the video, the overall model building process was exactly similar to the process used from the BoW model. 

1. Extract the features 

2. Split the train and test data features 

3. Split the labels 

4. Train the model 

5. Use the model for prediction 

The code used to build the model using the TFIDF is given below.

```python
#Transformed train reviews
norm_reviews=imdb.review

#Term-frequencey * inverse document frequency matrix
from sklearn.feature_extraction.text import TfidfVectorizer

#Applying TF-IDF vectorizer
tv=TfidfVectorizer()

#Fitting model on entire data
tv_fit = tv.fit(norm_reviews)

#Normalised train reviews
norm_train_reviews=imdb.review[:8000]
print('train:','\n',norm_train_reviews[0])
norm_train_tv_reviews=tv_fit.transform(norm_train_reviews)

#Normalised test reviews
norm_test_reviews=imdb.review[8000:]
print('test:','\n',norm_test_reviews[8001])
norm_test_tv_reviews=tv_fit.transform(norm_test_reviews)

norm_train_tv_reviews.shape

#Splitting the sentiment data
train_sentiments=sentiment_data[:8000]
test_sentiments=sentiment_data[8000:]

from sklearn.linear_model import LogisticRegression,SGDClassifier

#Training the model
lr=LogisticRegression(penalty='l2',max_iter=500,C=1,random_state=42)

#Fitting the model for tf-idf features
lr_tfidf=lr.fit(norm_train_tv_reviews,train_sentiments)
print(lr_tfidf)

#Predicting the model for tf-idf features
lr_tfidf_predict=lr.predict(norm_test_tv_reviews)
print(lr_tfidf_predict)
```

Only addition of a piece of code in the segment shown above is the part where Mahesh checks the shape of the feature matrix. The feature matrix has 8000 rows and 62623 columns, which implies that there are 62623 unique words in the corpus.

Each review will be, on average, about 100 or 200 words long. So, most of the feature matrix will be filled with 0s with only a few non-zero values. 

Notice the fit and transform commands are separated again. First, the fit command is executed on the entire dataset, and then the transform command is executed separately on the train and the test dataset. The logic is also the same, by executing the fit command on the entire dataset you make sure that the feature matrix stays uniform. 

Other than the shape of the feature matrix everything else is the same. Mahesh also trained a different logistic regression model for TFIDF features. Now, let’s compare the model predictability for both these models.

**VIDEO**

On comparing both the logistic models, it seems that their predictability are very close to each other. In the video, you learnt the various metrics that are used to evaluate a classification. Let’s take a look at the code used. 

```python
from sklearn.metrics import classification_report, confusion_matrix, accuracy_score

#Accuracy score for bag of words
lr_bow_score=accuracy_score(test_sentiments,lr_bow_predict)
print("lr_bow_score :",lr_bow_score)

#Accuracy score for tf idf features
lr_tfidf_score=accuracy_score(test_sentiments,lr_tfidf_predict)
print("lr_tfidf_score :",lr_tfidf_score)
```

In this video, you first saw a comparison of the accuracy of the models. The accuracy score indicates the number of correct predictions as compared to the total number of predictions. You have already seen that the number of positives and negatives in the dataset are balanced. So, comparing the accuracy of the models will give you a fair comparison of the performance of both models. 

| lr_bow_score   | 0.8654 |
| -------------- | ------ |
| lr_tfidf_score | 0.8675 |

The accuracy score for both the models is the same upto two decimal places.

Next, you saw a comparison between all the other evaluation matrices, such as recall, precision, etc.   
 
```python
#Classification report for bag of words 
lr_bow_report=classification_report(test_sentiments,lr_bow_predict,target_names=['Positive','Negative'])
print(lr_bow_report)

#Classification report for tf idf features
lr_tfidf_report=classification_report(test_sentiments,lr_tfidf_predict,target_names=['Positive','Negative'])
print(lr_tfidf_report)
```

Again most of the metrics used are almost similar with minor variations. 

![TFIDF Model Metrics](https://i.ibb.co/9v2jR9H/TFIDF-Model-Metrics.png)

For example, if you require better precision, you might want to choose the BoW model, but for better recall, TFIDF model will be more appropriate. So, you might want to select a model on the basis of your requirement. Same is the case with the confusion matrix as well. The values in the confusion matrix are quite similar. 

![TFIDF Model Confusion Matrix](https://i.ibb.co/d4rBP9S/TFIDF-Model-Confusion-Matrix.png)

First four values belong to the BoW model and the next four values belong to the TFIDF model. 

#### Model Comparison

Qn: The IMDB data we are considering has an almost equal number of positive and negative sentiment reviews. For such a balanced dataset, which of the following matrices would you give a fair assessment of model predictability?   
 
- Accuracy 

- Recall 

- Precision

- All the above

Ans: D. *All the above metrics will provide a good assessment of model predictability.*

In this case study, you trained your own model. Model training was possible because the dataset had only 10000 rows and 62000 unique words. Imagine if you had to build a similar model for Twitter’s data. It will have millions of rows and columns. Obviously, you can get high performance hardware or you can use pre-trained models. 

In the next segment, let’s use a pre-trained model called the TextBlob library to build a model for the same case study.