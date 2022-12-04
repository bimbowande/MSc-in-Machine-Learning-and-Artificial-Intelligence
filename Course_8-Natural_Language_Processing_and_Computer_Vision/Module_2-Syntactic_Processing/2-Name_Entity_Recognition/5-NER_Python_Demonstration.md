# NER: Python Demonstration

In previous segments, we covered the theory part of named entity recognition. You learnt about named entity types, the benefits of NER tagging over PoS tagging and IOB tags. Before we discuss how a machine learning model can be trained to do NER, let us first look at a practical application of NER.

We will use the python library spacy, which comes pre-built with NER tagger.

The well-commented notebook used in the next couple of videos which you can download from the below link. We strongly recommend you to write the code as you watch the videos for a better understanding.

**VIDEO**

Download [NER Code Notebooks](NER_Code_Demonstration.zip)

As you saw in the video, to understand the query, a search engine first tries to find the named entity used in the query, and then corresponding to that entity, it displays the appropriate searches to the user. Named entity recognition is one of the aspects of the search engine mechanism.

You obtained PoS tags of the following sentence:

‘Sumit[PROPN] is[AUX] an[DET] adjunct[ADJ] faculty[NOUN] at[ADP] UpGrad[PROPN].’ 

However, PoS tagging failed to distinguish between ‘Sumit’ and ‘UpGrad'. 

According to PoS tagging, both ‘Sumit’ and ‘UpGrad’ are proper nouns. In the next video, you will see how NER is able to differentiate between ‘Sumit’ and ‘UpGrad’.

**VIDEO**

Note: At the timestamp 3:10, Sumit mistakenly says ‘Pronoun’ instead of ‘Proper noun’.

Like PoS tagging, you can also find the named entities present in a sentence using the following code:

```python
import spacy # import spacy module
model = spacy.load("en_core_web_sm") #load pre-trained model
doc = "Any sentence"
 
processed_doc = model(doc); #process input and perform NLP tasks
for ent in processed_doc.ents:
  print(ent.text, " -- ", ent.start_char, " -- ", ent.end_char, " -- ", ent.label_)
```

   
After processing the model over ‘doc’, we got ‘processed_doc’, which contains an attribute called ‘ents’, which contains all the entities that identify with the Spacy NER system. So, the code above iterates over every token of the sentence and provides the corresponding entity associated with that token that was identified by the Spacy-trained model.  
   
You might have also noticed that the entity types of ‘Sumit’ and Upgrad in the following two sentences are different  
   
*‘Sumit is an adjunct faculty of Upgrad[GPE].’*  
   
*‘Dr. Sumit[PERSON] is an adjunct faculty of Upgrad[ORG]’*  
   
In the second sentence, the model successfully finds both the entities, but in the first sentence, it fails to identify ‘Sumit’. The reason for this could be that ‘Sumit’ is not present in the corpus on which the model was trained. However, adding ‘Dr’ as a prefix indicates the model that the next word is a person. Based on these observations, we can conclude that there are various situations where systems make errors  depending on the application.  
   
Let’s now consider a practical application of NER systems. 
  
**Anonymisation of data and redacting personally-identifying information**

In many scenarios, we would want to withhold sensitive and confidential information such as names of persons, dates and amounts. 

Suppose you are asked to write a program that can anonymise people’s names in many emails for confidential purposes.  
For this task, we can use NER techniques to automatically identify PERSONS in the text and remove PERSON names from the text.  
   
Let’s watch the next video to learn how this can be done based on your learnings so far. Note: we will take the example of emails from the Enron email data set for illustration in this demo.  
   
