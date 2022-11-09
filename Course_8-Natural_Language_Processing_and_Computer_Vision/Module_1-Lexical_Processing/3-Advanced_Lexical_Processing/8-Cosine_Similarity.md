# Cosine Similarity

By now, you have covered the sentiment analysis case study. So, you understand the fundamentals of model building on text data. Now, let’s learn a way to mathematically find similar documents. 

The cosine similarity model is used to find similar documents from a corpus. In the upcoming video, Mahesh will explain the objective of cosine similarity. 

**VIDEO**

As you saw in this video, cosine similarity is a metric that measures the distance/similarity between two documents. 

Now, let’s learn how to calculate cosine similarity. 

**VIDEO**

In this video, you saw an example depicting the calculation of cosine similarity. Let’s summarise this example. 

Consider the following set of documents. 

_**D1**: ‘Interstellar is a science based movie. It uses physics concepts’_

_**D2**: ‘Gravitation is a physics concept. It is one of the important fields in science and there is a movie Gravity based on this’_

_**D3**: ‘Fast and Furious is a thriller movie. It is based on cars and adventures’_

The first step is to find the TFIDF matrix for these sentences. 

![TFIDF Matrix Example2](https://i.ibb.co/FbJTNfT/TFIDF-Matrix-Example2.png)

Now, you use the TFIDF values of words that are common in both the documents to find the cosine similarity score. The formula to determine the cosine similarity is given below. 

Cosine Similarity:  
$$\large{cos\theta=\dfrac{X*Y}{|X||Y|}}$$

Here, X and Y are vectors of the TFIDF values, corresponding to common words in the two documents. Then, this formula is used to find similarity between D1 and D2. 

1. The common values in D1 and D2 are highlighted.

![Common Values D1 & D2 Highlighted](https://i.ibb.co/bWL1WVy/Common-Values-D1-D2-Highlighted.png)

2. Apply the formula to the four highlighted sets of TFIDF values. 
$$\text{Cosine Similarity}:=\dfrac{(0.40×0.32)+(0.31×0.25)+(0.40×0.42)+(0.53×0.42)}{\sqrt{0.40^2+0.31^2+0.40^2+0.53^2}*\sqrt{0.32^2+0.25^2+0.42^2+0.42^2}}$$
3. So, the cosine similarity between D1 and D2 = 0.992.

So, the cosine similarity between D1 and D2 is 0.992. What does this mean? Are the documents similar or not similar? Mahesh will explain the interpretation of the values in the upcoming video. 

**VIDEO**

#### Cosine Similarity

Qn: Consider 2 documents and their respective vectors X and Y:

X = [3,8,7,5,2,9] (vector from term document matrix for document d1)   
Y= [10,8,6,6,4,5] (vector from term document matrix for document d2)

What will be the value of cosine distance?  
 
- 0.86

- 0.14

- 0.36

- 0.64

Ans: B. *To find cosine similarity you can use the following formula* 

$cos\theta=\dfrac{X*Y}{|X||Y|}$

Given,

X = [3,8,7,5,2,9]

y = [10,8,6,6,4,5]

$$\text{Cosine similarity}=\dfrac{(3×10)+(8×8)+(7×6)+(5×6)+(2×4)+(9×5)}{\sqrt{3^2+8^2+7^2+5^2+22+9^2}*\sqrt{3^2+8^2+7^2+5^2+2^2+9^2}}$$
$$=\dfrac{30+64+42+30+8+45}{\sqrt{9+64+49+25+4+81}*\sqrt{100+64+36+36+16+25}}$$
$$=\dfrac{219}{15.23*16.64}=0.864$$

Therefore cosine distance $=1-0.86=0.14$

You already know that the value of cosine ratio varies from 0 to 1.  

If the value of cosine similarity is closer to 0, the vectors of these two documents are approximately at 90 degrees to each other and they are not at all similar to each other. 

If the value of cos similarity is closer to 1, the vectors of these two documents are parallel to each other and the documents are highly similar. 

In this case, documents D1 and D2 are very similar to each other, as the cosine similarity value is 0.992, which is close to 1. 

Conversely, the cosine distance (1-cosine similarity) is quite high between D1 and D2. Contrary to cosine similarity, which signifies how similar the documents are, cosine distance signifies how different a pair of documents are. 

Use the TFIDF table below to answer the test. 

![TFIDF Matrix Qn](https://i.ibb.co/3Yb8bTg/TFIDF-Matrix-Qn.png)

#### Cosine Similarity

Qn: Find the cosine distance between D2 and D3. 

- 0.10

- 0.158

- 0.91

- 0.847

Ans: D. *Only one token is common in D2 and D3. So, the cosine distance can be found in the following way:*

$\text{Cosine Similarity}=\dfrac{0.25+0.43}{0.25×0.43}=0.153$

$\text{Cosine Distance}=1-0.153=0.847$

Qn: What would be the cosine similarity in two documents that have no tokens in common? 

- 0

- 1

Ans: A. *Since the two documents do not have any common elements, the cosine similarity will be zero. Cosine similarity of 1 implies a strong similarity. Since the two documents do not have any common elements, the cosine similarity will be zero.*

In the next segment, let’s take a look at a code demonstration of cosine similarity.