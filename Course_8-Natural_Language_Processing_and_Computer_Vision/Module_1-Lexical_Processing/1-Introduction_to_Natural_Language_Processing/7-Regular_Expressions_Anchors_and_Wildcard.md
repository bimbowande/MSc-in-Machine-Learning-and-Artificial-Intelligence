# Regular Expressions - Anchors and Wildcard

Now, you will learn about anchors in regular expressions. Anchors are used to specify the start and end of the string. Watch the following video where Krishna explains what anchors are and how to use them.

  
**Note**: There is a correction in the video. In the comment of the python code,   
print(find_pattern("India", "a$"))   #return true if the string ends with 'a' and not 'c'.   
print(find_pattern("Japan", "a$"))  #return true if the string ends with 'a' and not 'c'. 

**VIDEO**

In the video, you learnt about the two anchors characters – ‘^’ and ‘$’.

The ‘^’ specifies the start of the string. The character followed by the ‘^’ in the pattern should be the first character of the string in order for a string to match the pattern.

Similarly, the ‘$’ specifies the end of the string. The character that precedes the ‘$’ in the pattern should be the last character in the string for it to match the pattern.
  
Both the anchors can be specified in a single regular expression itself. For example, the regular expression pattern ‘^01*0$’ will match any string that starts and ends with zeroes with any number of 1s between them. It will match ‘010’, ‘0110’, ‘01111111110’ and even ‘00’ (‘*’ matches zero or more 1s). But it will not match the string ‘0’ because there is only one 0 in this string and in the pattern, we have specified that, there needs to be two 0s, one at the start and one at the end.

### Anchors

#### Description
Write a pattern that matches all the dictionary words that start with ‘A’  
  
Positive matches (should match all of these):  
Avenger  
Acute  
Altruism  
  
Negative match (shouldn’t match any of these):  
Bribe  
10  
Zenith

#### Solution
```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "A^"# write your regex here

# check whether pattern is present in string or not
result = re.search(pattern, string, re.I)  # re.I ignores the case of the string and the pattern

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
if result != None:
    print(True)
else:
    print(False)
```

#### Description
Write a pattern which matches a word that ends with ‘ing’. Words such as ‘playing’, ‘growing’, ‘raining’, etc. should match while words that don’t have ‘ing’ at the end shouldn’t match.

#### Solution
```python
# 15_1

import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = ".*(ing)$"# write your regex here

# check whether pattern is present in string or not
result = re.search(pattern, string)  # pass parameters to the re.search() function

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
if result != None:
    print(True)
else:
    print(False)
```

Now, there is one special character in regular expressions that acts as a placeholder and can match any character (literally) in the given input string. The ‘.’ (dot) character is also called the **wildcard character**.  

**VIDEO**

Till now, you were mentioning the exact character followed by a quantifier in your regular expression patterns. For example, the pattern ‘hur{2,}ay’ matches ‘hurray’, ‘hurrray’, ‘hurrrray’ and so on. Here, we had specified that the letter ‘r’ should be present two or more times. However, you do not always know the letter that you want to repeat. In such situations, you will need to use the wildcard instead. 

The wildcard comes in handy in many situations. It can be followed by a quantifier which specifies that any character is present a specified number of times.

For example, if you are asked to write a regex pattern that should match a string that starts with four characters followed by three 0s and two 1s and any two characters, the valid strings can be abcd00011ft, jkds00011hf, etc. The pattern that satisfies this kind of condition would be ‘.{4}0{3}1{2}.{2}’. You can also use ‘....00011..’ where the dot acts as a placeholder which means anything can sit in the place of the dot. Both are correct regex patterns.

### Wildcard

#### Description
Write a regular expression to match password that has length between three and fifteen characters.

Sample positive match:

Amandeep
Krishna

Sample negative match:

Balasubrahmanyam

#### Solution
```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "^.{3,15}$" # write your regex here

# check whether pattern is present in string or not
result = re.search(pattern, string)

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
if result != None:
    print(True)
else:
    print(False)
```

So, you learnt how the ‘.’ character can act as a placeholder for any character and how to use it. In the next section, you’ll learn about character sets.