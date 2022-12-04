# Regular Expressions: Characters Sets

Until now, you were either using the actual letters (such as ab, 23 and 78) or the wildcard character in your regular expression patterns. There was no way of saying that the preceding character is a digit, an alphabet, a special character, or a combination of these.

For example, say you want to match phone numbers in a large document. You know that the numbers may contain hyphens, plus symbols, etc. (e.g., +91-9930839123), but it will not have any alphabet. You will have to somehow specify that you are looking only for numerics and some other symbols but avoid alphabets.

To handle such situations, you can use what are called character sets in regular expression jargon.

The following lecture explains the various types of character sets available in regular expressions and how you can use them in different situations.

**Note**: At 1:47, "the ASCII values of a,b,c.... are 97,98,99,......". Also, the ASCII codes of [A-z] contain non-alphabet characters between 91 and 96.

**Note**: A-Z is case-sensitive and not insensitive.

Play Video

3221820

Character sets provide a lot more flexibility than just typing a wildcard or the literal characters. Character sets can be specified with or without a quantifier. When no quantifier succeeds the character set, it matches only one character, and the match is successful only if the character in the string is one of the characters present inside the character set. For example, the pattern ‘[a-z]ed’ will match strings such as ‘ted’, ‘bed’ and ‘red’ because the first character of each string such as ‘t’, ‘b’ and ‘r’ is present inside the range of the character set.

On the other hand, when we use a character set with a quantifier such as ‘[a-z]+ed’ in this case, it will match any word that ends with ‘ed’ such as ‘watched’, ‘baked’, ‘jammed’ and ‘educated’. In this way, a character set is similar to a wildcard because it can also be used with or without a quantifier. It is just that a character set gives you more power and flexibility.

Note that a quantifier loses its special meaning when it is present inside the character set. Inside square brackets, it is treated as any other character. 

You can also mention a whitespace character inside a character set to specify one or more whitespaces inside the string. The pattern [A-z] can be used to match the full name of a person. It includes a space so it can match the full name which includes the person’s first name, a space and the last name.

But what if you want to match every other character other than the one mentioned inside the character set? You can use the caret operator to do this. Here, Krishna explains the use of caret operator inside a character set.

Play Video

3221820

The ‘^’ has two use cases. You already know that it can be used outside a character set to specify the start of a string. Here, it is known as an anchor.

Its another use is inside a character set. When used inside a character set, it acts as a complement operator, i.e., it specifies that it will match any character other than the ones mentioned inside the character set.

The pattern [0-9] matches any single-digit number. On the other hand, the pattern ‘[^0-9]’ matches any single-digit character that is not a digit.

## Meta-Sequences

When you work with regular expressions, you will find yourself using characters often. You will commonly use sets to match only digits, only alphabets, only alphanumeric characters, only whitespaces, etc.

Therefore, there is a shorthand way to write commonly used character sets in regular expressions. These are called meta-sequences. In the following video, Krishna explains the use of meta-sequences.

Play Video

3221820

Those were the commonly used meta-sequences. You can use meta-sequences in the following two ways:

1.  You can use them without the square brackets. For example, the pattern ‘\w+’ will match any alphanumeric character.
    
2.  You can also put them inside the square brackets. For example, the pattern ‘[\w]+’ is the same as ‘\w+’. But when you use meta-sequences inside a square bracket, they are commonly used along with other meta-sequences. For example, the ‘[\w\s]+’ matches both alphanumeric characters and whitespaces. The square brackets are used to group these two meta-sequences into one.
    

Practice the use of meta-sequences in the following exercise.

### Meta-sequences

#### Description
Write a regular expression with the help of meta-sequences that matches usernames of the users of a database. The username starts with alphabets of length one to ten characters long and then followed by a number of length 4.  
  
Sample positive matches:  
sam2340   
irfann2590   
  
Sample negative matches:  
8730   
bobby9073834   
sameer728   
radhagopalaswamy7890

#### Solution
```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "^[A-z]{1,10}[0-9]{4}$" # write your regex here

# check whether pattern is present in string or not
result = re.search(pattern, string, re.I)

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
if result != None:
    print(True)
else:
    print(False)
```

With that you have learnt the basics of regex. Although regular expressions are the most fundamental tools for text analytics, in actual practice, you will not frequently use regex.  Nonetheless, it will be useful to know the use of regular expressions. To learn more about the regular expressions, you can visit the optional session.