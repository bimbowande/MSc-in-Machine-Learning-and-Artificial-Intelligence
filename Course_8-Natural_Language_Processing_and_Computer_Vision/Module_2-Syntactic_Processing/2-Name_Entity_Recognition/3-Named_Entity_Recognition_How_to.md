# Named Entity Recognition How to?

In the previous segment, you learnt about the concept of named entities. In this segment, you will learn how the NER system works.

Before proceeding to the next video, answer the question given below.  

#### NER

Qn: Which of the following PoS tag do you think most named entities correspond to?

- Noun

- Adjective

- Verb

- Adverb

Ans: A. *Most of the named entities are names of people (Mother Teresa), places (California, New York), organisations (American Express, Deutsche Bank), etc.*

In the next video, we will discuss some approaches behind the design of the NER system.

**VIDEO**

#### NER

Qn: Which of the following statements are true regarding Named Entity Recognition (NER)? (Note: More than one option may be correct.)   
 
- NER is a technique that is used to extract entities from the text.

- Generally, nouns are the name entities that contain relevant information in any text.

- NER plays an important role in search engines.

- NER is an alternative to PoS tagging. However, PoS tagging provides more useful results than NER.

Ans: A, B & C. *NER enables you to easily identify the key elements in a text, such as a person’s name, locations, brands, monetary values, dates and so on.  These are generally nouns in a sentence. Search engines are based on the applications of NER.*

Some important points from the video above can be summarised as follows:

**Noun PoS tags:** Most entities are noun PoS tags. However, extracting noun PoS tags is not enough because in some cases, this technique provides ambiguous results. 

Let’s consider the following two sentences:

S1: ‘Java is an Island in Indonesia.’

S2: ‘Java is a programming language.’

PoS tagging only identifies ‘Java’ as a noun in both these sentences and fails to indicate that in the first case, ‘Java’ signifies a location and in the second case, it signifies a programming language.

A similar example can be ‘**Apple**’. PoS tagging fails to identify that ‘Apple’ could either be an organisation or a fruit.

Let’s take a look at a simple rule-based NER tagger.

**Simple rule-based NER tagger:** This is another approach to building an NER system. It involves defining simple rules such as identification of faculty entities by searching ‘PhD’ in the prefix of a person's name.

However, such rules are not complete by themselves because they only work on selected use cases. There will always be some ambiguity in such rules. 

Therefore, to overcome these two issues, Machine Learning techniques can be used in detecting named entities in text.

#### NER

Qn: Which of the following techniques can be used to find a named entity? (Note: More than one option may be correct.)  
 
- Extracting nouns from the text as a named entity

- Extract all the words starting with an uppercase letter as a named entity

- Using machine learning to find a named entity

- Creating rules for all the possible cases to find a named entity

Ans: A, C & D. *Most of the time, noun PoS tags help in finding named entities. ML algorithm can be used to train a model from a labelled data set and to predict the named entities present in the given text. A rule-based approach can find a named entity, but sometimes it can be difficult to create complete rules.*

In the next segment, you will learn about the IOB format and how NER can be looked at as a sequence labeling task, which is the basis of machine learning in named entity recognition tasks.
