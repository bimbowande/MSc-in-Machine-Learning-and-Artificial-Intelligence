# Zomato Case Study: Basic Text Processing

Now, let’s begin by sanitising the text, that is, removing the emojis, URLs and other components that make a review noisy. In the next video, Mahesh will take a custom review that has many noisy elements and remove these elements programmatically. Once the program works on a single review, it can be applied to the complete column. 

**VIDEO**

The review used in the video is provided below. 

| `<div><h1><Title>The apple π was [*][AMAZING][*] and YuMmY too😂! You can Checkout the entire Menu in https://www.zomato.com/chennai/top-restaurants</div></h1></Title>` |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|

The review has residual HTML tags, URLs, emojis and a few other problems. 

  
#### Removing HTML tags 

  
Beautiful Soup is a Python library that can be used to remove HTML tags. Passing the review to Beautiful Soup enables you to extract text. The code given below is the same code that Mahesh used to remove HTML tags.

```python
#Removing the html strips
from bs4 import BeautifulSoup

def strip_html(text):
    soup = BeautifulSoup(text, "html.parser")
    return soup.get_text()

text = strip_html(text)
print(text)
```

A function is created from the Beautiful Soup library to extract text from HTML files. Post this, every time you want to delete HTML tags, you can call the same function. 

  
#### Removing URLs

Regular expressions can be used to remove URLs. Every URL starts with a transfer protocol tag. In most cases, it is ‘https://’. You can use regex pattern matching to search for this pattern and remove all the text that follows it.   
The code given below will show the implementation of regex to remove URLs. 

```python
import re

text = re.sub(r"http\S+", "", text)
print(text)
```

There is nothing new to see in this code; you have already learnt about the use of regex. This code above will match any text that starts with ‘http’ and replace it with blanks. 

#### Removing emojis

In the backend, all emojis and special characters are also encoded. Each of them has a specific pattern. You can use regex to create patterns that match the emojis and remove them using the regrex_pattern.sub method. This method substitutes functions such as ‘find and replace’. Once a match pattern is detected, you can replace it with a blank.   
Removing emojis is also a regex job, but one needs to know the right pattern to match. The code that Mahesh wrote for removing emojis used unicodes to match the pattern. The code is given below.   
 

```python
def deEmojify(text):
    regrex_pattern = re.compile(pattern = "["
        u"\U0001F600-\U0001F64F"  # emoticons
        u"\U0001F300-\U0001F5FF"  # symbols & pictographs
        u"\U0001F680-\U0001F6FF"  # transport & map symbols
        u"\U0001F1E0-\U0001F1FF"  # flags (iOS)
                           "]+", flags = re.UNICODE)
    return regrex_pattern.sub(r'',text)

text = deEmojify(text)
print(text)
```

