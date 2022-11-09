# Dealing With Inconsistent Text

User generated text like reviews, tweets even some blogs and articles have many insconsistances. Some of which you will learn to handle in this segment. 

In this segment, you will learn about: 

1.  Converting text to a uniform case (lowercase),
    
2.  Removing symbols and punctuations from text, and 
    
3.  Handling numbers in text. 
    

Programmatically speaking, handling these three tasks is quite similar; therefore, we club them together. In the next video, Dr Balan will speak about sanitising text.

**VIDEO**

In this video, you saw the transformation of a Zomato review as it was passed through the different steps mentioned earlier. 

#### Case Standardisation

Why is it important to convert the complete text corpus to lower case? 

Note that lower case is not an absolute necessity; even if you convert the complete corpus to upper case, it will serve the same purpose. The objective of case conversion is to reduce variation in encoding. Earlier, you learnt that the binary versions of A and a are different regardless of the  encoding technique being used. However, from a lingual perspective, A and a are not that different; so, it makes sense that they need to be encoded in similar binary forms. By converting the corpus to  lower case, we ensure that such variation is reduced.   

#### Removal of punctuations and symbols

Next, Mahesh spoke about removing punctuation and symbols. Consider the following sentences: 

1.  I do not particularly like the play Who’s Afraid of Virginia Woolf?
2.  I did not like it even when I worked at Yahoo!
3.  I especially did not like it when I saw it at 5:00 am.

What kind of information is conveyed by ‘?’ and the ‘!’ in these sentences? They convey the tone of the sentence. In a grammatically correct text, such as a research paper or newspaper article, you may want to retain these because they are conveying certain information. On the other hand, take a look at the following comment by a user on YouTube.   
 
![Comment](https://i.ibb.co/GHY57Wc/Comment.png)

The comment is full of unnecessary full stops separating sentence fragments, not complete sentences. In such user-generated content. Punctuation marks do not carry any meaning. Removing the punctuation marks and symbols makes the text cleaner.  

#### Handling numbers in a text

Finally, let’s discuss numbers embedded in text. In user-generated text, numbers perform different functions. They can be used to write words such as gr8 and 4ever. They can also denote quantity, such as ‘I ate 2 pizzas’ and ‘There were 3 different curries on the plate’. And finally, numbers can be included in nouns such as Brooklyn 99 and COVID-19. 

You can either convert all numbers from digits to spellings or keep them as they are. The guiding principle to make this decision is: Redive the variation in encoding and preserve only the relevant information. For instance, consider this sentence:

I bought 5 apples for ₹150, fruits have become quite expensive at this store. 

If you need to build a model to guess the sentiment of the review, are the numbers necessary? The answer is ‘no’. In this case, the negative sentiment is conveyed by words such as ‘expensive’. On the other hand, consider the following text: 
  
‘Due to COVID-19, the 2020 Olympics were suspended.’ 
 
All the digits in this example are relevant, which is why you may want to keep them as they are.  
#### Standardising text

Qn: Consider the following tweet. 

![Tweet Example](https://i.ibb.co/TcMYZSR/Standardising-Text.png)

Assume that you want to build a sentiment classification model. Which of the following processing techniques will you perform on this text to convert it to standard text? (Note: More than one option may be correct.)

- Text encoding

- Convert to lower case 

- Removing symbols and punctuations 

- Number removal

Ans: All of the above.

- *You can use text encoding to remove emojis from the text. Although these emojis are used as replacements for words and they do have certain information, for the purpose of sentiment analysis, they can be removed.*

- *This tweet has a mix of cases. It is a good idea to convert all the text to one standard case.*

- *Symbols that do not hold a lot of information can be removed.*

- *The numbers in this case convey information about the success of Kane Williamson, but the sentiment is contained in words (phrases) such as ‘loves to play under pressure'*

#### Handling Emojis

Qn: Consider the following tweet.

![Tweet Example](https://i.ibb.co/TcMYZSR/Standardising-Text.png)

Suppose you need to convert these emojis into the words that they represent. Which of the following would be a way to achieve that? 

- Use ASCII encoding to process the text

- Use of regex to identify the emoji and then replace it

Ans: B. *You can create a custom regex pattern to match with specific emojis and then replace the emoji with its corresponding word.*

You will learn how to perform these tasks in a Jupyter Notebook later in this session. For now, let’s continue learning about text preprocessing.