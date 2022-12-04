# Regular Expressions: Use Cases

Let’s see some examples where regular expressions can be used as a handy tool. These use cases will demonstrate how can you use regular expressions for practical applications.

**VIDEO**

The following code demonstrates how regex can be used for a file search operation. Say you have a list of folders and filenames called 'items' and you want to extract (or read) only some specific files, say images.

```python
# items contains all the files and folders of current directory
items = ['photos', 'documents', 'videos', 'image001.jpg','image002.jpg','image005.jpg', 'wallpaper.jpg',
         'flower.jpg', 'earth.jpg', 'monkey.jpg', 'image002.png']

# create an empty list to store resultant files
images = []

# regex pattern to extract files that end with '.jpg'
pattern = ".*\.jpg$"

for item in items:
    if re.search(pattern, item):
        images.append(item)

# print result
print(images)
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

If you run the above code in Python, you’ll get the following result.

```python
['image001.jpg', 'image002.jpg', 'image005.jpg', 'wallpaper.jpg', 'flower.jpg', 'earth.jpg', 'monkey.jpg']
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

The above code extracts only those documents which have ‘.jpg’ extension. The pattern ‘.*\.jpg$’ is pretty self-explanatory. The important thing here is the use of backslash. If you don’t escape the dot operator with a backslash, you won’t get the results you want. Try to run the code without the escape sequence.

Take a look at another example. This is just an extension to the previous example. In this case, we’re trying to extract documents that start with the prefix ‘image’ and end with the extension ‘.jpg’. Here’s the code:

```python
# items contains all the files and folders of current directory
items = ['photos', 'documents', 'videos', 'image001.jpg','image002.jpg','image005.jpg', 'wallpaper.jpg',
         'flower.jpg', 'earth.jpg', 'monkey.jpg', 'image002.png']

# create an empty list to store resultant files
images = []

# regex pattern to extract files that start with 'image' and end with '.jpg'
pattern = "image.*\.jpg$"

for item in items:
    if re.search(pattern, item):
        images.append(item)

# print result
print(images)
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

The output of the above code is as follows:

```python
['image001.jpg', 'image002.jpg', 'image005.jpg']
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

You saw how to search for specific file names using regular expressions. Similarly, they can be used to extract features from text such as the ones listed below:

1.  Extracting dates
    
2.  Extracting emails
    
3.  Extracting phone numbers, and other patterns.
    

Along with the applications in NLP, regular expressions are extensively used by software engineers in various applications such as checking if a new password meets the minimum criteria or not, checking if a new username meets the minimum criteria or not, and so on.

Now, let’s end the session with a practical tip. You’ve already gotten to know that there are websites such as [this](https://regex101.com/) one which helps you to compile your regular expression because sometimes it can get very hard to write regular expressions. There are various other online tools as well which provide intuitive interfaces to write and test your regex instantly.

Let’s see how to make use of one such online tool, in the following video.

**VIDEO**

In the following video, Krishna demonstrates one more problem in the online tool that you just saw.

**VIDEO**

## **Regular Expressions - Practice Exercises**

Regular expressions happen to be one of those concepts which you'll be able to retain in memory only with frequent practice. There are numerous online tools that teach and let you practice regex, online. [Here](https://regexone.com/) is one such tool that you can use to quickly revise all the commnly used regex patterns and concepts.

If you want to practice regex, here is a Jupyter notebook that contains some practice questions. The solution of the above exercises can be download here.

Download [Regular Expressions - Bonus exercise with solution](Bonus_Exercise_with_Solution.ipynb)

That brings us to the end of the lecture on regular expressions. The next section summarises all the concepts that you learnt till now.