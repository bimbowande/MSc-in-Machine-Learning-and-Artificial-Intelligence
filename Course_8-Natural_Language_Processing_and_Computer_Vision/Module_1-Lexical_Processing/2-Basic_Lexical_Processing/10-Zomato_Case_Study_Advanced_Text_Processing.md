# Zomato Case Study: Advanced Text Processing

In the last segment, Dr Balan demonstrated various techniques to clean text. Before moving any further, let’s apply all the cleaning steps to the Zomato data set. 

**VIDEO**

As you saw, a custom function that has all the cleaning techniques together was used to clean the text. Creating functions of this sort is a good practice because the next time you want to perform the same tasks, you can simply use the same function. It gives a lot of reusability. 

  
The next step in preprocessing is removing the stop words. Let’s first take a look at the demonstration. 

**VIDEO**

The NLTK library has a predefined set of stop words; it can be directly used to build a function that can remove stop words. The following is the pseudo code of removing the stop words from reviews. 

1.  Separate the reviews into words.  
    We use the toktok tokeniser from the NLTK library to split the review sentences into a list of words. 
    
2.  From the list of words, check each word to see if it belongs to the stop words list from NLTK. 
    
3.  If the word is present in the stop words list, then do nothing; if not, add it to a new list. 
    
4.  Combine the words from the new list to convert the list of words into a sentence. 
    

Now, let’s compare the pseudo code to the actual code; the code will be much clearer to understand now.

```python
from nltk.corpus import stopwords
from nltk.tokenize.toktok import ToktokTokenizer

#Tokenization of text
tokenizer=ToktokTokenizer() 

#Setting English stopwords
stopword_list=nltk.corpus.stopwords.words('english')

#Removing standard english stop words like prepositions, adverbs
from nltk.tokenize import word_tokenize,sent_tokenize

stop=set(stopwords.words('english'))
print(stop)
```

First, import the necessary tools and initialise them. Download the stop words list and print the list of stop words. 

```python
#Removing the stopwords
def remove_stopwords(text, is_lower_case=False):
    # tokenize the test into a list of words. 
    tokens = tokenizer.tokenize(text)
    # remove the empty spaces from right and left of the tokens. 
    tokens = [token.strip() for token in tokens]
    # The second optional argument comes in the picture here. 
    # If the option is true then the function will assume all the letters are in lower case
    if is_lower_case:
        # A new list is created with the words which are not in the  list of stop words. 
        filtered_tokens = [token for token in tokens if token not in stopword_list]
    else:
        # If the second argument is false then all token will also be converted to lowercase
        filtered_tokens = [token for token in tokens if token.lower() not in stopword_list]
    # join the text back together 
    filtered_text = ' '.join(filtered_tokens)    
    # return the text without stop words. 
    return filtered_text

#Apply function on review column
zomato['Review']=zomato['Review'].apply(remove_stopwords)
```

Let’s focus on the function to remove stop words. It is the same as the pseudo-code written earlier, except this function also checks for capitals. The function first tokenises the text into words, following which each word is compared with a list of stop words that we downloaded from the NLTK corpus. If the word is present, then we do nothing; if not, we add it to a new list. Finally, the elements of the list are combined to create the complete review. The if statement that is responsible for removing stop words is inside the list comprehension. The other if statement is responsible for converting all tokens to lower case. 

  
 After this exercise, you will be left with only significant words in each review. 

## Stemming and lemmatization 

In the demonstration given below, Mahesh will perform both stemming and lemmatisation on the review data. 

**VIDEO**

As you saw in the demonstration, the processes of stemming and lemmatisation are similar, but lemmatisation has a few more steps. 

  
When you use stemming, you split the corpus into tokens and pass each token to the stemmer. The stemmer then decides the necessary modifications to the token and returns the stem of the token. Most of the time, the stems are not complete English words. This method serves its purpose of reducing unique words by converting all words to their stems. The stemming code used in the demonstration is given below.   
 

```python
from nltk.stem import WordNetLemmatizer,SnowballStemmer
from nltk.stem.porter import PorterStemmer
nltk.download('wordnet')

def simple_stemmer(text):
    ps=SnowballStemmer(language='english')
    return ' '.join([ps.stem(word) for word in tokenizer.tokenize(text)])
```

In this demonstration, the snowball stemmer has been used. The process of stemming is simple: You import the stemmer, pass each token, one by one, to the stemmer. Note that list comprehension has been used to make the code elegant and compact. The code after the return keyword serves three functions: It tokenises the text given to it, passes each token to the stemmer and finally joins all the stems back together. 

  
On the other hand, in lemmatisation, first, you pass the complete text to the parts of speech tagger, post which each word will have a part of speech attached with it. Now you can tokenise the text and lemmatise it. For each word to be converted to its lemma, you need the word itself and its POS tag. Although the results obtained using a lemmatiser are more accurate, it uses a significantly larger amount of computation resources. Let’s understand the code used for lemmatisation. 

