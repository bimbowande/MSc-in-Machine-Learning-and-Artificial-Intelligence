# Intuition of Word2Vec Model

In 1957, the English linguist John Firth said, “You shall know a word by the company it keeps”.

We, as humans, can decipher the meaning of an unknown word simply by taking a look at its surrounding words.

Previously, you learnt about the different approaches to convert a word into vectors such as Bag of Words and Tfidf. Let’s take a look at a different approach to predict word vectors based on machine learning/neural networks, which is also known as the Word2Vec model.

**VIDEO**

Now that you have understood what a machine learning model is trying to achieve, let’s take a step-by-step look at the process.

**VIDEO**

In this video, you gained an understanding of a brief intuition of the Word2Vec model.

The steps involved in this are as follows:

**Step 1**: Make a neural network that predicts a word, given the nearby words as shown below.

![Word2Vec Model Step 1](https://i.ibb.co/n02yTg0/Word2-Vec-Model-Step1.png)  

**Step 2**: Wait for it to predict well enough. Train the neural network such that the probability of the glitters is the highest in the output layer, as the network is trying to predict glitters as shown below.

![Word2Vec Model Step 2](https://i.ibb.co/vqgWjtJ/Word2-Vec-Model-Step2.png)

**Step 3**: Find out what it has learnt

Surprisingly, the output of the neural network is not what we are interested in, although this is what is generally extracted from neural networks. Instead, we are interested in the weight matrices which contain the semantic information, known as word embeddings.

In the next segment, you will learn how to extract the word vectors from the weight matrices. Do keep in mind that the word vectors are not found in the output of neural networks but in the weight matrices!

To summarise, if a machine is able to predict the words from its surroundings, it has captured the meaning of the word. In the next segments, you will learn about two different algorithms of the Word2Vec model, which are Skipgram model and the Continuous Bag Of Words (CBOW) model.

_Note: In the above diagrams, the representation of input word vectors that are fed into neural networks are not exact. It is shown for understanding purpose. We will understand the exact representation of input vector of neural networks in the upcoming segments._

Before taking a deep dive into the concepts, let’s recall how forward pass works in the neural network.