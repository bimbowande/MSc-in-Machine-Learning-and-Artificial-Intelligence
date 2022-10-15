# Regular Expressions: Quantifiers - I

From this segment onwards, you will learn about regular expressions. **Regular expressions**, also called **regex**, are very powerful programming tools that are used for a variety of purposes such as feature extraction from text, string replacement and other string manipulations.   
A regular expression is a set of characters, or a **pattern**, which is used to find substrings in a given string. 
  
Let’s say you want to extract all the hashtags from a tweet. A hashtag has a fixed pattern to it, i.e., a pound (‘#’) character followed by a string. Some example hashtags are #India, #upgrad and #covid19. You could easily achieve this task by providing this pattern and the tweet that you want to extract the pattern from (in this case, the pattern is any string starting with #). Another example is to extract all the phone numbers from a large piece of textual data.

In short, if there is a pattern in any string, you can easily extract, substitute and do all kinds of other string manipulation operations using regular expressions. Learning regular expressions basically means learning how to identify and define these patterns.

Regular expressions are a language in itself since they have their own compilers. Almost all popular programming languages support working with regexes and so does Python.  
Let's take a look at how to work with regular expressions in Python. Download the given Jupyter notebook to follow along:

Download [Regular Expressions Jupyter Notebook](Regular_Expressions.ipynb)

**VIDEO**

In the video, Krishna gave a brief introduction to regular expressions and their use. You can find all the code that is demonstrated in the notebook attached before the video.   
Let’s look at an example of a simple pattern search. 

```python
re.search('Ravi', 'Ravi is an exceptional student!')
```

The re.search is the method used to perform simple text searches. The first argument is the search key and the second argument is the corpus in which the search operation should be performed. Now, look at the printed result.

![RE Search](https://i.ibb.co/ygdNhmY/RE-Search.png)

It shows that a match has been found with the match position and the text which is matched.

**General Note on Practice Coding Questions**

In the practice questions that you will attempt in this module, the phrases ‘match string’ and ‘extract string’ will be used interchangeably. In both cases, you need to use the 're.search()' function which detects whether the given regular expression pattern is present in the given input string. The 're.search()' method returns a [RegexObject](https://docs.python.org/2/library/re.html#re.RegexObject) if the pattern is found in the string, else it returns a none object.

After writing your code, you can use the 'Run' and 'Verify' buttons to evaluate your code against sample test cases. After verifying the code, you can 'Submit' the code which will then be validated against the (hidden) test cases.

The comments in the coding questions will guide you with these nuances. Also, you can look at the sample solution after submitting your code, i.e., after the maximum number of allowed submissions, at the bottom of the coding console window.

### Regular Expressions

#### Description
Consider the following sentence: "The roots of education are bitter, but the fruit is sweet.".

#### Solution
```python
# import the regular expression module
import re

import ast, sys
# input string 'The roots of education are bitter, but the fruit is sweet.' is given in sample test case
string = sys.stdin.read()

# regex pattern to check if 'education' is present in a input string or not.
pattern = "education" # write regex to extract 'education'

# check whether pattern is present in string or not
result = re.search(pattern, string)

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
if result != None:
    print(True)
else:
    print(False)
```
  
#### Description
Consider the same problem as the previous question.  Extract the word 'education' from the sentence  'The roots of education are bitter, but the fruit is sweet'. But this time, extract the **starting position** of the result using result.start().

#### Solution
```python
# import the regular expression module
import re

# input string on which to test regex pattern
string = 'The roots of education are bitter, but the fruit is sweet.'

# regular expression pattern to check if 'education' is present in a given string or not.
pattern = 'education'

# store the match of regex
result = re.search(pattern, string)

# store the start of the match
# use result.start()
start_position = result.start() # write code here

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
print(start_position)
```

Write a regular expression pattern to check whether the word ‘education’ is present in the given string or not. Use the re.search() function.

So that’s how you import regular expressions library in python and use it. You saw how to use the re.search() function - it returns a match object if the pattern is found in the string. Also, you saw two of its methods - match.start() and match.end() which return the index of the starting and ending position of the match found.

Apart from re.search(), there are other functions in the re library that are useful for other tasks. You’ll look at the other functions later in this session.

Now, the first thing that you’ll learn about regular expressions is the use of **quantifiers**. Quantifiers allow you to mention and have control over how many times you want the character(s) in your pattern to occur.

Let’s take an example. Suppose you have some data which have the word ‘awesome’ in it. The list might look like - [‘awesome’, ‘awesomeeee’, ‘awesomee’]. You decide to extract only those elements which have more than one ‘e’ at the end of the word ‘awesome’. This is where quantifiers come into picture. They let you handle these tasks.

You’ll learn four types of quantifiers:

1.  The ‘?’ operator
2.  The ‘*’ operator
3.  The ‘+’ operator
4.  The ‘{m, n}’ operator

  
The first quantifier is ‘?’. Let’s understand what the ‘?’ quantifier does.

**VIDEO**

You heard Krishna say that you’ll learn about five quantifiers instead of four. That’s because the fourth quantifier has some more variations. You’ll learn about it later in the session. 

The ‘?’  can be used where you want the preceding character of your pattern to be an **optional character in the string**. For example, if you want to write a regex that matches both ‘car’ and ‘cars’, the corresponding regex will be ’cars?’. ‘S’ followed by ‘?’ means that ‘s’ can be absent or present, i.e. it can be present zero or one time.

### Quantifiers

#### Description

Write a regular expression that matches the word ‘tree’ or ‘trees’ in a given piece of text.  
  
Sample positive cases:  
‘The tree stands tall.’  
‘There are a lot of trees in the forest.’  
  
Negative negative cases:   
‘The boy is heading for the school.’  
'It's really hot outside!'

#### Solution
```python
import ast, sys
string = sys.stdin.read() # input string

# import the regular expression module
import re

# regex pattern
pattern = "tree[s]?" # write regex here
#Hint: pass the arguments in below re.search() function.

# check whether pattern is present in string or not
result = re.search(pattern, string)  # pass the arguments to the re.search function

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
if result != None:
    print(True)
else:
    print(False)
```

The next quantifier that you’re going to study is the ‘*’ quantifier.

**VIDEO**

A ‘*’ quantifier causes the resulting regular expression (RE) to match 0 or more repetitions of the preceding RE.

For example, ab* will positively match a, ab, abbb and a followed by any number of bs. But the same search ab* will not match aab. 

Practice some of the given questions to strengthen your understanding of it.

### Quantifiers

#### Description

Match a binary number that starts with 101 and followed by zero or more number of zeroes.

Sample positive cases (pattern should match all of these):

1010

10100

101000

101

Sample negative cases (shouldn’t match any of these):

10

100

1

#### Solution
```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "101[0]*"# write your regex pattern here

# check whether pattern is present in string or not
result = re.search(pattern, string)

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
if result != None:
    print(True)
else:
    print(False)
```

You learnt two quantifiers - the ‘?’ and the ‘*’. In the next section, you’ll learn two more quantifiers.