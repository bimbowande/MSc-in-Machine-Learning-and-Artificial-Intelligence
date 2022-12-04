# Parts of Speech

Let’s start with the first level of syntactic analysis: PoS (Parts of Speech) tagging. To understand PoS tagging, you first need to understand what parts of speech are. 

Let’s consider a simple example given below.

*‘You are learning NLP at upGrad.’*

From your knowledge of the English language, you are aware that in this sentence, ‘**NLP**’ and ‘**upGrad**’ are nouns, the word ‘**learning**’ is a verb and ‘**You**’ is a pronoun. These are called the parts of speech tags of the respective words in the sentence. A word can be tagged as a noun, verb, adjective, adverb, preposition, etc., depending upon its role in the sentence. These tags are called the PoS tags. 

Assigning the correct tag, such as noun, verb and adjective, is one of the most fundamental tasks in syntactic analysis.

Suppose you ask your smart home device the following question. 

*‘Ok Google, where can I get the permit to work in Australia?’ *

The word '**permit**' can potentially have two PoS tags: noun or a verb. 

In the phrase *'I need a work permit'*, the correct tag of '**permit**' is 'noun'. 

On the other hand, in the phrase 'Please permit me to take the exam', the word '**permit**' is a 'verb'.

In the following video, let’s hear from Sumit about part-of-speech tags in detail.

**VIDEO**

Parts of speech (PoS) are the groups or classes of words that have similar grammatical properties and play similar roles in a sentence. They are defined based on how they relate to the neighbouring words.

Assigning the correct PoS tags helps us better understand the intended meaning of a phrase or a sentence and is thus a crucial part of syntactic processing.

Now, let’s understand the types of PoS tags available in the English language.

**VIDEO**

A PoS tag can be classified in two ways: **open class and closed class**.

Open class refers to tags that are evolving over time and where new words are being added for the PoS tag.

- **Open class**
  - Noun
  - Verb
  - Adjective
  - Adverb
  - Interjection

Some useful examples of open class PoS tags are as follows:

- Name of the person
- Words that can be added or taken from another language such as words taken from the Sanskrit language such as ‘Yoga’ or ‘Karma’ 
- Words that are nouns but can be used as verbs such as ‘Google’
- Words that are formed by a combination of two words such as football, full moon and washing machine

Closed class refers to tags that are fixed and do not change with time.

- **Closed class**
  - Prepositions
  - Pronouns
  - Conjunctions
  - Articles
  - Determiners
  - Numerals

Some examples of closed-class PoS tags are as follows:

- Articles: a, an, the 
- Pronouns: you and I 

You can take a look at the universal tagsets used by the spaCy toolkit [here](https://universaldependencies.org/docs/u/pos/).

**Note**: [spaCy](https://spacy.io/) is an open-source library used for advanced natural language processing, similar to NLTK, which you have used in lexical processing.

In this module on syntactic processing, you are going to use the spaCy library to perform syntactical analysis.

You do not need to remember all the PoS tags. You will pick up most of these tags as you work on the problems in the upcoming segments, but it is important to be aware of all the types of tags.

You can also refer to the alphabetical list of 36 part-of-speech tags used in the [Penn Treebank Project](https://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html), which is being used by the spaCy library.

#### Parts of Speech

Qn: Choose the correct option from those given below. You have been given the following sentence. *"India is the largest democracy in the world."* The PoS tags for the respective words of the sentence are given in the following table.

| India     | NNP |
| --------- | --- |
| is        | VBZ |
| the       | DT  |
| largest   | JJS |
| democracy | NN  |
| in        | IN  |
| the       | DT  |
| world     | NN  |

You can take a look at the universal tagsets used by the spaCy toolkit [here](https://universaldependencies.org/docs/u/pos/). What is the meaning of the tag ‘JJS’ in the table provided above? 

- JJS stands for determiners. Determiners are words that modify nouns or noun phrases and express the reference of the noun phrase in context.

- JJS stands for adjectives. Adjectives are words that typically modify nouns and specify their properties or attributes. 

- JJS stands for interjections. An interjection is a word that is used most often as an exclamation or part of an exclamation. 

Ans: B. *The word ‘largest’ modifies the word ‘democracy’, and it is working as an adjective. Hence, the tag of the word ‘largest’ is JJS, which stands for adjective.*

Qn: Which of the following parts of speech is categorised as open class parts of speech? (Note: More than one option may be correct.) Hint: You can take a look at the universal tagsets used by the SpaCy toolkit [here](https://universaldependencies.org/docs/u/pos/).

- Coordinating conjunction (CONJ)

- Proper noun (PROPN)

- Adverb (ADV)

- Interjection (INTJ)

Ans: B, C & D. 

- *A [proper noun](https://universaldependencies.org/docs/u/pos/https://universaldependencies.org/docs/u/pos/) is a noun (or nominal content word) that is the name (or part of the name) of a specific individual, place or object and is covered under open class.*

- *[Adverbs](https://universaldependencies.org/docs/u/pos/) are words that typically modify verbs for categories such as time, place, direction or manner. They may also modify adjectives and other adverbs.*

- *An [interjection](https://universaldependencies.org/docs/u/pos/) is a word that is used most often as an exclamation or part of an exclamation. It typically expresses an emotional reaction, is not syntactically related to other accompanying expressions and may include a combination of sounds not otherwise found in the language. It is covered under open class.*

#### Part of Speech

You can run the following lines of code to identify the PoS tags using SpaCy.

```python
import spacy
nlp = spacy.load("en_core_web_sm")
doc = nlp("upGrad is teaching Data Science courses to the working professionals.")
for token in doc:
    print(token.text, token.pos_, token.tag_)
```

Note: It is recommended to run the code in Google Colab. Can you write a descriptive answer about the meaning of the PoS tags ‘VBG’ and ‘NNP’ that are assigned to the words ‘teaching’ and ‘upGrad’, respectively?

Ans: *The word ‘teaching’ is assigned the PoS tag VBG, which is used to tag words that are verbs or gerunds or those with present participle tense. NNP stands for proper nouns that name specific people, places, things or ideas. ‘upGrad’ is a proper noun; hence, it is assigned an NNP tag.*

In the next segment, you will learn how PoS tagging is done for a sentence.