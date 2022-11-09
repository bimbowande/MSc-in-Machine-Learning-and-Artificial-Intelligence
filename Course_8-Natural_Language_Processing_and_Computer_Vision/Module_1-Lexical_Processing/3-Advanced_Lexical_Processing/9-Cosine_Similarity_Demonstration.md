# Cosine Similarity: Demonstration

In previous segments, you learnt the algorithm used to calculate the cosine similarity and you also learnt the interpretation of cosine values. Now, let’s take a look at a demonstration of the calculation of cosine similarities. You can find the notebook for the demonstration below. 

Download [Cosine Similarity: Demonstration](Cosine_Similarity.ipynb)

To keep the demonstration simple and understandable, Mahesh will declare a five-document corpus, and then try to find the similarity between all the individual documents. 

**VIDEO**

This video demonstrated the declaration of text and the text cleaning steps. You are already familiar with these concepts. 

The cleaning steps performed were: 

1.  Convert the words to the lower case
    
2.  Remove the stop words 
    

The code for these steps is given below.

```python
# Dicalring the text corpus 
corpus = ['The sun is the largest celestial body in the solar system', 
          'The solar system consists of the sun and eight revolving planets', 
          'Ra was the Egyptian Sun God', 
          'The Pyramids were the pinnacle of Egyptian architecture', 
          'The quick brown fox jumps over the lazy dog']

# Stop word removal 
stop = set(stopwords.words('english'))
for index, sentence in enumerate(corpus):
  corpus[index] = ' '.join([i for i in word_tokenize(sentence.lower()) if i not in stop])
```

The next step is to create the TFIDF matrix and then calculate the cosine similarity metrics. In the next video, Mahesh will calculate the cosine similarity programmatically. 

**VIDEO**

As you saw in this video, the first step is to create a TFIDF matrix. The code for creating a TFIDF matrix is given below.

```python
# Initialize an instance of tf-idf Vectorizer
tfidf_vectorizer = TfidfVectorizer()
 
# Generate the tf-idf vectors for the corpus
tfidf_matrix = tfidf_vectorizer.fit_transform(corpus)
```

The output of the above-mentioned code is the TFIDF matrix shown below. 

![TFIDF Matrix Cosine Similarity Demo](https://i.ibb.co/qJjx5w4/TFIDF-Matrix-Cosine-Similarity-Demo.png)

From this TFIDF matrix, you can then find the cosine similarity scores. The cosine similarity function is present in the sklearn library. You can import the library and use it to calculate the cosine similarity for the declared corpus. 

The code for calculating cosine similarity is given below.

```python
cosine_sim = cosine_similarity(tfidf_matrix, tfidf_matrix)
print(cosine_sim)
```

From this TFIDF matrix, you can then find the cosine similarity scores. The cosine similarity function is present in the sklearn library. You can import the library and use it to calculate the cosine similarity for the declared corpus. 

The code for calculating cosine similarity is given below. 

![Cosine Similarity Demo](https://i.ibb.co/9sk7sFR/Cosine-Similarity-Demo.png)

Each row and each column represent a document. This matrix will show the relationship between each pair of documents. 

Higher scores represent higher similarity between the documents. The most similar documents in the given corpus are document 2 and document 1, which are shown below. 

**Document 1**: The sun is the largest celestial body in the solar system

**Document 2**: The solar system consists of the sun and eight revolving planets

#### Cosine Similarity

Qn: Consider the text corpus given below.

```python
corpus = [
   'This is the first document.',
    'This document is the second document.',
    'And this is the third one.',
    'Is this the first document?'
]
```

Remove the stop words and find the cosine similarity between the first and the fourth documents. 

- 1

- 0

- 0.49

- 0.73

Ans: A. *After removing the stop words both the documents have exactly the same words.   
You can use the following code to calculate cosine similarity. You can use the following code to find the cosine similarity matrix.*

```python
#Importing Libraries
import numpy as np
import pandas as pd

import nltk
nltk.download('stopwords')
nltk.download('punkt')
from nltk import word_tokenize
from nltk.corpus import stopwords

from sklearn.metrics.pairwise import cosine_similarity
from sklearn.feature_extraction.text import TfidfVectorizer

corpus = [ "this is the first document",
                      "this document is the second document",
                      "and this is the third one",
                      "is this the first document"]

stop = set(stopwords.words('english'))
for index, sentence in enumerate(corpus):
  corpus[index] = ' '.join([i for i in word_tokenize(sentence.lower()) if i not in stop])

# Initialize an instance of tf-idf Vectorizer
tfidf_vectorizer = TfidfVectorizer()

# Generate the tf-idf vectors for the corpus
tfidf_matrix = tfidf_vectorizer.fit_transform(corpus)

cosine_sim = cosine_similarity(tfidf_matrix, tfidf_matrix)
print(cosine_sim)
```

Now, in the next segment let’s learn the concept of n-gram models.