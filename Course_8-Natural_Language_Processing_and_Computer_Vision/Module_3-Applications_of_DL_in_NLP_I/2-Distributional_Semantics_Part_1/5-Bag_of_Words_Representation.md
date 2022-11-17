# Bag of Words Representation

In the previous module on lexical processing, you learnt about frequency-based methods such as TfiDf or the bag-of-words approach for creating word vectors.

Let us revise the bag of words representation of creating word vectors.

**VIDEO**

Bag of Words is a representation of text that describes the occurrence of words within a corpus of text, treating each word independently.

  
For example, the following text extract from A Tale of Two Cities authored by Charles Dickens can be converted into a bag-of-words representation: 

_“It was the best of times,_

_it was the worst of times._

_It was the age of wisdom,_

_it was the age of foolishness._

_It was the season of Light,_

_it was the season of Darkness._

_It was the spring of hope,_

_it was the winter of despair”_

![Bag-of-Words Representation](https://i.ibb.co/G3VYkSm/Bag-of-Words-Representation.png)

The above table represents the one-hot encoded vector for the text extract. If a word is present in the sentence, a value of ‘1’ is assigned; otherwise, ‘0’ is assigned.

Note that attention is not given to the meaning, sequence or context of the words in this representation. In the next video, Jaidev will discuss the limitations of this technique.

**VIDEO**

To understand the relationship between words, cosine similarity can be applied on the one-hot encoded representation of this text corpus. For example, on taking the words ‘best’ and ‘worst’ as shown below and applying cosine similarity, we get 0. This means that the words are completely unrelated.

![Cosine Similarity Example Best Worst](https://i.ibb.co/74jd1rb/Cosine-Similarity-Example-Best-Worst.png)**

$$S=cos(x,y)=\dfrac{x.y}{||x||||y||}$$

$$S(best,~worst)=\dfrac{0}{1X1}=0$$

However, ‘best’ and ‘worst’ are antonyms, and their cosine similarity should be negative as you learnt earlier. 

Similarly:

S(wisdom, foolishness) = 0

S(wisdom, winter) = 0

S(winter,light) = 0

S(winter, season) = 0

S(spring, season) = 0

The cosine similarity for unrelated words, related words and antonyms is zero. 

This proves that the bag-of-words representation is not the most accurate way to convert words into its vectors. The vectors captured by Bag of Words do not capture the meaning of words. 

#### Bag of Words

Qn: Why does the Bag-of-Words (BoW) representation of word vectors fail to capture the meaning of words?

- Word vectors based on BoW only depend on the frequency of the occurrence of words, not on the context in which they occur.

- Word vectors based on BoW capture the context in which a word occurs.

Ans: A. *Context is necessary to understand the meaning of words.*

Let us summarise what we have learnt in the next segment.