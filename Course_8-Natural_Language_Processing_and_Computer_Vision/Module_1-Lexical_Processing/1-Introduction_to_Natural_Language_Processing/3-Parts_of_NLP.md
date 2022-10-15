# Parts of NLP

Text processing tools are divided into three broad categories based on their complexity of information extraction. 

## Lexical Processing

Consider the following wiki article You can break it down into smaller segments. 

![Wiki Article](https://i.ibb.co/MP9GDtQ/Wiki-Article.png)

The smallest segment can be a word, a sentence, or even a paragraph. This smallest unit is called a ‘token’. You will learn what guides the choice of the token a little later. Lexical processing focuses on information extraction at the token level. 

In the next video, Dr Balan will give you some examples of lexical processing along with its limitations. 

**VIDEO**

As you saw in the video, lexical processing tools cannot differentiate between sentences that have similar words but different meanings. For instance, both the following sentences will have the same tokens and, hence, both the sentences are the same for lexical processing though they have different meanings.

**Sentence A**: “My cat ate its third meal”.  
**Sentence B**: “My third cat ate its meal”.  
 

## Syntactic Processing

Syntactic processing is where we try to extract more information from the sentence by using its syntax and grammar. Instead of only looking at the words, we look at the grammatical structure of the sentence. 

For instance, consider the word ‘drive’. The word itself has a specific meaning that is ‘to operate a motor vehicle’. However, if you consider a sentence like ‘All the documents can be found in Google Drive’, the word ‘Drive’ is a noun. The upcoming video will give you more examples of syntactic processing. 

**VIDEO**

As you saw in the video, syntactic processing can be used to identify heteronyms, differentiate subject and object in a sentence and find name entities. There can be multiple other situations where the use of grammatical structure can lead to information extraction that cannot be extracted from tokens. 

## Semantic Processing

Lexical and syntactic processing do not suffice when it comes to building advanced NLP applications such as language translation and chatbots. Even after extracting information from tokens themselves and the grammar syntax, some information is still lost. For example, if you ask a question answering system, “Who is the PM of India?”, it may not understand that PM and Prime Minister mean the same thing. It may not even be able to give an answer unless it has a database connecting the PM to the Prime Minister. You could store the answer separately for both the variants of the meaning (PM and Prime Minister), but how many of these meanings are you going to store manually? At some point, your machine should be able to identify synonyms, antonyms, etc., on its own.

In the upcoming video, Dr. Balan will share thoughts about semantic processing. 

**VIDEO**

Once you have the meaning of the words obtained via semantic analysis, you can use it for a variety of applications. Applications like machine translation and chatbots require a complete understanding of the text, right from the lexical level to the understanding of syntax or grammar to that of meaning. 

#### Understanding Text

Qn: Deep learning architectures short-circuit the conventional NLP path. Which stage is entirely eliminated from the three stage process?

- Lexical processing

- Syntactic processing

- Semantic processing

- All of the above

Ans: C. *Deep Learning architecture can complete the NLP path using Syntactic process output which eliminates the need for Semantic processing.*

Qn: Select the correct statement among the following:

- Lexical processing does not have anything to do with the structure or meaning of words in a given sentence.

- Syntactic processing considers the grammatical structure of a given sentence to extract information.

- Semantic processing is concerned with the meaning of the sentence.

- All of the above.

Ans: D. *All the above statements are correct.*

Earlier you saw a few NLP applications, but the fact still remains that since most of the data created on the internet is in the form of text, NLP systems also find a lot of applications.

In the next session, let’s learn the various applications of NLP.