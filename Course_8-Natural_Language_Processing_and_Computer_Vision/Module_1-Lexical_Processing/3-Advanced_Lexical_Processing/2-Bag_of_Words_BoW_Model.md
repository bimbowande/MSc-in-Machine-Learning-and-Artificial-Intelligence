# Bag of Words (BoW) Model

Any machine learning algorithm works on matrices made of digits and not text. Feature extraction algorithms are responsible for converting a clean text into digits. First let’s hear Dr Balan talk about feature extraction in the next video. 

**VIDEO**

In this video, you learnt a strategy to convert text data into numerical data to create features and feed them into the ML model. Let’s recap the learnings of the video. 

Consider the text corpus given below. It shows text in each document along with its sentiment label. A document in a text corpus is an entity that corresponds to one complete row in the feature matrix. For instance, in the Zomato review dataset, a document was the one entire review. It could comprise multiple sentences or just a few words. For analytics purposes, one review represents one entity and it is referred to as a document.   
 

|       | **Phone review**                             | **Sentiment** |
| ----- | -------------------------------------------- | ------------- |
| Doc_1 | camera, not, good                            | Negative      |
| Doc_2 | screen, awesome, microprocessor, slow, happy | Positive      |
| DOc_3 | hotspot, not, connect                        | Negative      |

Notice the text in the given documents. The text is clean and has no noise, which implies that it is already tokenised and lemmetised and all the stop words have been removed. If you were to convert such a corpus into features, you would arrange all the unique words in the corpus column-wise and each document would be represented row-wise as shown in the matrix below.   
 
![Unique Words in the Corpus Column-Wise](https://i.ibb.co/B3Lz36p/Unique-Words-in-the-Corpus-Column-Wise.png)

Next, you need to learn how to fill the matrix. In each row, you mark zero in the columns corresponding to the words that do not appear in the document. And you fill a value in the columns for words that are present in the document. 

The values that you fill in the columns can be determined through multiple techniques. In this session, you will learn two such techniques, which are as follows: 

1. Bag of words (BoW)

2. Term frequency inverse document frequency (TFIDF)

### Bag of Words (BoW)

In the BoW technique, the values in each cell is just the count of words that are present in that document. The upcoming video will explain the BoW technique in greater detail.

**VIDEO**

As explained in this video, the BoW model uses the frequency of occurrence of a word in a document to fill up the features matrix. To attain a better understanding of how BoW works, let’s try to create a feature matrix for the two documents given below. 

Doc 1: quick, brown fox, jump, over, lazy, dog, back

Doc 2: now, time, all good, men, come, aid, their, party

Again, note that, here, clean tokenised text is being used. Usually, it will take a lot of effort to bring raw data to this state. To create a feature matrix, take all the unique words in these documents and make them columns and the documents will be rows.

![Document Feature Matrix](https://i.ibb.co/jM200H7/Document-Feature-Matrix.png)

The value in each cell with the frequency of the corresponding word appears in that document. For example, in the first row and the first column, 0 will be entered because the word “aid” does not appear in document 1. All other cells will be filled in a similar way. The filled matrix is shown below. 

![Document Feature Matrix Filled](https://i.ibb.co/QCZQzjP/Document-Feature-Matrix-Filled.jpg)

So, document 1 can be represented as \[0010110110010100\]. There will be similar vectors for all the documents. The length of count vectors for all the documents is the same because the number of columns for each row will be the same. It is not necessary that all count vectors will only have 0s and 1s. If there is a word that repeats more than once in a sentence, then the corresponding cell will harbor the actual frequency of the occurrence of the word. 

#### Feature Matrix

Qn: The shape of a feature matrix is represented as (m,n).  
With respect to the feature matrix, which of the following are correct? More than one option might be correct. 

- m is the number of documents in the dataset. 

- m is the number of unique words in the text corpus.

- n is the number of documents in the dataset.

- n is the number of unique words in the whole text corpus or dataset.

Ans: A & D. *Each document will take up a row in the feature matrix. So, the number of documents will decide the number of rows. Each unique word will be a column in the feature matrix.*

Now, it’s your turn to create a bag of words model. Consider these documents and create a bag-of-words model with the frequency approach on these documents. Please note that there is no need to remove the stop words in this case (just for this exercise). After you’re done creating the model, answer the questions that follow.

Document 1: “there was one place on my ankle that was itching”

Document 2: “but we did not scratch it”

Document 3: “and then my ear began to itch”

Document 4: “and next my back”

Question 1/2

Mandatory

#### Bag-of-words model

Qn: What is the size of the bag-of-words matrix?

- 4 rows and 15 columns

- 4 rows and 23 columns

- 4 rows and 22 columns

- 4 rows and 24 columns

Ans: B. *The number of rows in a bag-of-words model is equal to the number of documents. While the number of columns is equal to the number of unique words in the documents, i.e. the vocabulary size. There are four documents and 23 unique words.*

Qn: What is the value of the cell under the column “was” and in the row that corresponds to the first document?

- 0

- 1

- 2

- 3

Ans: C. *The word ‘was’ is present two times in the first document. So the value of the cell that corresponds to the first document and to the columns ‘was’ is 2.*

The BoW model implies that the word that repeats the most number of times is the most important word. Is this assumption correct? Can we make a better assumption? 

The TFIDF model is an improved technique that checks the relative importance of words in the documents. You will learn this technique in the next segment. You will also be provided the coding demonstrations of these models in the upcoming segments using the IMDB dataset.
