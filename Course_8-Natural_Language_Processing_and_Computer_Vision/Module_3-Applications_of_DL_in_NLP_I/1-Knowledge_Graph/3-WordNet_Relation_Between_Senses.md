# WordNet - Relation Between Senses

In the previous sessions, you learnt about different types of knowledge graphs.

In this session, you will gain a detailed understanding of the WordNet knowledge graph. 

WordNet is a part of NLTK, and you will use it later in this module to identify the 'correct' sense of a word (i.e., for word sense disambiguation).

WordNet® is a large lexical database of English words developed by Princeton University. It can be accessed [here](http://wordnet.princeton.edu/).

Let’s see Jaidev explore the Wordnet database.

**VIDEO**

Let us understand what we learnt in the above video.

The diagram below is a screenshot from the WordNet website:

![WordNet Example](https://i.ibb.co/jhbWM0d/Word-Net-Example.png)

In the diagram given above, each word sense of the word bank is grouped into its nouns and verbs. A set of all these senses is called a synset.

Each sense of the word has a gloss or meaning of the word and an example as in the dictionary.

For example, the first verb sense of the word has a gloss or a meaning as ‘tip literally’ and the example sentence as ‘the pilot had to bank the aircraft’.

Similarly, each word sense contains a gloss and an example sentence.

  
If meanings are available in the dictionary as well, what makes WordNet unique?

Each of these senses of the words is related to other senses through some relations. In the next video, let’s take a look at the relations in WordNet. 

**VIDEO**

The types of relationship between different words can be grouped as follows:

1.  Synonym: A relation between two similar concepts
    

Example: Large is a synonym of big.

2.  Antonym: A relation between two opposite concepts
    

Example: Large is an antonym of big.

3.  Hypernym: A relation between a concept and its superordinate
    

 A superordinate is all-encompassing.

Example: Fruits is the hypernym of mango.

4.  Hyponym: A relation between a concept and its subordinate
    

Example: Apple is the hyponym of fruits.

You can refer to the diagram given below to understand hyponyms and hypernyms. Any word that is connected with its hypernyms has an ‘is a’ relationship

![Hyponyms and Hypernyms](https://i.ibb.co/hs7GJJV/Hyponyms-and-Hypernyms.png)

1.  Holonym: A relation between a whole and its parts
    

Example: Face is the holonym of eyes.

2.  Meronym: A relation between a part and its whole.
    

Example: Eyes is the meronym of human body

You can refer to the diagram given below to gain an understanding of holonyms and meronyms. Any word is connected with its holonym by a ‘has part’ relationship. 

![Holonyms and Meronyms](https://i.ibb.co/Ykbt0Bk/Holonyms-and-Meronyms.png)

Based on your learnings so far, attempt the following questions.

#### Relations

Qn: Fill in the blank in the following sentence. *"Car is a \_\_\_\_\_ of brakes"*  
 
- Meronym 

- Hypernym

- Holonym

- Hyponym

Ans: C. *Term ‘A’ is said to be a holonym of a term ‘B’  if A has several parts and B is one of them.*

Qn: Fill in the blank in the following sentence. *"Rose is a \_\_\_\_\_ of flower."*  
 
- Meronym 

- Hypernym

- Holonym

- Hyponym

Ans: D. *A hyponym is a relation between a concept and its subordinate.*

Qn: Fill in the blank in the following sentence.: *"Country is a \_\_\_\_\_ of India"*  
 
- Meronym

- Hypernym 

- Holonym 

- Hyponym

Ans: B. *A hypernym is a relation between a concept and its superordinate.*

Apart from these, can you think of some other examples of hypernyms, hyponyms, meronyms, holonyms, synonyms and antonyms?

To summarise, Wordnet contains word senses for each word, and these senses are related through different relations.

In the next segment, you will understand the different functions of WordNet using NLTK.