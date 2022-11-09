# Syntax and Syntactic Processing

Let's start the session with understanding of the terms like syntactic processing and syntax. We all have learnt in our schools how a particular language is built based on the grammatical rules. 

Let’s take a look at the sentences given below.

‘Is EdTech upGrad company an.’

‘EdTech is an company upGrad.’

‘**upGrad is an EdTech company.**’

All of these sentences have the same set of words, but only the third one is syntactically or grammatically correct and comprehensible. 

One of the most important things that you need to understand here is that in lexical processing, all of the three sentences provided above are similar to analyse because all of them contain exactly the same tokens, and when you perform lexical processing steps such as stop words removal, stemming, lemmatization and TFIDF or countvectorizer creation, you get the same result for all of the three sentences. The basic lexical processing techniques would not be able to identify the difference between the three sentences. Therefore, more sophisticated syntactic processing techniques are required to understand the relationship between individual words in a sentence.

Now, before understanding what syntactic processing is, let’s first understand what syntax is and then take a look at some of the interesting examples that make use of syntactic processing. Let’s watch the next video for the same.

**VIDEO**

As discussed in this video, arrangement of words in a sentence plays a crucial role in better understanding the meaning of the sentence. These arrangements are governed by a set of rules that we refer to as ‘syntax’, and the process by which a machine understands the syntax is referred to as syntactic processing.

**Syntax**: A set of rules that govern the arrangement of words and phrases to form a meaningful and well-formed sentence

**Syntactic processing**: A subset of NLP that deals with the syntax of the language.

In the video provided above, you also looked at some examples such as chatbots, speech recognition systems and grammar checking software that use syntactic processing to analyse and understand the meaning of the text. 

#### Syntactic Processing

Qn: Consider the following two statements.  
I - Performing text cleaning steps such as stop words removal and tokenisation of documents and then performing feature extraction is part of syntactic processing.  
II - Creating parse trees for checking structural dependencies in a sentence is part of lexical processing.  
Which of these statements is correct?  
 
- Only I

- Only II

- Both I and II

- Neither I nor II

Ans: D. *Lexical analysis is the data pre-processing and feature extraction step. It involves analysis at word level. Syntactical analysis aims at finding structural relationships among the words of a sentence.*

Qn: Which of the following aspects lexical processing does not look at in the sentence? (Note: More than one option may be correct.)  
 
- Word order and meaning

- Incorporating stop words to analyse the grammatical structure of sentences

- Identifying the parts-of-speech words in a sentence

Ans: All of the above. 

- *Syntactic analysis aims to find how words are dependent on each other. Changing the word order will make it difficult to comprehend a sentence.*

- *Removing stop words can altogether change the meaning of a sentence; hence, syntactic processing analyses the grammatical structure of a sentence by incorporating stop words.*

- *Identifying the correct part of speech of a word is important.   
Example:  
'cuts and bruises on his face' (Here, 'cuts' is a noun.)  
'he cuts an apple' (Here, 'cuts' is a verb.)*

Qn: Which of the following is not a technique of lexical processing? (Note: More than one option may be correct.)  
 
- PoS tagging

- Stemming

- Stop words removal

- Name Entity Recognition

Ans: A & D. *PoS tagging identifies the linguistic role of each word in a sentence. Dependency parsing is one of the levels in syntactic processing, not lexical processing.*

Qn: Which of the following is a ‘must-have’ condition for a sentence to be syntactically correct?

- The sentence should be both meaningful and have the right syntax.

- The sentence should have the 'right grammar', i.e., nouns, adjectives, verbs - all parts of speech should be placed correctly in the sentence.

- Both of the above

- None of the above

Ans: B. *Syntactic analysis checks the grammatical structure of a sentence.*

Now, let’s consider the following example.

‘In Bangalore, it is better to have your own transport.’

‘We use carpooling to transport ourselves from home to office and back.’

What do you think about the word ‘**transport**’ in these two sentences? 

In the next segment, you will learn about parts of speech that show how different words function grammatically within a sentence and find out the meaning of the sentence.