```python
# Import all the necessary tools and packages. 
# pos_tag is a module used to tag the part of speech. 
from nltk.tag import pos_tag
from nltk.tokenize import word_tokenize
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
#Lemmatizer example
def lemmatize_all(sentence):
    wnl = WordNetLemmatizer()
    # create a loop which processes each token at a time. 
    # During each loop one word is first tagged by pos_tag 
    # The same tag is converted to a form which the lemmatizer understands.
    for word, tag in pos_tag(word_tokenize(sentence)):
        if tag.startswith("NN"):
            yield wnl.lemmatize(word, pos='n')
        elif tag.startswith('VB'):
            yield wnl.lemmatize(word, pos='v')
        elif tag.startswith('JJ'):
            yield wnl.lemmatize(word, pos='a')
        # if none of the tags match, the word is returened as is. 
        else:
            yield word
            
def lemmatize_text(text):
    return ' '.join(lemmatize_all(text))
```

This piece of code is a bit complex to understand. First, all the necessary functions are imported. Again, let's focus on the lemmatize_all function. The input to the function is a tokenised sentence with each token (word in this case) tagged with its relevant part of speech, such as noun, verb, adverb or preposition. This tagging is done by another module in the NLTK library, the pos_tag. Then, the nested if statement makes sure that the tags are in such a format that the WordNetLemmatizer() function can understand them. If the part of speech tag does not match any of the wordnet specified parts of speech, then the word is returned as is. 

Notice the extra processing that is needed for lemmatization. The complete POS tagging exercise is additional in lemmatization. Hence, lemmatization is computationally expensive.   
With that, the review text is ready to be used for feature extraction. We will save that part for the next case study. The objective of this case study is to perform various text data preprocessing techniques on a real data set, which has been achieved. 

  
Use the data attached to answer the following questions.

Download [Quiz data file](tripadvisor_hotel_reviews.csv)

#### Tokenisation

Qn: How many words does the 1111th review \[index number 1110\] from the data set attached have?

- 100

- 115

- 124

- 142

Ans: C. *Tokenise the review into words and then count the number of elements in the list. The code for the solution can be found below.*

```python
import pandas as pd

hotel=pd.read_csv('tripadvisor_hotel_reviews.csv')
hotel.head(5)

text = hotel["Review"][1110]

import re

def remove_digits(text):
    regrex_pattern = re.compile(pattern = "["
        u"\U00000030-\U00000039" 
                           "]+", flags = re.UNICODE)
    return regrex_pattern.sub(r'',text)

def add_space(text):
    regrex_pattern = re.compile(pattern = "["
        u"\U0000002E" 
                           "]+", flags = re.UNICODE)
    return regrex_pattern.sub(r' ',text)

def remove_excalmation(text):
    regrex_pattern = re.compile(pattern = "["
        u"\U00000021-\U0000002F" 
                           "]+", flags = re.UNICODE)
    return regrex_pattern.sub(r'',text)

text = remove_digits(text)
text = add_space(text)
text = remove_excalmation(text)

from nltk.corpus import stopwords
from nltk.tokenize.toktok import ToktokTokenizer

#Tokenization of text
tokenizer=ToktokTokenizer() 

tokens = tokenizer.tokenize(text)

len(tokens)
```

#### Stop Word Removal

Qn: In the same review processed above, remove the stop words from the text. What is the length of the text (number of words) after removing the stop words?

- 124

- 121

- 88

- 72

Ans: B. *Use the NLTK stop words list to remove the stop words from the text and then check its length. The code for the solution can be found attached below.  Note that the text already seems to be devoid of stop words.*

```python
#Setting English stopwords
stopword_list=nltk.corpus.stopwords.words('english')

#Removing standard english stopwords like prepositions, adverbs
from nltk.tokenize import word_tokenize,sent_tokenize

stop=set(stopwords.words('english'))
print(stop)

#Removing the stopwords
def remove_stopwords(text, is_lower_case=False):
    tokens = tokenizer.tokenize(text)
    tokens = [token.strip() for token in tokens]
    if is_lower_case:
        filtered_tokens = [token for token in tokens if token not in stopword_list]
    else:
        filtered_tokens = [token for token in tokens if token.lower() not in stopword_list]    
    return filtered_tokens
```

#### Stemmer

Qn: Use the snowball stemmer to stem the text. What does the word ‘onduty’ change to after stemming?

- Onduty

- Onduti

- Duty

- Duti

Ans: B. *After stemming, the word ‘onduty’ becomes ‘onduti’. A simple rule of replacing y with i is followed in this transformation.*

```python
from nltk.stem import WordNetLemmatizer,SnowballStemmer
from nltk.stem.porter import PorterStemmer
nltk.download('wordnet')

def simple_stemmer(text):
    ps=SnowballStemmer(language='english')
    return [ps.stem(word) for word in text]

text = simple_stemmer(text)

print (text)
```

Let’s hear the concluding remarks from Dr Balan.

**VIDEO**

With that, we have come to the end of this case study. In the next segment, let’s summarise your learnings so far.