- [Email source](http://www.enron-mail.com/email/lay-k/elizabeth/Christmas_in_Aspen_4.html)  
- [Complete Enron data](http://www.enron-mail.com/)

**VIDEO**

In the above video, we first identified the person’s name in the email using _‘ent.label== ‘PERSON’_. We then replaced the character of a person’s name with ‘*’ to make it anonymous. Now, based on this anonymisation example, answer the following questions  
 
#### NER

Qn: Suppose you are given the following message, and you want to hide the dates mentioned in this message. In order to hide the dates, you replace them with the ‘#’ symbol whenever a date appears.

**Message**: 

*‘Dear Family,  
Jose Luis and I have changed our dates, we are going to come to Aspen on the 23rd of December and leave onthe 30th of December. We would like to stay in the front bedroom of the Aspen Cottage so that Mark Natalie and Zachary can stay in the guest cottage.  
Please let me know if there are any problems with this. If I do not hear anything, I will assume this is all o.k. with you.  
Love,  
Liz ’*

**Program**:

```python
import spacy # import spacy module
             model = spacy.load("en_core_web_sm") #load pre-trained model
email = ('Dear Family, Jose Luis and I have changed our dates, we are '
         'going to come to Aspen on the 23rd of December and leave on the '
         '30th of December. We would like to stay in the front bedroom of '
         'the Aspen Cottage so that Mark, Natalie and Zachary can stay in '
         'the guest cottage. Please let me know if there are any problems '
         'with this. If I do not hear anything, I will assume this is all '
         'o.k. with you.'
         'Love, Liz')
processed_email = model(email) # Apply spacy's model to process the email
 
anonymized_email = list(email) # initialize data structure to store anonymized email
 
/* write the code here*/     
 
print("\n\n-- After Anonymization--\n")
Anonymized_sentence = "".join(anonymized_email)
print(Anonymized_sentence)
```

   
Which of the following code snippets would complete the program?

- 
```python
for ent in processed_email:
  if(ent.label_ == 'DATE'): 
    for char_pos in range(ent.start_char, ent.end_char): # use character positions
      anonymized_email[char_pos] = '#'
```

- 
```python
for ent in processed_email.ents:
  if(ent.label_ == 'DATE'): 
    for char_pos in range(ent.start_char, ent.end_char): # use character positions
      anonymized_email[char_pos] = '#'
```

- 
```python
for ent in processed_email.ents:
  if(ent.label_ == 'EVENT'): 
    for char_pos in range(ent.start, ent.end): # use character positions
      anonymized_email[char_pos] = '#'
```

- 
```
for ent in processed_email.ents:
  if(ent.label_ == 'EVENT'): 
    for char_pos in range(ent.start_char, ent.end_char): # use character positions
      anonymized_email[char_pos] = '#'
```

Ans: B. *This code would complete the program.*

Qn: Considering we are using the Spacy library, which of the following code snippets would identify the entities in the given sentence?

*‘Mr. Kenneth L. Lay, Chairman and CEO of Enron Corp. will not be able to  
attend the November 16 - 17, 2000 6th Olympiad of the Mind.’  *
 
- 
```python
import spacy # import spacy module
model = spacy.load("en_core_web_sm") #load pre-trained model
doc3 = "Mr. Kenneth L. Lay, Chairman and CEO of Enron Corp. will not be             able to attend November 16,"
processed_doc3 = model(doc3)
for ent in processed_doc3:
  print(ent.text, " -- ", ent.start_char, " -- ", ent.end_char, " -- ", ent.label_)
```

- 
```python
import spacy # import spacy module
model = spacy.load("en_core_web_sm") #load pre-trained model
doc3 = "Mr. Kenneth L. Lay, Chairman and CEO of Enron Corp. will not be             able to attend November 16,"
processed_doc3 = model(doc3)
for ent in processed_doc3.ents:
  print(ent.text, " -- ", ent.start_char, " -- ", ent.end_char, " -- ", ent.label_)
```
 
- 
```python
import spacy # import spacy module
model = spacy.load("en_core_web_sm") #load pre-trained model
doc3 = "Mr. Kenneth L. Lay, Chairman and CEO of Enron Corp. will not be             able to attend November 16,"
processed_doc3 = doc3
for ent in processed_doc3:
  print(ent.text, " -- ", ent.start_char, " -- ", ent.end_char, " -- ", ent.label_)
```

Ans: B. *This code will identify the entities in the sentence.*
