# PoS Tagging Application - II

In the previous segment, you were introduced to the problem of heteronyms which can be solved using PoS tagging to a large extent.

Now, let’s see how PoS tagging can be done in spaCy. 

**VIDEO**

Let’s try to understand each line of code one by one.

```python
model = spacy.load(“en_core_web_sm”)
```

-   ‘**en**’ stands for English language, which means you are working specifically on English language using the spaCy library.
-   ‘**core**’ stands for core NLP tasks such as lemmatization or PoS tagging, which means you are loading the pre-built models which can perform some of the core NLP-related tasks.
-   ‘**web**’ is the pre-built model of the spaCy library which you will use for NLP tasks that are trained from web source content such as blogs, social media and comments.
-   ‘**sm**’ means small models which are faster and use smaller pipelines but are comparatively less accurate. As a complement to ‘sm’, you can use ‘**lg**’ or ‘**md**’ for larger pipelines which will be more accurate than ‘sm’.

Visit this [link](https://spacy.io/models/en#en_core_web_sm) to know more about the spaCy package.

So, you have loaded the ‘en_core_web_sm’ model into the object ‘model’. Now, let’s apply the model on the input sentence, i.e., ‘She wished she could desert him in the desert’, using the following line of code.

```python
#Use the model to process the input sentence
tokens = model("She wished she could desert him in the desert.")
```

So, you get the words and its part of speech and tags in the variable ‘tokens’. Now, to print the tokens, part of speech and PoS tags, you need to apply a ‘for’ loop on this ‘tokens’ object as follows:

```python
# Print the tokens and their respective PoS tags.
for token in tokens:
    print(token.text, "--", token.pos_, "--", token.tag_)
```

 So, when you print ‘token.pos_’, it prints the part of speech and using ‘token.tag_’, it prints the PoS tags corresponding to each token in a given sentence.   
   
Please note that the ‘token.pos_’ gives you the part of speech which is defined in spaCy’s universal part of speech tags that you can get from this [link](https://universaldependencies.org/u/pos/). Moreover, to give the PoS tags using ‘token.tag_’, spaCy uses the PoS tags provided by the Penn treebank that you can get from this [link](https://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html).

When you get the PoS tags of each token of the sentence ‘She wished she could desert him in the desert’, then you will observe that the PoS tag of the word ‘desert’ is different in both of the instances. At one place, it is working as a verb and in another instance, it is working as a noun. 

  
**Word sense disambiguation (WSD)**: WSD is an open problem in computational linguistics concerned with **which sense of word** is used in a sentence. It is very difficult to fully solve the WSD problem. Google, however, has partially solved it.

Let’s try to listen to the pronunciation of the word ‘bass’ in the following sentence in Google Translator.

‘The bass swam around the bass drum on the ocean floor’.

You will see in the upcoming videos that both the occurrences of the word ‘bass’ have the same PoS tags, but the pronunciation should be different. Even Google Translator is not able to pronounce it differently.

However, as you have seen, the use of PoS tagging in heteronyms detection can be one of the prominent solutions to remove ambiguity in the sentence. 

Let’s take the example of  the following sentence:

‘She wished she could desert (verb) him in the desert (noun)’.

Here, the word ‘desert’ has two PoS tags based on its uses. At one place, it is working as a verb and at another place, it is working as a noun.

But what if the heteronyms have the same PoS tag but different pronunciation?

Let’s hear from Sumit to know more about it.

**VIDEO**

As discussed earlier, PoS tagging works pretty accurately to detect heteronyms but fails to distinguish between the words having the same spelling and the same PoS tags. Let’s consider the following example:

‘The bass swam around the bass drum on the ocean floor’.

When you implement the model on this sentence, you get the list of PoS tags of each token in the sentence. As you noticed that the word ‘bass’ is working as a noun at both of the places, but it should have different pronunciation at both the instances. 

So, the problem when the system is not able to identify the correct pronunciation of the words which have the same PoS tag but different meanings in different contexts can be considered under the WSD problem. 

Please note that this is just one of the dimensions of WSD. WSD is altogether a broader area to discover and it is an open problem in computational linguistics concerned with identifying which sense of a word is used in a sentence.

#### Word Sense Disambiguation

Qn: Which of the following problems can be considered under the word sense disambiguation (WSD) problem? Choose the **most appropriate** option from the following   
 
- When the system is not able to identify the correct PoS tag 

- When the system is not able to identify the correct pronunciation for the words which have the same PoS tag and have the same meaning

- When the system is not able to identify its correct pronunciation for the words which have the same PoS tag but different meanings in different contexts 

- None of the above 

Ans: C. *This is the correct explanation of WSD.*

#### Heteronyms

Qn: Which of the following words are considered as heteronyms? More than one option can be correct.  
Hint: Heteronyms are words that are spelled identically but have different meanings when pronounced differently.  

- Live

- Minute

- Wind

Ans: All of the above.

- *The word ‘live’ can act as a verb (to be alive, pronunciation is ‘laiv’) or it can act as an adjective (having life, pronunciation is ‘leev’).*

- *The word ‘minute’ can act as an adjective (which means small, the pronunciation is ‘mainute’) or it can act as a noun (a unit of time, the pronunciation is ‘minut’).* 

- *The word ‘wind’ can act as a noun (related to air movement, the pronunciation is ‘wind’) or it can act as a verb (related to tightening the spring, the pronunciation is ‘waind’).*

Qn: Which of the following heteronyms can be successfully detected by PoS tagging? More than one option can be correct.  
 
- Live

- Minute

- Wind

- Bass

Ans: A, B & C.

- *The word ‘live’ can have a VERB PoS tag and sometimes it may have an ADJECTIVE PoS tag. Consider the following two examples:*
	1.  *We can see live (adjective) animals.*
	2.  *I live (verb) in India.*

- *The word ‘minute’ can act as an adjective (which means small, the pronunciation is ‘mainute’) or it can act as a noun (a unit of time, the pronunciation is ‘minut’). Consider the following two examples:*
	1.  *There is a minute (adjective) difference in crimson red and red colours.*
	2.  *The minute (noun) hand of the clock is broken down.*

- *The word ‘wind’ can act as a noun (related to air movement, the pronunciation is ‘wind’) or it can act as a verb (related to tightening the spring, the pronunciation is ‘waind’). Consider the following two examples:*
	1.  *We have experienced a heavy wind (noun) in the afternoon.*
	2.  *Please wind (verb) up the rope on the terrace.*

#### PoS tagging

Qn: SpaCy is a Python library that can be used to perform many tasks such as identifying PoS tags of words in a corpus of documents. You need to code in Google Colab and find out the PoS tag of each token in the following  sentence:

*‘Apple is looking at buying UK-based start-up for $1 billion’.*

Qn: What is the PoS tag of ‘billion’ in the following sentence? Hint: You need to use ‘token.tag_‘ to get the correct answer.  
 
- NN

- JJ

- CD

- DT

Ans: C. *Please refer to the following code to get the PoS tags of each token of the sentence.*  

```python
#import library
import spacy
 
# built the model
model = spacy.load("en_core_web_sm")
 
#Use the model to process the input sentence
tokens = model("Apple is looking at buying UK-based start-up for $1 billion.")
 
# Print the tokens and their respective PoS tags.
for token in tokens:
    print(token.text, "--", token.pos_, "--", token.tag_)
```



#### PoS tagging

Qn: You have been given the following sentence.

*“UpGrad is teaching Data Science courses to the working professionals.”*

What will be the PoS tags of ‘teaching’ and ‘to’, respectively?

- DT, IN

- VBG, IN

- VBZ, NNS

- NNS, DT

Ans: B. *You can run the following lines of code to identify the PoS tags using SpaCy.*

```python
import spacy
nlp = spacy.load("en_core_web_sm")
doc = nlp("upGrad is teaching Data Science courses to the working professionals.")
for token in doc:
    print(token.text, token.pos_, token.tag_)
```

Qn: You have been given the following sentence.

*“UpGrad is teaching Data Science courses to the working professionals.”*

Which of the following is the correct PoS tag for the word ‘working’?  
 
- NNP

- VBZ

- VBG

- DT

Ans: C. *You can run the following lines of code to identify the PoS tags using SpaCy.*

```python
import spacy
nlp = spacy.load("en_core_web_sm")
doc = nlp("upGrad is teaching Data Science courses to the working professionals.")
for token in doc:
    print(token.text, token.pos_, token.tag_)
```

In the next segment, you will go through PoS tagging case study.