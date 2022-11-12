# Sentiment Analysis: BoW Model

Now, the text in the IMDB dataset is clean and ready for feature extraction. You have already learnt feature extraction techniques, such as BoW and TFIDF. Mahesh will apply both these techniques to the dataset to extract features. Later, logistic models will be built using both these sets of features and the predictability of the models built using these features will be compared. 

In the next video, Mahesh will explain and demonstrate the complete process of feature extraction and model building. 

**VIDEO**

Let’s summarise the steps shown in this video. 

### LabelBinarizer

Recall the IMDB dataset. It had two columns: the reviews and the labels for each review, that is, either ‘positive’ or ‘negative’. Even the labels need to be in numerical form for the logistic algorithm to process them. The label column is categorical with only two classes. So, it is quite easy to convert categorical data into numerical data. To this end, the code given below was used in this demonstration.

```python
from sklearn.preprocessing import LabelBinarizer

#Labelling the sentient data
lb=LabelBinarizer()

#Transformed sentiment data
sentiment_data=lb.fit_transform(imdb['sentiment'])
print(sentiment_data.shape)
```

LabelBinarizer is a function that converts categorical labels into numerical labels. You simply import the function and apply it to the relevant column. 

### Extracting features

Now, to convert the clean IMDB data into features, you use a function called the CountVectorizer. Like most of the other prebuilt algorithms, there are two different stages in the application: first fit the algorithm, and then, transform the data. The ‘fit’ and the ‘transform’ stages aremore complex in case of text data than normal data. 

The ‘fit’ command is executed using the code shown below. 

```python
from sklearn.feature_extraction.text import CountVectorizer

#Creating a matrix with reviews in row and unique words as columns 
# and frequency of word in review as values.
#Count vectorizer for bag of words
cv=CountVectorizer()

#Fitting model on entire data
cv_fit = cv.fit(norm_reviews)
```

Recall the feature matrix. The columns in the feature matrix are unique words in the corpus and the rows are count vectors describing specific documents. When the fit command is executed, all the unique words from the entire corpus are collected together. The code shown above executes the fit command. Next comes the transform command, and here, the complexity begins. Let’s take a look at the code first.   

```python
#Normalised train reviews
norm_train_reviews=imdb.review[:8000]
print('train:','\n',norm_train_reviews[0])
norm_train_cv_reviews=cv_fit.transform(norm_train_reviews)

#Normalised test reviews
norm_test_reviews=imdb.review[8000:]
print('test:','\n',norm_test_reviews[8001])
norm_test_cv_reviews=cv_fit.transform(norm_test_reviews)
```

Let’s summarise the fit and transform process. 

1. Fit the BoW model on the entire text corpus. 

2. Split the data into ‘train’ and ‘test’. 

3. Independently transform the train and test datasets. 

Why do we perform the Fit operation first and then apply the transform operation Independently on the train and test datasets?

Let’s take a look at a very simple example to understand this. 

Consider that you have a dataset of text as shown below. 

Document 1: Word_1 Word_2

Document 2: Word_2 Word_3 

Document 3: Word_1 Word_2 Word_4

When the fit command is executed on the entire dataset, the feature matrix will contain columns corresponding to all four unique words. Thus, there will be four columns in the feature matrix. 

Next, the data is split into ‘train’ and ‘test’ datasets. In this case, let documents 1 and 2 represent the training data. The feature matrix with the training data will be as shown below:

|      | Word_1 | Word_2 | Word_3 | Word_4 |
| ---- | ------ | ------ | ------ | ------ |
| Doc1 | 1      | 1      | 0      | 0      |
| Doc2 | 0      | 1      | 1      | 0      |

Then, the transform command picks up each document, cross-checks the tokens in the document with the feature list and populates the row with the right values. **So, by executing the fit command on the entire dataset, you have made sure that there are four values in each row corresponding to each w.**

Even if ‘Word_4’ is exclusively present in the test dataset, and if all the values in that column are 0, by keeping the words unique to test data in the fit command, you have ensured that the length of the count vector will not change. But, why is it necessary to keep the length of the count vector the same for all documents? 

Recall the machine learning algorithms you have learnt. The actual computations occur on matrix equations. So, all rows in the matrix need to have the same shape. If the rows have inconsistent shapes, the matrix operations will not work.  

Hence, by creating the feature matrix such that it contains all the unique words from the given text corpus, you are, in a way, ensuring that the length of the feature matrix stays the same. This is the reason for executing the fit command on the entire data but executing the transform command only on the training set. 

Next, you will also need to separate the labels for each document. The code given below will split the labels. 

```python
#Splitting the sentiment data
train_sentiments=sentiment_data[:8000]
test_sentiments=sentiment_data[8000:]
```