The first command in the function is regex.compile(). It is used to create a regex object from the text that it is provided with. You can read more about the compile function in the [python documentation](https://docs.python.org/3/library/re.html#re.compile). Next, the text that is passed to the compile function is composed of all the unicodes representing emojis. 

The unicode is a universal code that has all the emojis and symbols that you will ever need. You can find the list of all the unicodes on this [page](https://unicode-table.com/en/sets/). By choosing the codes that you want, you can create a custom set of emojis and symbols to process. If you do not want certain emojis to be removed, you can remove them from this list.

| Symbol | Unicode | Unicode Complete |
|--------|---------|------------------|
| 🍕      | U+1F355 | U0001F355        |

If you remove the code for pizza from the deEmojify function given above, it will be left in the corpus.   
After all the processing steps mentioned above, the same review will look like this:  
 
| The apple π was [*][AMAZING][*] and YuMmY too! You can Checkout the entire Menu in |
|------------------------------------------------------------------------------------|

Although this is much cleaner than the original, there are still other problems such as the Greek letter pi, square brackets and the mismatching case. In the next video, Dr Balan will demonstrate a way to handle these issues. 

**VIDEO**

After going through the demonstration, hopefully, you understand the need for and the use of text encoding. Earlier, when you learnt about text encoding, it was only a way to convert letters of the alphabet into digits, but in the real world, it can be used to remove noise from text as well. 

Using the ASCII encoding, you can remove all the characters that are not present in the encoding, but that will result in loss of information. For instance, in this case, by removing the letter pi, we lost the name of the dish being referred to. Whether the loss of information is acceptable or not depends on the application that you are building. The code given below can help encode and decode text.   
 

```python
# ASCII encoding 
text = text.encode('ascii', 'ignore')
print(text)

# Unicode encoding 
def to_unicode(text):
    if isinstance(text, float):
        text = str(text)
    if isinstance(text, int):
        text = str(text)
    if not isinstance(text, str):
        text = text.decode('utf-8', 'ignore')
    return text
```

You already know the use of the encode and decode functions. By executing the encode and decode cycle and suppressing the warnings, any character that is not present in the encoding standard gets removed. The isinstance() function checks whether the given input is of the given type. In this case, it is being used to convert floats and int to string.    
After using the text encoding method, the review looks like this:  
 
| The apple was  [*][AMAZING][*] and YuMmY too! You can Checkout the entire Menu in |
|-----------------------------------------------------------------------------------|

Next, you need to get rid of the square brackets. However, in doing so, whether or not the word inside the brackets goes is up to the application that you are building. In the next video, let’s see how Mahesh removes the square brackets. 

**VIDEO**

In this demonstration, you saw how the square brackets were completely removed. This approach might not work in some cases. In the video given above, you learnt about the code that is used to remove the brackets and the text inside. Try writing a regex to remove only the brackets and keep the text as-is. For the quiz given below use the data file attached here. 

Download [Quiz data file](tripadvisor_hotel_reviews.csv)

#### Removing digits

Qn: Write a code to remove the digits from the 30th review given above. After removing the digits, how many characters left in the review? (including spaces) 

Hint: Use encoding to find all the nine decimal digits. Then, you can reuse the deEmojify function to create the pattern to remove digits. You will need to find the Unicode codes for all the digits; you can use the Internet to do that.  
 

- 177

- 214

- 235

- 267

Ans: C. *The relevant review can be found by using pandas indexing. The code to achieve the rest of the solution is given below.*

```python
import pandas as pd

#Importing the training data
hotel=pd.read_csv('tripadvisor_hotel_reviews.csv')
hotel.head(5)

import re

def remove_digits(text):
    regrex_pattern = re.compile(pattern = "["
        u"\U00000030-\U00000039" 
                           "]+", flags = re.UNICODE)
    return regrex_pattern.sub(r'',text)

text = hotel["Review"][29]

text = remove_digits(text)
len(text)
```

#### Removing Punctuation

Qn: The text given below is the 30th review after removing the digits.

_'good hotel not large hotel newly decorated, rooms good size clean, excellent location  blocks centre town  blocks market area.hotel resturant bustling place alot diners coming street, good meal there.overall highly recommend staying,  '_ 

Note that in the text given above, the full stops have characters on both sides and there is no space between two sentences.

Which of the following functions will be able to replace the full stop with space?  
 
- 
```python
def add_space(text):
    regrex_pattern = re.compile(pattern = "["
        u"\U0000002E" 
                           "]+", flags = re.UNICODE)
    return regrex_pattern.sub(r' ',text)
```

- 
```python
def add_space(text):
    regrex_pattern = re.compile(pattern = "["
        u"\U0000001E" 
                           "]+", flags = re.UNICODE)
    return regrex_pattern.sub(r' ',text)
```

- 
```python
def add_space(text):
    regrex_pattern = re.compile(pattern = "["
        u"\U0000002E" 
                           "]+", flags = re.UNICODE)
    return regrex_pattern.sub(r'',text)
```

- 
```python
def add_space(text):
    regrex_pattern = re.compile(pattern = "["
        u"\U0000002A" 
                           "]+", flags = re.UNICODE)
    return regrex_pattern.sub(r' ',text)
```

Ans: A. *To check the correctness of the function simply run it in your jupyter notebook and then pass the sample text to it.*

In addition to handling the square brackets, Mahesh used regex to remove all the symbols and special characters. Finally, he used the inbuilt Python lower() function to convert the text to lower case. After all the cleaning steps, the review looks like this: 

| the apple  was  and yummy too you can checkout the entire menu in |
|-------------------------------------------------------------------|

Now this text is ready for advanced preprocessing. In the next segment, perform all the cleaning steps that we did here on the entire data set, post which you can continue prepping the text.