# Regular Expressions: Grouping

Sometimes you need to **extract sub-patterns out of a larger pattern**. This can be done by using **grouping**. Suppose you have textual data with dates in it and you want to extract only the year. from the dates. You can use a regular expression pattern with **grouping** to match dates and then you can extract the component elements such as the day, month or the year from the date.

Grouping is achieved using the parenthesis operators. Let’s understand grouping using an example.

Let’s say the source string is: “Kartik’s birthday is on 15/03/1995”. To extract the date from this string you can use the pattern - “\\d{1,2}\\/\\d{1,2}\\/\\d{4}”.

Now to extract the year, you can put parentheses around the year part of the pattern. The pattern is: “^\d{1,2}/\d{1,2}/(\d{4})$”.

Let’s see a demonstration of how to use grouping.

**VIDEO**

Grouping is a very useful technique when you want to extract substrings from an entire match. Let's practice some questions on grouping in the following quiz.

### Grouping

#### Description

You have a string which contains a data in the format DD-MM-YYYY. Write a regular expression to extract the date from the string.  
  
Sample input:  
"Today’s date is 18-05-2018."  
  
Sample output:  
18-05-2018

#### Solution

```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "\d{2}-\d{2}-\d{4}" # write regex to extract date in DD-MM-YYYY format

# store result
result = re.search(pattern, string)  # pass the parameters to the re.search() function

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
if result != None:
    print(result.group(0))  # result.group(0) will output the entire match
else:
    print(False)
```

#### Description

In the last exercise, you had extracted the date from a given string. In this coding exercise, write the same regular expression. But this time, use grouping to extract the month from the date. The expected date format is DD-MM-YYYY only.  
  
Sample input:   
Today's date is 18-05-2018  
   
Expected output:   
05

#### Solution

```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "\d{2}-(\d{2})-\d{4}"# write regex to extract date and use grouping to extract month

# store result
result = re.search(pattern, string)

# extract month using group command
if result != None:
    month = result.group(1) # extract month using group command
else:
    month = "NA"

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
print(month)
```

### Groups

#### Description

Write a regular expression to extract the domain name from an email address. The format of the email is simple - the part before the ‘@’ symbol contains alphabets, numbers and underscores. The part after the ‘@’ symbol contains only alphabets followed by a dot followed by ‘com’   
   
Sample input:   
user_name_123@gmail.com   
   
Expected output:   
gmail.com

#### Solution

```python
import re
import ast, sys
string = sys.stdin.read()

# regex pattern
pattern = "[0-9A-z_]*@([a-z]+[.]com)" # write regex to extract email and use groups to extract domain name ofthe mail

# store result
result = re.search(pattern, string)

# extract domain using group command
if result != None:
    domain = result.group(1) # use group to extract the domain from result
else:
    domain = "NA"

# evaluate result - don't change the following piece of code, it is used to evaluate your regex
print(domain)
```

You’ve come a long way and learnt almost all important concepts related to regular expressions. In the next section, you’ll see some examples where regular expressions can be used.