Here, simple series indexing is used to split the data. Now that you have the train and the test sets, you are ready to build a model. In the code given below, let’s take a look at the model building process. 

```python
from sklearn.linear_model import LogisticRegression,SGDClassifier

#Training the model
lr=LogisticRegression(penalty='l2',max_iter=500,C=1,random_state=42)

#Fitting the model for the bag of words
lr_bow=lr.fit(norm_train_cv_reviews,train_sentiments)
print(lr_bow)
```

As you can observe in the code, a simple logistic regression model with L2 regularisation is used to build the classification engine. The output of the print command is information about the logistic model. Then, you use this model to make predictions for the test dataset. 

```python
#Predicting the model for bag of words
lr_bow_predict=lr.predict(norm_test_cv_reviews)
print(lr_bow_predict)
```

This code is familiar to you nothing now to learn. Use the data attached to solve question two below. 

Download Data for segment five question two

#### Stop Word Removal

Qn: Consider the corpus given below. 

```python
corpus = [
   'This is the first document.',
    'This document is the second document.',
    'And this is the third one.',
    'Is this the first document?'
]
```

Assume that the only stop words you want to remove from the corpus above are [‘the’, ‘is’].

Which of the following code snippets will be able to remove only these specific stop words? Make sure that the number of documents in the output is also the same as the input.   

- ```python
  tokens = tokenizer.tokenize(corpus)
  Stopword_list = ["the", "is"]
  clean_tokens = [token for token in tokens if
  token not in stopword_list]
  clean_text = ' '.join(clean_tokens)
  ```

- ```python
  tokens = tokenizer.tokenize(corpus)
  Stopword_list = ["the", "is"]
  clean_tokens = [token for token in tokens if
  token not in stopword_list]
  ```

- ```python
  tokens = tokenizer.tokenize(corpus)
  Stopword_list = nltk.corpus.stopwords.words('english')
  clean_tokens = [token for token in tokens if
  token not in stopword_list]
  clean_text = ' '.join(clean_tokens)
  ```

- ```python
  tokens = tokenizer.tokenize(corpus)
  Stopword_list = ["the", "is"]
  clean_tokens = [token for token in tokens if
  token in stopword_list]
  clean_text = ' '.join(clean_tokens)
  ```

Ans: A. *This code will only remove the words ‘the’ and ‘is’ from the documents and also join the tokens back to form the right number of documents.* 

#### Bag-of-words model

Qn: Use the first 100 rows of the spam messages data to create a bag-of-words model after changing the text to lower case, tokenising and removing stop words (you can use the preprocess function that you saw professor Srinath use in the bag-of-words demonstration video). Print the shape of the bag-of-words matrix. What are the number of rows and columns in the matrix? Hint: use this following command to read the data file. 

```python
#Importing the training data
spam = pd.read_csv("SMSSpamCollection_1.txt", sep = "\t", names=["label", "message"])
```

- 100 rows and 560 columns

- 100 rows and 726 columns

- 100 rows and 640 columns

- 100 rows and 340 columns

Ans: C. *The code below will help you find the shape of the matrix.* 

```python
#Load the libraries
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
import matplotlib.cm as cm
import nltk
from nltk.tokenize import word_tokenize
from nltk.corpus import stopwords
from sklearn.feature_extraction.text import CountVectorizer

nltk.download('punkt')
nltk.download('stopwords')

import os
import warnings
warnings.filterwarnings('ignore')
nltk.download('stopwords')

#Importing the training data
spam = pd.read_csv("SMSSpamCollection_1.txt", sep = "\t", names=["label", "message"])
spam.shape

# get the first 100 rows
spam = spam.iloc[0:100,:]

# get the actual data from messages column
messages = spam.message

# convert messages into list
messages = [message for message in messages]

def preprocess(document):
    'changes document to lower case and removes stopwords'

    # change sentence to lower case
    document = document.lower()

    # tokenize into words
    words = word_tokenize(document)

    # remove stop words
    words = [word for word in words if word not in stopwords.words("english")]

    # join words to make sentence
    document = " ".join(words)
    
    return document

# preprocess messages using the preprocess function
messages = [preprocess(message) for message in messages]

# create the bag of words feature matrix  
vectorizer = CountVectorizer()
bow_model = vectorizer.fit_transform(messages)

bow_model.shape
```

*The output of this code is (100, 640)*

Qn: What is the total sum of all the values of the bag-of-words model that you created in the last question?

Ans: 934

```python
# convert the bag of words sparce matrix to an array and then get the sum of all elements. 
bow_model.toarray().sum()
```

So, with that, the demonstration of the model building process on the features extracted by the BoW algorithm comes to an end. In the next segment, let’s take a look at the same steps for the TFIDF algorithm.