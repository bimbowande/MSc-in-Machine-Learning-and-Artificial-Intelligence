# Graded Questions

All the questions given below are graded. All the best! 

To answer the following questions, use the text corpus given below. 

 ```python
corpus = [
"john told you to come market",
"can you please come here",
"can you please come to meet sofia",
"i suggest you do not come to party",
"please come with harry",
"may i come in",
"dreams come true",
"why dont you come to audition",
"may i come help you" 
]
```

Qn: First, remove all the stop words from the corpus. Now, extract all the features from the corpus using the BoW algorithm. Which element is in the (0,7) location? 
  
Hint:

1.  When you print the vectorizer, each non-zero element is printed along with its location.
2.  Code to remove stop words from the corpus is also given below. 

```python
stop = set(stopwords.words('english'))
for index, sentence in enumerate(corpus):
  corpus[index] = ' '.join([i for i in word_tokenize(sentence.lower()) if i not in stop])
```

- 0

- 1

- 2

- 3

Ans: B. *The code file attached below can be used to find the element at the (0,7) location in the feature matrix. Make sure you remove the stop words and only then execute the following code.*

```python
#Creating a matrix with reviews in row and unique words 
# as columns and frequency of word in review as values.
#Count vectorizer for bag of words
cv=CountVectorizer()

#Fitting model on entire data
cv_fit = cv.fit_transform(corpus)

print(cv_fit)
```

Qn: First, remove all the stop words from the corpus. Now, extract all the features from the corpus using the TFIDF algorithm. Which element is in the (1,11) location? 

Hint:

1.  When you print the vectorizer, each non-zero element is printed along with its location.
2.  Code to remove stop words from the corpus is also given below. 

```python
stop = set(stopwords.words('english'))
for index, sentence in enumerate(corpus):
  corpus[index] = ' '.join([i for i in word_tokenize(sentence.lower()) if i not in stop])
```

- 0.886

- 0.462

- 0.610

- 0.223

Ans: A. *The code file attached below can be used to find the element at the (1,11) location in the feature matrix.*

```python
#Creating a matrix with reviews in row and unique words
# as columns and frequency of word in review as values.
#Count vectorizer for bag of words
tf=TfidfVectorizer()

#Fitting model on entire data
tf_fit = tf.fit_transform(corpus)

print(tf_fit)
```

Qn: To answer the following question, use the text corpus given below. 

```python
corpus = ["can you please come here",
"can you please come to meet sofia"]
```

First, remove all the stop words from the corpus. What is the cosine similarity between the documents?

- 0.639

- 0.123

- 0.066

- 0.579

Ans: D. *Find the tfidf for the documents under consideration and find the cosine similarity in them. THe code below will help achieve the same.*

```python
corpus = ["can you please come here",
"can you please come to meet sofia"]

stop = set(stopwords.words('english'))
for index, sentence in enumerate(corpus):
  corpus[index] = ' '.join([i for i in word_tokenize(sentence.lower()) if i not in stop])

# Initialize an instance of tf-idf Vectorizer
tfidf_vectorizer = TfidfVectorizer()

# Generate the tf-idf vectors for the corpus
tfidf_matrix = tfidf_vectorizer.fit_transform(corpus)

# compute and print the cosine similarity matrix
cosine_sim = cosine_similarity(tfidf_matrix, tfidf_matrix)
print(cosine_sim)
```

Qn: When the word "Upgrad" is written in the google search bar it recommends popular searches. Refer to the image below. 

![upGrad Google Search](https://i.ibb.co/b3G9Wdh/up-Grad-Google-Search.png)

Which of the following algorithms is used to predict the next words? 

- BoW 

- TFIDF

- unigram model

- Cosine similarity

Ans: C. *Such word prediction is done by language models. In this case, it is the n-gram model. More specifically since only one word is used for prediction, the ngram mode used is called the unigram model.*
