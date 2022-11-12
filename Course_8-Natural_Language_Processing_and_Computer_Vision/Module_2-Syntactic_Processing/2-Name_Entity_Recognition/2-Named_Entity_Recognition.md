# Named Entity Recognition

Welcome to the segment on named entity recognition (NER). As you already know, with the help of PoS tagging and parsing techniques, you can determine the relationship between the words in a sentence. Now, the next step of understanding the text is Named Entity Recognition (NER).

Consider the following two representations of the given sentence:

‘John bought 300 shares of Apple in 2006’

**Representation1**:  John\[**NOUN**\] bought 300 shares  of Apple\[**NOUN**\] in 2006\[**NUMBER**\]

**Representation2**:  John\[**PERSON**\] bought 300 shares of Apple\[**ORGANISATION**\] in 2006\[**DATE**\]

As you can see, Representation1 has tagged the words ‘John’ and ‘Apple’ as nouns and ‘2006’ as a number. 

On the other hand, Representation 2 indicates the entity of the words like ‘John’ is tagged as ‘PERSON’ and ‘Apple’ as ‘ORGANISATION’, which provides information about the entities present in the sentence. This output can be achieved by using NER techniques. Essentially, with the help of NER, you will be able to find what the word is referring to like ‘John’ is a person and ‘Apple’ is an organisation.

Let’s hear from Sumit as he elaborates on the concept of NER.

**VIDEO**

As you learnt in the video above, NER techniques are applied in various fields such as search engine, chatbot and mainly in entity extraction in the long texts such as reviews, books, blogs and comments.

**Named Entity Recognition (NER)** enables you to easily identify the key elements in a piece of text, such as a person’s name, locations, brands, monetary values, dates and so on. 

Some example sentences with their named-entity recognition are as follows:

Note that GPE is short for the geopolitical entity, ORG is short for organisation and PER is short for a person.

S: ‘Why is Australia burning?’  
**NER**:   ‘Why is Australia\[GPE\] burning?’

  
S: ‘UK exits EU’  
**NER**:  ‘UK\[GPE\] exits EU\[ORG\]’  
   
S: ‘Joe Biden intends to create easier immigration systems to dismantle Trump's legacy’  
**NER**: ‘Joe Biden\[PER\] intends to create easier immigration systems to dismantle Trump's\[PER\] legacy’  
   
S: ‘First quarter GDP contracts by 23.9%’  
**NER**: ‘First quarter\[DATE\] GDP contracts by 23.9%\[PERCENT\]’

Let’s watch the next video to learn more about Named Entities.

**VIDEO**

Some commonly used entity types are as follows:

-    **PER**: Name of a person (John, James, Sachin Tendulkar)
-    **GPE**: Geopolitical entity (Europe, India, China)
-    **ORG**: Organisation (WHO, upGrad, Google)
-    **LOC**: Location (River, forest, country name)

In this course, we will be using the Spacy toolkit for NER tasks. Spacy contains predefined entity types and pretrained models, which makes our task easier.

#### NER

Identify all the named entities in the following sentence: *“US President Donald Trump has announced that he is heading to Singapore on June 12 to hold talks with North Korean leader Kim Jong-un.”* (Note: More than one option may be correct.)  
 
- US

- Donald Trump

- that

- Singapore

- June 12

- North Korea

Ans: A, B, D, E & F. *Country name, Person and Date are classified into named entity*

Qn: An entity is an object in the real world with an independent existence and can be differentiated from other objects

An entity can be \_\_\_\_\_.

-   An object with physical existence, for example, a lecturer, a student, a car, etc.
-   An object with conceptual existence, for example, a course, a job, a position, etc.

An entity type defines a collection of similar entities.

*'John drives a Mercedes.'*
  
Here, ‘John’ is the entity of entity type ‘Person’ and ‘Mercedes’ is the entity of entity type ‘Car’

Which of the following represents an **entity type**? (Note: More than one option may be correct.)  
 
- Location

- Date

- Taj Mahal

- Person

Ans: A, B & D. *‘Location’ is an entity type of entities such as ‘River’ and ‘Forest’. 'Date’ is an entity type of entities such as ‘18 Jan’ and ‘first quarter’. ‘Person’ is an entity type of entities such as ‘Smith’ and ‘Ram’.*

In the next segment, you will learn how the NER system works.