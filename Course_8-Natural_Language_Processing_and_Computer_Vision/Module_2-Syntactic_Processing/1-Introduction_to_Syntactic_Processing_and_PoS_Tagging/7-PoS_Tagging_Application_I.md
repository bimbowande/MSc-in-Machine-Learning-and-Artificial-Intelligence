# PoS Tagging Application - I

In the previous segment, you learnt about the underlying process of PoS tagging, i.e Hidden Markov Model(HMM). In this segment, you will go through a coding exercise to see how PoS tagging can be used to solve the problem.

Let’s start the segment with Sumit in the next video.

**VIDEO**

As Sumit mentioned in the video, we are not going to design and implement the rule-based tagger or a sequential tagger like HMM in the real world. However, it is good to have an intuitive understanding of how a PoS tagger can be built.

For the implementation of PoS tagging, you are going to use a Python library, i.e., spaCy. 

Please note that it is not important to deep dive into the working of the spaCy library. The working of spaCy is based on neural networks which is out of the scope of this course. spaCy works well in different applications of NLP such as PoS tagging, parsing and lexical processing steps. You just need to learn how to use this library for various applications. 

Now, let’s learn how one can use PoS tagging in applications like Heteronyms identification using the spaCy library.

Consider the following two sentences and pay attention to the pronunciation of word ‘**wind**’ while you read:

-   The doctor started to wind the bandage around my finger.
-   The strong wind knocked down the tree.

You can listen to these sentences in the [Google Translator](https://www.google.com/search?q=google+translate&rlz=1C1CHBF_enIN868IN868&oq=google+tra&aqs=chrome.0.0i131i433j0j69i57j0i131i433j0i433j69i60l3.5141j0j7&sourceid=chrome&ie=UTF-8) application. 

As you might have noticed, the pronunciation of ‘**wind**’ is different in both the sentences, though its spelling is the same. Such words are known as **Heteronyms**.

**Heteronyms** are words that have the same spelling but mean differently when pronounced differently.

But how do machines like Alexa and Google Translator detect these heteronyms? To understand this, let’s hear from Sumit in the next video.

You have been provided with notebook in the below link to code along with the video. We strongly recommend you to write the code along with the video to have a better understanding of the concepts.

Download [POS Tagging Demonstration](Heteronyms_POS.ipynb)

**VIDEO**

As you saw, Sumit took the following sentence:

‘She wished she could desert him in the desert.’

Google translator pronounces ‘desert’ differently based on its PoS tag. You can see that both the instances of the word ‘desert’ have different PoS tags, one is a verb and other one is a noun.

#### Heteronyms

Qn: Which of the following statements is true for heteronyms?  
 
- Words that are spelled differently but have the same meanings  

- Words that are spelled identically but have different meanings when pronounced differently

- Words that have the same PoS tags in a given sentence 

- Words that are spelled identically and pronounced differently but have the same PoS tag in a given sentence 

Ans: B. *This is the correct statement about Heteronyms.*

In the next segment, you will see how PoS tagging can be done using the spaCy library.