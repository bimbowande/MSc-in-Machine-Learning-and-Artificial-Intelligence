# Input Data for CBOW

In the previous segment, you recalled forward pass in neural networks. 

The two different approaches for Word2Vec are Skip-gram model and Continuous Bag Of Words (CBOW) model. In the next video, we will discuss the difference between them.

**VIDEO**

The Skip-gram model predicts words within a certain range before and after the input word.

![Skip-Gram Example](https://i.ibb.co/CbW9zNf/Skip-Gram-Example.png)

Continuous Bag of Words predicts the middle word based on the surrounding words.

![CBOW Example](https://i.ibb.co/N9LZNmn/CBOW-Example.png)

Let us test our understanding:

#### Model

Qn: Read the following sentence. *"A bird in \_\_\_\_\_ is worth two in the bush."*

If you have to predict the word to be filled in the blank, which of the following models would you use?  
 

- Skip-gram

- Continuous Bag of Words (CBOW)

- Both

- None

Ans: B. *Continuous Bag of Words predicts the middle word based on the surrounding words.*

Now, you know that two models can create word embeddings. You will gain a detailed understanding of the CBOW model by assessing the training data, understanding the architecture of neural networks and learning how to extract word embeddings from weight matrices. Finally, you will take a look at the case and understand how Skip-gram differs from CBOW.

In the next video, you will learn how to make the training data for the CBOW model.

**VIDEO**

We assumed that we have only one sentence in our corpus, which is ‘My experience with upGrad has been wonderful’. The vocabulary size is the number of unique words in the corpus, which is 7 in our case. 

The context size determines the number of words that are present before and after a given word would be included as the context words of the given word. This is a parameter that we need to decide before creating training data. For the sake of simplicity, we have considered the context size to be 1. 

The training data for the CBOW model for our sentence with a context size of 1 looks like this.

![l](https://images.upgrad.com/80e88cdf-cca3-4332-b5eb-ac188fa4efb2-Screenshot%202021-06-03%20at%209.23.16%20AM.png)

l

We can represent our training data as follows.

![b](https://images.upgrad.com/31ff03c7-60fb-47a7-b652-b5d97aa8678c-Screenshot%202021-06-02%20at%203.03.31%20PM.png)

b

Based on your understanding of the topic so far, please attempt the following question.

#### Training Sample

For the CBOW model, create the training samples for the sentence  
‘The quick brown fox jumps over lazy dog’  for a context size of 1.  
 

- ([quick],The), ([The,brown],quick), ([quick,fox],brown),([brown,jumps],fox) ([fox,over],jumps), ([jumps,lazy],over),([over,dog],lazy),([lazy],dog)

- ([The,brown],quick), ([quick,fox],brown),([brown,jumps],fox) ([fox,over],jumps), ([jumps,lazy],over),([over,dog],lazy),([lazy],dog)

- ([quick],The), ([The,brown],quick), ([quick,fox],brown),([brown,jumps],fox) ([fox,over],jumps), ([jumps,lazy],over),([over,dog],lazy)

- None of the above

Ans: A.

We have created the training samples that need to be fed into a neural network, but neural networks do not take words as inputs. We need to encode these words into a numeric input. In the next video, Jaidev will demonstrate it.

**VIDEO**

One Hot Encoding is used to convert words into a numeric format. The words can be arranged in alphabetical order or based on frequency or any other heuristic. One hot encoding of the words in our example can be represented as follows.

![l](https://images.upgrad.com/367da7cb-888a-41af-b496-9814bc5f48ee-Screenshot%202021-06-02%20at%203.05.40%20PM.png)


From this table, the one hot encoding of ‘experience’ is as follows. The position of the ‘1’ is in the second position as the mapping has been done according to the table above.

| 0 | 1 | 0 | 0 | 0 | 0 | 0 |
|---|---|---|---|---|---|---|

Based on your understanding of the topic so far, please attempt the following question:

#### One Hot Encoding

Qn: For the CBOW model, on which of the following does the length of the one hot encoded vector depend?

- Context size

- Vocabulary size 

- The number of words in the sentence

Ans: B. *The length of OHE vector depends on the vocabulary size.*

You learnt how to create training data for a given corpus and for a decided context size. In any neural network, you need input data that you have created using the methods shown above. In the next segment, you will understand the architecture of the neural network.