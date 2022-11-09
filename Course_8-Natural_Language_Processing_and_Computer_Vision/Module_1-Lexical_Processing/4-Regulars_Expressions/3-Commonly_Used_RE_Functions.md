# Commonly Used RE Functions

Till now you’ve seen only one function of the 're' module, that is, the 're.search()' function. While it is a very common function used while working with regular expressions in python, it is not the only function that you’d use while working with regular expressions.

You’re going to learn about four more functions in this section where Krishna explains them one-by-one. Let’s look at the other functions.

**VIDEO**

You learnt about the match function and the search function. The match function will only match if the pattern is present at the very start of the string. On the other hand, the search function will look for the pattern starting from the left of the string and keeps searching until it sees the pattern and then returns the match.

#### The 're.match()' function

Qn: Given the pattern ‘\d+’, on which of the following strings will the 're .match()' function return a non-empty match. (Multiple choices may be correct)

- dummy_user_001

- 100_crores

- 78

- UpGrad

Ans: B & C. *`re.match()` returns a non-empty match only if the match is present at the very beginning of the string. The pattern is present in the string right at the start. The substring ‘100’ satisfies the condition.*

The next function that you’re going to study is the _re__.sub()_ function. It is used to substitute a substring with another substring of your choice. 

Regular expression patterns can help you find the substring in a given corpus of text that you want to substitute with another string. For example, you might want to replace the American spelling ‘color’ with the British spelling ‘colour’. Similarly, the _re__.sub()_ function is very useful in text cleaning. It can be used to replace all the special characters in a given string for example, remove '\$','@' and '\*' in the string '\$hello @wo\*rld'.

Next, Krishna will explain how to use the _re.sub()_ function.

**VIDEO**

The re.sub() function is used to substitute a part of your string using a regex pattern. It is often the case when you want to replace a substring of your string where the substring has a particular pattern that can be matched by the regex engine and then it is replaced by the re.sub() command. 

Note that, this command will replace all the occurrences of the pattern inside the string. For example, take a look at the following command:

```python
pattern = "\\d"
replacement = "X"
string = "My address is 13B, Baker Street"

re.sub(pattern, replacement, string)
```

It will change the string to: "My address is XXB, Baker Street"

### The 're.sub()' function

#### Description

You are given the following string:   
  
“You can reach us at 07400029954 or 02261562153 ”  
   
Substitute all the 11-digit phone numbers present in the above string with “####”.

#### Solution

```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "\d{11}" # write a regex that detects 11-digit number

# replacement string
replacement = "####" # write the replacement string

# check whether pattern is present in string or not
result = re.sub(pattern, replacement, string)

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
if (re.search(replacement, result)) != None:
    print(True)
else:
    print(False)
```

#### Description

Write a regular expression such that it replaces the first letter of any given string with ‘$’.   
  
For example, the string ‘Building careers of tomorrow’ should be replaced by “$uilding careers of tomorrow”.

#### Solution

```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "[A-z]" # write a regex that detects the first character of a string

# replacement string
replacement = "$" # write the replacement string
#Hint: give the arguments to the below re.sub() function

# check whether pattern is present in string or not
result = re.sub(pattern, replacement, string)  # pass the parameters to the sub function

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
print(result[0] == '$')
```

The next set of functions let you search the entire input string and return all the matches, in case there are more than one present. In the following video, Krishna explains the remaining functions.

**VIDEO**

To summarise, the match and search command return only one match. But you often need to extract all the matches rather than only the first match, and that's when you use the other methods.

Suppose, in a huge corpus of text, you want to extract all the dates, in that case you can use the finditer() function or the findall() function to extract the results. The result of the findall() function is a list of all the matches and the finditer() function is used in a 'for' loop to iterate through each separate match one by one.

The following questions will help you practice these functions.

### The 're.finditer()' function

#### Description

Write a regular expression to extract all the words from a given sentence. Then use the re.finditer() function and store all the matched words that are of length more than or equal to 5 letters in a separate list called result.  
  
Sample input:  
"Do not compare apples with oranges. Compare apples with apples"  
  
Expected output:  
6

#### Solution

```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "[A-z]+" # write regex to extract all the words from a given piece of text

# store results in the list 'result'
result = []

# iterate over the matches
for match in re.finditer(pattern, string): # replace the ___ with the 'finditer' function to extract 'pattern' from the 'string'
    if len(match.group()) >= 5:
        result.append(match)
    else:
        continue

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
print(len(result))
```

### The 're.findall()' function

#### Description

Write a regular expression to extract all the words that contain ‘ing’ using the re.findall() function. Store the matches in the variable ‘results’ and print its length.

Sample input:
"Playing outdoor games when its raining outside is always fun!"

Expected output:
2

#### Solution

```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "[A-z]+ing" # write regex to extract words ending with 'ing'

# store results in the list 'result'
result = re.findall(pattern, string) # extract words having the required pattern, using the findall function

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
print(len(result))
```

In the next section, you’ll learn about **grouping** a regular expression into different parts.