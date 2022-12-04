# Term Frequency Inverse Document Frequency (TFIDF) Model

In the previous segment, you learnt a way to convert text into features by using the BoW model. The TFIDF model is another way to convert text into features. The upcoming video explains the working of TFIDF. 

**VIDEO**

The TFIDF representation, also called the TFIDF model, takes into account the importance of each word in the given documents. In the BoW model, each word is assumed to be equally important in the corpus of documents, which is, of course, not correct.

  
The formula to calculate the TFIDF weight of a term in a document is as follows:

$$\large{tf_{t,~d}=\dfrac{frequency~of~term~'t'~in~document~'d'}{total~terms~in~document~'d'}}$$

$$\large{idf_t=log\dfrac{total~number~of~documents}{total~documents~that~have~the~term~'t'}}$$

The log in the above formula is with base 10. Now, the TFIDF score for any term in a document is just the product of the two variables determined using the above-mentioned formulas:

$$\large{tf−idf=tf_{t,~d}∗idf_t}$$

Higher weights are assigned to terms that occur frequently in a document and are rare among all documents. On the other hand, a low score is assigned to terms that are common across all documents.
  
Now, attempt the following quiz. Questions 1-3 are based on the following set of documents:  
**Document1**: ‘Vapour, Bangalore, has a really great terrace seating and an awesome view of the Bangalore skyline.’  
**Document2**: ‘The beer at Vapour, Bangalore, was amazing. My favourites are the wheat beer and the ale beer.’  
**Document3**: ‘Vapour, Bangalore, has the best view in Bangalore.’

#### TF-IDF model

Qn: What is the tf-idf score of the term ‘Bangalore’ in document one? (Remove stop words and punctuations before calculating the tf-idf score).

Ans: *0. The word 'Bangalore' occurs in all the documents and hence we will have the $tf_{t,~d}=\dfrac{2}{10}=0.2$ and $idf_t=log\left(\dfrac{3}{3}\right)=log(1)=0$. Hence $tf-idf=0.2*0=0$*

Qn: What’s the tf-idf score of the term ‘beer’ in document two?  (Remove stop words and punctuations before calculating the tf-idf score). Round your answer to three digits after the decimal.

Ans: *0.159. $tf-idf=\dfrac{3}{9}*log\left(\dfrac{3}{1}\right)=0.1590404182$*

Qn: Which of the following statement regarding the tf-idf score of the terms ‘Vapour’ and ‘Bangalore’ in the second document is true?

- Tf-idf score of ‘Vapour’ and ‘Bangalore’ in the second document is equal

- Tf-idf score of ‘Vapour’ in the second document is greater than the tf-idf score of ‘Bangalore’ in the second document

- Tf-idf score of ‘Vapour’ in the second document is less than the tf-idf score of ‘Bangalore’ in the second document

Ans: A. *The tf of ‘vapour’ and ‘bangalore’ in the second document is equal. The idf of both of these terms is also equal since they have an idf score of zero. Hence, their tf-idf score is also equal.*

Qn: In this particular example, the TF-IDF value of the token 'Bangalore' is different and non zero for all three documents.  
 
- True

- False

Ans: B. *The IDF value of Bangalore is zero, hence the TF-IDF value is zero for all the occurrences of Bangalore*

Qn: “For a given set of documents, the idf score of a term is same across all the documents.”  
The above statement is true or false?  

- True

- False

Ans: A. *The idf of a term is the log of the total number of documents divided by the total number of documents where the term appears. Now, the total number of documents where the term is present is a constant and so is the total number of documents. Hence, idf is also a constant for a given word.*

Note that TFIDF is implemented in different ways in different languages and packages. While calculating the TF score representation, some people use only the frequency of the term, that is, they do not divide the frequency of the term by the total number of terms. While calculating the IDF score, some people use natural log instead of log with base 10. Therefore, you may observe a different score of the same terms in the same set of documents. However, the end goal remains the same - assign a weight to a word according to its importance. 

The TFIDF model intuitively assigns higher value to words that are rare. The term frequency is higher for words that are frequent in a document. Whereas, the inverse document frequency is high for terms that are rare. As a result, only the more significant and rare words get assigned high numerical values. 

Consider the example shown below. 

**Document1**: "Harry Potter is a great movie. It is based on Harry's life".

**Document2:** "The success of a song depends on the music".

**Dcoument3**: "THere is a new movie releasing this week. The movie is fun to watch".

![TFIDF Feature Matrix](https://i.ibb.co/TcQH6G2/TFIDF-Feature-Mtrix.png)

Even though the word ‘movie’ occurs very frequently in the text corpus, it has low TFIDF values. Take a look at the words that have high TFIDF values. For instance, in the second document, the word ‘depend’ has a high value. This implies that the word ‘depend’ is critical in case of the second document. Similarly, the word ‘new’ is critical in case of the third document.

Major difference between BoW and TFIDF is the fact that they assign a high value to words based on different criteria. BoW gives importance to words that are more frequently present, whereas TFIDF gives importance to words that are more rare and significant. 

With this, you have reached the end of feature extraction. In the next video, let’s hear Mahesh quickly summarise the text cleaning and feature extractions phases. 

In the next segment, you will learn how to apply all the techniques that you have learnt to a real-life dataset and build a sentiment predicting model.
