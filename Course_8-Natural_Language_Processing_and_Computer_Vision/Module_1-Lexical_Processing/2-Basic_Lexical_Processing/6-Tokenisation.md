# Tokenisation

An important question to ask while dealing with text data is: How do we extract features from messages so that they can be used to build an ML model? When you create an ML model, you need to feed in features related to each message that the machine learning algorithm can take in and build the model. But here, data is text. As you know, machine learning works on numeric data, not text. Recall the case studies that you have gone through so far; the text columns are usually categorical data. Categorical data is handled by assigning numbers to each category or creating dummy variables. 

For instance, if the education levels of individuals are recorded as matric pass, graduate, postgraduate, and so on, simple encoding, that is, 0 for matric pass, 1 for graduate and so on will convert the data to numerical form.

| Name  | Education_Level | Education_Level_neumerical |
| ----- | --------------- | -------------------------- |
| Rohan | Graduate        | 1                          |
| Ravi  | 10th pass       | 0                          |
| Raj   | Graduate        | 1                          |
| Amar  | Post graduate   | 2                          |

The above transfomration was possible because the data was categorical. However, since natural text is not categorical in nature, one cannot use these techniques to handle natural text. Unless the text is converted to a numerical form, machine learning models cannot learn from these models. How do you convert natural text to a numerical form? 

Consider the following sentences: 

1. Cat ate the fish. 

2. Raj ate his lunch. 

One way to convert these sentences to numeric data is to create a dictionary of unique words and call them features as shown in the table provided below. 

| Features   | cat     | ate     | the     | fish    | raj     | his     | lunch   |
| ---------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- |
| Sentence_1 | Present | Present | Present | Present | Absent  | Absent  | Absent  |
| Sentence_2 | Absent  | Present | Absent  | Absent  | Present | Present | Present |

Representing the ‘present’s and ‘absent’s in a numerical way to represent the sentence is a discussion for later. For now, we will focus on the process of separating individual words from sentences. This process is called tokenisation. 

**Tokenisation** is a technique that is used to split text into smaller elements. These elements can be characters, words, sentences or even paragraphs, depending on the application that you are working on. In the next video, Mahesh will talk about tokenisation and the types of tokens that one can create.

Play Video

3221820

In this video, you learnt that there are various types of tokenisation techniques. You can split a text corpus into words, sentences or even paragraphs. 

The guiding principle for the choice of tokens depends on the ability to extract maximum information from the text. The smaller the token, the more information you can extract, but this will also increase the computational cost. On the other hand, larger tokens will be easy to compute, but information might be lost. 

The library that will be used in the Zomato case study is the NLTK (Natural Language Toolkit) library. In NLTK, you have different types of tokenisers that you can use in a variety of applications. The most popular tokenisers are as follows:

1. Word tokeniser, which splits text into different words

2. Sentence tokeniser, which splits text in different sentences

3. Tweet tokeniser, which handles emojis and hashtags that you see in social media texts

4. Regex tokeniser, which lets you build your own custom tokeniser using regex patterns of your choice

#### Tokenisation

Qn: Consider a sample telegram message as shown below. 

DEAREST JOHN AND MARTHA.  
ESLEY CRAWLEY TO WED JOSEPH JONES AT THE GRANDE HOTEL IN LONDON UNITED KINGDOM THE NINTH OF MARCH 1927. THE EXCITEMENT AND HOW! WE HOPE YOU WILL JOIN US TO CELEBRATE. FORMAL INVITATION FORTHCOMING.   
 
Based on which punctuation marks would you split the text to tokenise the corpus into sentences?

- Only the period (.)

- Commonly used punctuation marks such as the period, exclamation mark and question mark

Ans: B. *You can use a regex pattern to match these punctuation marks and separate the sentences.*

### Tokenisation

#### Description
Write a piece of code that breaks a given sentence into words and store them in a list. Then print the length of the list. Use the NLTK tokeniser to tokenise words.

Sample input:

"I love pasta"

Expected output:

3

#### Solution
```python
from nltk.tokenize import word_tokenize
import ast, sys
sentence = sys.stdin.read()

# tokenise sentence into words
words = word_tokenize(sentence) # write your code here

# print length - don't change the following piece of code
print(len(words))
```

#### Description
Write a piece of code that breaks a given sentence into words and stores them in a list. Then remove the stop words from this list and then print the length of the list. Again, use the NLTK tokeniser to do this.  
  
Sample input:   
“Education is the most powerful weapon that you can use to change the world”   
  
Expected output:   
6

#### Solution
```python
from nltk.tokenize import word_tokenize
from nltk.corpus import stopwords
import ast, sys
sentence = sys.stdin.read()

# change sentence to lowercase
sentence = sentence.lower() # write code here

# tokenise sentence into words
words = word_tokenize(sentence) # write code here

# extract nltk stop word list
stopwords = set(stopwords.words('english')) # write code here

# remove stop words
no_stops = [w for w in words if not w in stopwords] # write code here

# print length - don't change the following piece of code
print(len(no_stops))
```

You will learn about the use of these tokenisers in the Zomato case study. For now, let’s continue learning about text preprocessing. In the next segment, you will learn about stemming and lemmatisation.
