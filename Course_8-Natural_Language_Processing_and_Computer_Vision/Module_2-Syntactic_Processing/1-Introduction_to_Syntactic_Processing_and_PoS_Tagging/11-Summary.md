# Summary

In this session, you learnt about the fundamentals of syntactic processing and PoS tagging. Let’s summarise the entire session:

**Syntax and syntactic processing**: Syntax is a set of rules that govern the arrangement of words and phrases to form a meaningful and well-formed sentence. Syntactic processing is a subset of NLP that deals with the syntax of the language.

**Parts of speech**: Parts of speech (PoS) are the groups or classes of words that have similar grammatical properties and play similar roles in a sentence. They are defined based on their relation to the neighbouring words.

Assigning the correct PoS tags helps us better understand the intended meaning of a phrase or a sentence and is thus a crucial part of syntactic processing. 

  
A PoS tag can be classified in two classes – open class and closed class.  
The open class refers to tags that are evolving over time and where new words are being added for the PoS tag.

-   Open class
    -   Noun
    -   Verb
    -   Adjective
    -   Adverb
    -   Interjection
-   Closed class
    -   Prepositions
    -   Pronouns
    -   Conjunctions
    -   Articles
    -   Determiners
    -   Numerals

    You can take a look at the universal tag sets used by the SpaCy toolkit [here](https://universaldependencies.org/docs/u/pos/).

**Note**: [Spacy](https://spacy.io/) is an open-source library used for advanced natural language processing, (similar to NLTK) which you have used in lexical processing.

In this module, you are going to use the SpaCy library to perform syntactical analysis. You can also refer to the alphabetical list of 36 PoS tags used in the [Penn Treebank Project](https://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html) which is being used by the SpaCy library.

**PoS tagging:** A PoS tagger is a model/algorithm that automatically assigns a PoS tag to each word of a sentence.

![PoS Tagger](https://i.ibb.co/xHDp7np/Po-S-Tagger.png)

You can refer to the [universal PoS tag](https://universaldependencies.org/docs/u/pos/index.html) list to find tags corresponding to their parts of speech and also refer to the alphabetical list of PoS tags used in the [Penn Treebank Project](https://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html) which is being used by the SpaCy library.

You have learnt the following two types of PoS taggers:

-   **Rule-based tagger:** Here, you assign the most frequent PoS tags that appear in the training data to the test data set. However, sometimes, it does not give satisfactory results because it does not incorporate the **context** of the word.
-   **Sequential tagger (Hidden Markov Model):** Sequence labelling is the task of assigning respective PoS tags of words in a sentence using the PoS tag of the previous word in that sentence.

The Hidden Markov Model (HMM) can be used to perform sequence labelling, which means that it takes input of words in a sequence and assigns the PoS tags to each word based on the PoS tag of the previous word. 

Now, let’s take a look at the following points and try to understand why the Hidden Markov Model is called ‘hidden’:

1.  When you observe (read/listen) a sentence, you only observe the words in the sentence and not their PoS tags; thus, PoS tags are hidden.
2.  You must infer these hidden tags from your observations and that is why the Hidden Markov Model is called hidden.

      
Before learning about HMM, you need to understand the two most important types of matrices, i.e., emission and transition matrices.

-   Emission matrix: This matrix contains all words of the corpus as row labels. The PoS tag is a column header and the values are the conditional probability values. This matrix contains the conditional probability that if a particular PoS tag is present at a given place in the training data set, then the value will be the probability that it will be a given word? The emission matrix looks like as follows:

![Emission Matrix](https://i.ibb.co/K750y01/Emission-Matrix.png)

For example, whenever a noun appears in the training corpus, there is an 18% chance that it will be the word ‘judge’. Similarly, whenever a verb appears in the training corpus, there is an 84% chance that it will be the word ‘laugh’.

-   **Transition matrix:** This matrix contains PoS tags in the column and row headers. Let’s try to understand the conditional probability values that have been given in the following table.

Let’s take a look at the first row of the table. It represents that 0.26 is the probability of occurrence of a noun at the start of the sentence in the training data set. In the same way, 0.73 is the probability of occurrence of a verb at the start of the sentence in the training data set.

![Transition Matrix](https://i.ibb.co/q1WQHGf/Transition-Matrix.png)

Using these two matrices, you can calculate the probability of occurrence of PoS tags sequence in a given test sentence.

**Python implementation**: After completing the theoretical part, you used the Spacy library to identify the PoS tag in a given sentence and completed two use cases:

1.  Heteronyms use case
2.  Feature extraction case study

The important codes to correctly tag the tokens corresponding to their PoS tags is as follows:

```python
# Import SpaCy library
import spacy 

# Load pre-trained SpaCy model for performing basic 
model = spacy.load("en_core_web_sm")
```

 Where,  
**‘en’** stands for English language,  
**‘core’** stands for core NLP tasks such as lemmatization or PoS tagging,  
**‘web’** means a pre-built model of this library a trained from web source content such as blogs and social media comments, and  
**‘sm’** means faster and smaller pipelines but less accurate. As a complement to ‘sm’, you can use ‘trf’ for larger and slower pipelines but are more accurate.

```python
#Use the model to process the input sentence
tokens = model("We all are learning NLP with Sumit.")

# Print the tokens and their respective PoS tags.
for token in tokens:
    print(token.text, "--", token.pos_, "--", token.tag_)
```

Following is the link to download all the code notebook that has been used in this session:

Download [POS Tagging Case Study](POS_Tagging_Case_Study.zip)

Download [POS Tagging Demonstration](Heteronyms_POS.ipynb)
