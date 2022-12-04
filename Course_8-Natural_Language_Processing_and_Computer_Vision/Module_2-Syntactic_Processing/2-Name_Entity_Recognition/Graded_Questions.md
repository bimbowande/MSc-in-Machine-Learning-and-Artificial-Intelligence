# Graded Questions

You have been given the following text corpus of the stock market data. In this, various prices have been mentioned in different situations as well as the time for a particular stock of a company. The price written in this text is in dollars ($). 

Download [Dataset](data.txt)

#### Graded Question

Qn: Based on the given data set, what will be the average price value of the stock from the text corpus? Hint: Find the name entity related to money and then perform the average operation on all the MONEY entity type.  
 
- 99.10

- 89.32

- 93.26

- 95.12

Ans: C. *Find the name entity corresponding to MONEY and then perform an average operation after computing the summation of all the values of money.*

```python
import spacy # import spacy module
model = spacy.load("en_core_web_sm") #load pre-trained model
## Read the file in variable name ‘doc’

processed_doc = model(doc); #process input and perform NLP tasks
a=0
c=0
for ent in processed_doc.ents:
  if ent.label_ == 'MONEY':
    c= c+1
    b = ent.text 
    a = a+ int(b)

print(a/c)
```

Qn: What is the date name entity in this text corpus?

- a year later

- a year ago

- past 10 years

- previous year

Ans: B. *Get all the DATE type entities and check if it is ‘a year ago’ or any other.*

```python
import spacy # import spacy module
model = spacy.load("en_core_web_sm") #load pre-trained model
## Read the file in variable name ‘doc’
 
processed_doc = model(doc); #process input and perform NLP tasks
for ent in processed_doc.ents:
  if ent.label_ == 'DATE':
    print(ent.text)
```

