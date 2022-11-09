# Greedy versus Non-Greedy Search

When you use a regular expression to match a string, the regex greedily tries to look for the longest pattern possible in the string. For example, when you specify the pattern 'ab{2,5}' to match the string 'abbbbb', it will look for the maximum number of occurrences of 'b' (in this case 5).

This is called a 'greedy approach'. By default, a regular expression is greedy in nature.

There is another approach called the non-greedy approach, also called the lazy approach, where the regex stops looking for the pattern once a particular condition is satisfied.

The following video uses the basic concept of HTML, for this you can refer to this [link](https://html.com/).

Let’s look in detail when and how to use the non-greedy technique.

**VIDEO**

Let’s understand the non-greedy or the lazy approach with another example. Suppose, you have the string ‘3000’. Now, if you use the regular expression ‘30+’, it means that you want to look for a string which starts with ‘3’ and then has one or more '0's followed by it. This pattern will match the entire string, i.e. ‘3000’. This is the greedy way. But if you use the non-greedy technique, it will only match ‘30’ because it still satisfies the pattern ‘30+’ but stops as soon as it matches the given pattern.

It is important to not confuse the greedy approach with matching multiple strings in a large piece of text - these are different use cases. Similarly,  the lazy approach is different from matching only the first match.

For example, take the string ‘One batsman among many batsmen.’. If you run the patterns ‘bat*’ and ‘bat*?’ on this text, the pattern ‘bat*’ will match the substring ‘bat’ in ‘batsman’ and ‘bat’ in ‘batsmen’ while the pattern ‘bat*?’ will match the substring ‘ba’ in batsman and ‘ba’ in ‘batsmen’. The pattern ‘bat*’ means look for the term ‘ba’ followed by zero or more ‘t’s so it greedily looks for as many ‘t’s as possible and the search ends at the substring ‘bat’. On the other hand, the pattern ‘bat*?’ will look for as few ‘t’s as possible. Since ‘*’ indicates zero or more, the lazy approach stops the search at ‘ba’.

To use a pattern in a non-greedy way, you can just put a question mark at the end of any of the following quantifiers that you’ve studied till now:

-   \*
    
-   \+
    
-   ?
    
-   {m, n}
    
-   {m,}
    
-   {, n}
    
-   {n}
    

The lazy quantifiers of the above greedy quantifiers are:

-   \*?
    
-   +?
    
-   ??
    
-   {m, n}?
    
-   {m,}?
    
-   {, n}?
    
-   {n}?
    

To strengthen your understanding of greedy vs non-greedy search, attempt the following exercise.

### Non_Greedy Search

#### Description

You’re given the following html code:

```html
<html>
<head>
<title> My amazing webpage </title>
</head>
<body> Welcome to my webpage! </body>
</html>
```

Write a non-greedy regular expression to match the contents of only the first tag (the `<html>` tag in this case) including the angular brackets.

#### Solution

```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "<.*?>" # write your regex here

# check whether pattern is present in string or not
result = re.search(pattern, string, re.M)  # re.M enables tha tpettern to be searched in multiple lines

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
if (result != None) and (len(result.group()) <= 6):
    print(True)
else:
    print(False)
```

In the next section, you’ll learn about the various re functions that you can leverage to help you with your text analysis.