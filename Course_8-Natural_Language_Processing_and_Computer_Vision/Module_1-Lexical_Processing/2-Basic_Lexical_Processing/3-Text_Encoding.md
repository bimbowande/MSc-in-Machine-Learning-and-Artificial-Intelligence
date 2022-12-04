# Text Encoding

Before moving onto the text preprocessing step, let’s first understand how machines convert characters or symbols into machine language, that is, binary digits.

The biggest challenge with text analytics is that machines cannot process human language; they can process only binary data, that is, 0s and 1s. Text encoding is a way to convert letters of the alphabet of human language (high level) to machine language (binary). First, let’s hear from Dr Balan about his thoughts on text encoding. 

**VIDEO**

In this video, the ASCII standard of text encoding was discussed. The ASCII (American Standard Code for Information Interchange) standard was the first encoding standard to come into existence. It assigns a unique code to all normal letters as well as digits and some special characters. You can find the list of all ASCII characters [here](https://theasciicode.com.ar/). For example, the table provided below gives the ASCII code of a few characters. 

| Character | ASCII code in Decimal | ASCII code in Binary |
| --------- | --------------------- | -------------------- |
| A         | 65                    | 01000001             |
| p         | 112                   | 01110000             |
| %         | 37                    | 00100101             |

Notice the binary form of ASCII characters. Each character is eight digits long, which means it takes eight bits, or one byte, to store each character in ASCII encoding. The standard ASCII character always begins with a 0, i.e., it is in the form of 0xxxxxxx. There are only 128 unique combinations of 0 and 1 in the form shown above. 

When ASCII was built, only the letters of the English alphabet were used in the English language. With time, as the need for more and more characters was felt, the encoding system had to be expanded. In the video given below, you will learn about the Unicode standard, which was developed to overcome the limitation of characters in ASCII. 

**VIDEO**

As you saw in this video, ASCII becomes useless once characters such as Ӧ need to be encoded. The Unicode standard supports all the languages in the world, both modern and archaic.  
   
To work on text processing, you need to know how to handle encoding. For instance, let’s say you are encoding text about Erwin Schrödinger; if you use ASCII encoding, all the ös in the text will be lost. The encoder will not be able to convert the letter to machine language. So, before beginning with text processing, you need to know what kind of encoding the text has and, if required, modify it to another encoding format.

To get a more in-depth understanding of Unicode, you can refer to [this guide](https://docs.python.org/3/howto/unicode.html) available on the official Python website.

To summarise, the following are the two most popular encoding standards:

1. American Standard Code for Information Interchange (ASCII)

2. Unicode

Even Unicode is not a final version of the encoding standard. There are multiple versions of Unicode encoding: UTF-8, UTF-16 and UTF-32. Exploring the details of these encoding techniques is beyond the scope of this module.

UTF-8 offers a big advantage in cases when the character belongs to the English alphabet or the ASCII character set. Let’s look at the relation between ASCII and UTF-8 through an example. The table given below shows the encoding of two symbols on ASCII and UTF-8.  
 

| Character | Binary ASCII | Binary UTF-8      |
| --------- | ------------ | ----------------- |
| $         | 00100100     | 00100100          |
| £         | NA           | 11000010 10100011 |

For all characters present in ASCII encoding, the UTF code and the ASCII codes are the same. The characters that are not present in the ASCII set are encoded in two bytes. As the symbols become rare, such as Greek letters and Chinese characters, the memory allocation of UTF-8 goes on increasing. 

To know more about UTF encoding, you can visit the following links: 

1. [Wiki article explaining the UTF 8 system](https://en.wikipedia.org/wiki/UTF-8) 

2. [Online tool to convert symbols to binary using UTF-8 UTF-16 and UTF-32 encoding.](https://onlineunicodetools.com/convert-unicode-to-binary) 

The code provided below is an example of converting a set of characters from a string to an encoded format, and vice versa. Try this code in your Jupyter Notebook and look at its output. Feel free to change the code and experiment.

```python
# create a string

amount = u"₹50" 
print('Default string: ', amount, '\n', 'Type of string', type(amount), '\n') 

# encode to UTF-8 byte format

amount_encoded = amount.encode('utf-8')
print('Encoded to UTF-8: ', amount_encoded, '\n', 'Type of string', type(amount_encoded), '\n') 

# decode from UTF-8 byte format

amount_decoded = amount_encoded.decode('utf-8') 
print('Decoded from UTF-8: ', amount_decoded, '\n', 'Type of string', type(amount_decoded), '\n')
```

The output of the encode command is shown in what is called [byte string](https://stackoverflow.com/questions/6224052/what-is-the-difference-between-a-string-and-a-byte-string), which is beyond the scope of this module. 

Before moving onto the next segment, attempt the following questions.

#### ASCII System

Qn: How many different characters can be represented in the ASCII encoding system? 

- 64

- 128

- 256

- 512

Ans: B. *Usually, each ASCII character uses 1 byte of memory. However, each ASCII character only uses seven of the eight bits in a byte, so all ASCII encodings are of the form 0xxxxxxx. 128 unique characters can be made in this form.*

#### Encoding text

Qn: Use the UTF-8 encoding to encode ‘©’.

You can use a Jupyter Notebook. All standard encoding is already built-in Python 3. 

- `b'\xe2\x82\xb9'`

- `b'\xc2\xa9'`

- `b’©’`

- `b’\x000\x00’`

Ans: B. *The following code can be used to encode the given character.*

```python
char_test = "©"
char_test _encoded = char_test ('utf-8')
char_test _encoded
```


#### Decoding Text

Qn: Use the UTF-8 encoding to decode `b'\xe2\x82\xb9'`.

You can use a Jupyter Notebook. All standard encoding is already built-in Python 3.   
 
- ₹

- ©

- `b’\x000\x00’`

- $

Ans: A. *The following code can be used to decode the given encoded character.*

```python
code = b'\xe2\x82\xb9'
code.decode('utf-8')
```

In the next segment, you will learn how to deal with more inconsistencies related to case, punctuation, symbols, etc.
