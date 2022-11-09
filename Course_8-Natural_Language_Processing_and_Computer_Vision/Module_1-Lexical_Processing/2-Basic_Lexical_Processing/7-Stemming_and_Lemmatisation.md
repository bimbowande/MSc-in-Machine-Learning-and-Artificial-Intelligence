# Stemming and Lemmatisation

Let’s recall the preprocessing steps that you have learnt so far. At the beginning, you learnt about ways to reduce variation in encoding by standardising the case, removing punctuation marks, etc., followed by ways to reduce the number of words by removing stop words. 

  
Stemming and lemmatisation are other techniques that reduce the variety of words in a text corpus. Usually, text has a lot of different forms of the same word. Consider the piece of text provided below. 

  
**Person A**: What did you eat for dinner today?   
**Person B**: I ate a pizza. 

  
The word ‘eat’ appears as ‘eat’ and ‘ate’ in the text. Although the information they contain is similar, they are different words. Similarly, a large corpus of words will have many variations of the same words, which results in high computation requirements.  
In the next video, you will learn how stemming tries to deal with this variation of words.

Play Video

3221820

Let’s summarise the stemming process as it was explained in the video.   
Stemming is a rule-based technique that chops off the suffix of a word to get its root form, which is called the ‘stem’. For example, if you use a stemmer to stem the words of the string ‘The driver is racing his boss’ car’, the words ‘driver’ and ‘racing’ will be converted to their root form by just chopping off the suffixes ‘er’ and ‘ing’. So, ‘driver’ will be converted to ‘driv’ and ‘racing’ will be converted to ‘rac’.

  
You might think that the root forms (or stems) do not resemble the root words ‘drive’ and ‘race’. You need not worry about this because the stemmer will convert all the variants of ‘drive’ and ‘racing’ to the same root forms, i.e., it will convert ‘drive’, ‘driving’, etc. to ‘driv’, and ‘race’, ‘racer’, etc. to ‘rac’. Stemming gives us satisfactory results in most cases, but it is not always accurate. Cases where the root form of a word cannot be derived by chopping off the suffix cannot be handled through stemming. In such cases, more sophisticated methods are needed. Later in the segment, you will learn about lemmatisation, which helps solve this issue.    

There are two popular stemmers:

-   **Porter stemmer**: This was developed in 1980 and works only on English words. You can find the detailed rules of this stemmer [here](http://snowball.tartarus.org/algorithms/porter/stemmer.html).
    
-   **Snowball stemmer**: This is a more versatile stemmer that not only works on English words but also on words of other languages such as French, German, Italian, Finnish and Russian. You can learn more about this stemmer [here](http://snowball.tartarus.org/).

## Lemmatisation

A more sophisticated technique to achieve a similar result is lemmatisation. Let’s first hear about lemmatisation from Dr Balan.

Play Video

3221820

As you saw in this video, lemmatisation is a more sophisticated technique (and perhaps more 'intelligent') in the sense that it does not just chop off the suffix of a word. Instead, it takes an input word and searches for its base word by going recursively through all the variations of dictionary words. The base word in this case is called the lemma. Words such as ‘feet’, ‘drove’, ‘arose’ and ‘bought’ cannot be reduced to their correct base form using a stemmer. However, a lemmatiser can reduce them to their correct base form. The most popular lemmatiser is the WordNet lemmatiser, which was created by a team of researchers at Princeton University. You can read more about it [here](https://www.machinelearningplus.com/nlp/lemmatization-examples-python/#wordnetlemmatizer).

  
Nevertheless, you may sometimes find yourself confused as to whether to use a stemmer or a lemmatiser in your application. The following points may help you make this decision:

1.  A stemmer is a rule-based technique and is, hence, much faster than a lemmatiser (which searches the dictionary to look for the lemma of a word). On the other hand, a stemmer typically gives less accurate results than a lemmatiser.
    
2.  A lemmatiser is slower because of the dictionary lookup but gives better results than a stemmer. Note that for a lemmatiser to perform accurately, you need to provide the part-of-speech tag of the input word (noun, verb, adjective, etc.). You will learn about POS tagging in the next session. It should suffice to know that often, there are cases when the POS tagger is quite inaccurate on your text, and that worsens the performance of the lemmatiser as well. In short, you may want to consider a stemmer rather than a lemmatiser if you notice that the POS tagging is inaccurate.
    

In general, you can try both and see which one works better for you. If a stemmer is giving you almost the same results with increased efficiency, then choose a stemmer, else use a lemmatiser.

#### Stemming and Lemmatization

Qn: Which of the following words cannot be reduced to their base form by a stemmer?

- Running

- Better

- Bought

- Washed

Ans: B & C.

- *‘Running’ can be reduced to its base form by chopping off ‘ning’ from the end.*

- *The base form of the word ‘better’ is ‘good’. ‘Better’ cannot be reduced to ‘good’ using a stemmer.*

- *The base form of the word ‘bought’ is ‘buy’. ‘Bought’ cannot be reduced to ‘buy’ using a stemmer.*

- *‘Washed’ can be reduced to its base form by chopping off ‘ed’ from the end.*

#### Lemmatization

Qn: Which of the following options are the correct pairs of the word and its corresponding lemmatized form?

- leaves: leaf

- better: bet

- corpora: corpus

- matrices: matrix

Ans: A, C & D. 

- *'leaf' is the lemmatized form of 'leaves'.*

- *'corpus' is the lemmatized form of ‘corpora’.*

- *‘matrix’ is the lemmatized form of ‘matrices’.*

With that, you have learnt all the fundamental steps in lexical processing. It goes without saying that there are more techniques out there to preprocess text, but these are the most basic ones. In the next segment, let’s apply these preprocessing steps to a real data set.