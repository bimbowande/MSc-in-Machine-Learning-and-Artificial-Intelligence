# Regular Expressions - Quantifiers - II

In the last section, you learnt how to match strings with the ‘?’ and the ‘*’ quantifiers:

-   The ‘?’ matches the preceding character zero or one time. It is generally used to mark the **optional presence** of a character.
-   The ‘*’ quantifier is used to mark the presence of the preceding character **zero or more times.**

Now, you’ll learn about a new quantifier - the '+'.

**VIDEO**

The ‘+’ quantifier causes the resulting RE to match one or more repetitions of the preceding RE. That means the preceding character has to be present at least once for the pattern to match the string.'

  
For example, ab+ will successfully match ab, abb but ab+ will not match a.   
Thus, the only difference between '+' and '*' is that the '+' needs a character to be present at least once while the '*' does not.

#### Quantifiers

#### Description
Krishna had said in the video that the pattern ‘ab+’ will not match the string ‘ac’. Try it for yourself by running the following piece of code and see if the re.search() function finds a match or not.

#### Solution
```python
import re

# input string
string = "ac"

# regex pattern
pattern = "ab+"

# check whether pattern is present in string or not
result = re.search(pattern, string)

# print result
if result != None:
    print(True)
else:
    print(False)
```

You can also play around with the '+' quantifier by using it to match different types of strings. Finally, reset the code by reloading this page before submitting.

Qn: Let’s say you have this pattern - ‘abc+d’. Which of the following strings will not be matched by this pattern?  
 
- abcd

- abccd

- abd

- abccccccccd

Ans: C. *The '+' quantifier will match the string if the preceding character is present one or more times. Here, the character ‘c’ is not present which doesn't meet the condition.*

To summarise, you have learnt the following quantifiers until now:

-   '?': Optional preceding character
-   '*': Match preceding character zero or more times
-   '+': Match preceding character one or more times (i.e., at least once)

But how do you specify a regex when you want to look for a character that appears, say, exactly five times, or between three and five times? You cannot do that using the quantifiers mentioned earlier.

  
Hence, the next quantifier that you will learn will help you specify occurrences of the preceding character a fixed number of times.

Play Video

3221820

Following are the four variants of the quantifier that you just saw:

1.  {m, n}: Matches the preceding character ‘m’ times to ‘n’ times
2.  {m, }: Matches the preceding character ‘m’ times to infinite times, i.e., there is no upper limit to the occurrence of the preceding character
3.  {, n}: Matches the preceding character from zero to ‘n’ times, i.e., the upper limit is fixed regarding the occurrence of the preceding character
4.  {n}: Matches if the preceding character occurs exactly ‘n’ number of times

Note that while specifying the {m,n} notation, avoid using a space after the comma, i.e., use {m,n} rather than {m, n}.

An interesting thing to note is that this quantifier can replace the ‘?’, ‘*’ and the ‘+’ quantifiers. That is because:

1.  '?' is equivalent to zero or once, or {0, 1},
2.  '*' is equivalent to zero or more times, or {0, }, and
3.  '+' is equivalent to one or more times, or {1, }.

#### Quantifiers

Qn: The ‘?’ quantifier equivalent to which of the following quantifiers:

- {0,}

- {1,}

- {0,1}

- {0}

Ans: C. *The quantifier {0, 1} will match the preceding character zero or one time. This is equivalent to what the ‘?’ does as it also matches the preceding character zero or one time.*

Qn: The ‘+’ quantifier equivalent to which of the following quantifiers:

- {0,}

- {1,}

- {0, 1}

- {0}

Ans: B. *The quantifier {1,} will match the preceding character one or more times. This is equivalent to what the ‘+’ does as it also matches the preceding character one or more times.*

Now, practice some questions on the {m, n} quantifier in the exercise given below.

### Quantifiers

#### Description
Write a regular expression to match the word ‘hurray’. But match only those variants of the word where there are a minimum of two ‘r’s and a maximum of five ‘r’s.

#### Solution
```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "hur{2,5}ay" # write your regex pattern here

# check whether pattern is present in string or not
result = re.search(pattern, string)  # pass the pattern and string arguments to the function

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
if result != None:
    print(True)
else:
    print(False)
```

You learnt about all the quantifiers. In the next section, you will learn about wildcards and anchors.