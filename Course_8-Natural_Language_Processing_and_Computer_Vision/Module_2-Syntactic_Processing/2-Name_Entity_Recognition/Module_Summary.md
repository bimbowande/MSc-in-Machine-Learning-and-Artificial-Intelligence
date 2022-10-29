# Module Summary

In this module, you have learnt the following three areas of syntactic processing:

1.  What is syntax and syntactic processing
2.  PoS tagging:
3.  Name Entity Recognition (NER)

**Note**: [Spacy](https://spacy.io/) is an open-source library used for advanced natural language processing, (similar to NLTK) which you have used in lexical processing which you have used in the entire module.

-   **Syntax and syntactic processing**: Syntax is a set of rules that govern the arrangement of words and phrases to form a meaningful and well-formed sentence. Syntactic processing is a subset of NLP that deals with the syntax of the language.

-   **Parts of speech**: Parts of speech (PoS) are the groups or classes of words that have similar grammatical properties and play similar roles in a sentence. They are defined based on their relation to the neighbouring words. Assigning the correct PoS tags helps us better understand the intended meaning of a phrase or a sentence and is thus a crucial part of syntactic processing.

-   You have learnt the following two types of PoS taggers:
    
1.  **Rule-based tagger:** Here, you assign the most frequent PoS tags that appear in the training data to the test data set. However, sometimes, it does not give satisfactory results because it does not incorporate the **context** of the word.
    
2.  **Sequential tagger (Hidden Markov Model):** Sequence labelling is the task of assigning respective PoS tags of words in a sentence using the PoS tag of the previous word in that sentence. The Hidden Markov Model (HMM) can be used to perform sequence labelling, which means that it takes input of words in a sequence and assigns the PoS tags to each word based on the PoS tag of the previous word.
    

-   You can refer to the [universal PoS tag](https://universaldependencies.org/docs/u/pos/index.html) list to find tags corresponding to their parts of speech and also refer to the alphabetical list of PoS tags used in the [Penn Treebank Project](https://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html) which is being used by the SpaCy library.

-   **Name Entity Recognition:** NER is the technique to identify the entities in the corpus. It helps you easily identify the key elements in a text, such as a person’s names, location, brands, monetary values and dates. 

-   **NER IOB tags:** Instead of using nouns, verbs, etc., we will use the inside-outside-beginning (IOB) tags for entities that provide more relevant information about the text. Note that you will not always find the IOB format only in all applications. You may encounter some other labelling methods as well. So, the type of labelling method to be used depends on the scenario. Let's take a look at an example of a healthcare data set where the labelling contains 'D', 'T', and 'O', which stand for disease, treatment and others, respectively.

For reference, please download the lecture notes of this module from below:

Download [Summary Document](../Introduction_to_Syntactic_Processing_&_PoS_Tagging.pdf)

In this way, you have completed the module on syntactic processing.