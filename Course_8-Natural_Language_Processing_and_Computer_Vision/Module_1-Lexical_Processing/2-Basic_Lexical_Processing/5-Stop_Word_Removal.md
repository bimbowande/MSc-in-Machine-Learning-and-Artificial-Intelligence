# Stop Word Removal

Consider any text corpus that is made of paragraphs, sentences and words. Some words are present for grammatical accuracy. Words such as ‘is’, ‘an’ and ‘the’ are mostly used to form meaningful sentences. Such words are called stop words. In the video given below, Mahesh will explain the different kinds of groups into which words can be classified. 

**VIDEO**

As you saw in this video, any text corpus contains three kinds of words:

-   Highly frequent words called stop words, such as ‘is’, ‘an’ and ‘the’
    
-   Significant words, which are typically more important than the others to understand the text
    
-   Rarely occurring words, which are less important than significant words
    

For example, consider the text given below. The words in red stop words, those in blue are significant words, and the ones in green are rare.

![Stop Significant Rare Words Example](https://images.upgrad.com/89c16995-1cd7-4305-94de-b9b1edff4d3a-24.png)

Generally speaking, stop words are removed from the text for two reasons:

1.  They provide no useful information, especially in applications such as spam detectors or search engines. Therefore, you are going to remove stopwords from the spam data set. 
    
2.  Since the frequency of stop words is quite high, removing them significantly reduces the data size, which results in faster computation on text data and also reduces the number of features to deal with.
    

However, there are exceptions to this. In the next module, you will learn concepts such as POS (parts of speech) tagging and parsing, where stopwords are preserved because they provide meaningful (grammatical) information in those applications. Generally, stop words are removed unless they prove to be helpful in your application or analysis.

The most basic statistical analysis that you can do is to look at the **word frequency distribution**, i.e., visualising the word frequencies of a given text corpus. It turns out that you can see a common pattern when you plot word frequencies in a fairly large corpus of text, such as a corpus of news articles, user reviews, or Wikipedia articles. In the next video, Dr Balan will demonstrate some interesting insights from word frequency distributions.

**VIDEO**

To summarise this video, [Zipf's law](https://en.wikipedia.org/wiki/Zipf%27s_law) (formulated by linguist-statistician George Zipf) states that the frequency of a word is inversely proportional to the rank of the word, where rank 1 is given to the most frequent word, rank 2 to the second most frequent, and so on. This is also called the **power law distribution**. If you plot the rank of a word versus its frequency of occurrence, you will get a graph as shown below. 

![Power Law Distribution](https://images.upgrad.com/c827ef67-193a-45d9-bc56-5197d577bdb5-25.png)

The word with the highest frequency has the lowest rank; so, a point representing such a word will be closest to the y-axis to the top left. As the rank of a word decreases, its frequency of occurrence also decreases. The nature of the blue line in the graph suggests that the rank of a word and its occurrence frequency are inversely proportional, which leads us to the formula for Zipf’s law as provided below.  
$$\large{f(word)~×~r(word)\sim\\constant}$$

Be warned this is not a mathematically strong relationship, roughly holds in the middle regions of the graph and not to the extremes. This relationship gives an understanding of text distribution more than a mathematical way to formulate it. The following is an extract from a [published article](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4723055/#:~:text=Despite%20being%20a%20paradigm%20of,representatively%20large%20number%20of%20texts.).

_Despite being a paradigm of quantitative linguistics, Zipf’s law for words suffers from three main problems: its formulation is ambiguous, its validity has not been tested rigorously from a statistical point of view, and it has not been confronted to a representatively large number of texts._

Zipf's law helps us form a basic intuition for **stop words**; these are the words with the highest frequencies (or lowest ranks) in the text and are typically of limited 'importance'. By removing the stop words, you make the model less sparse and computationally efficient.

#### Stop words

Qn: Which of the following words is not a stop word in the English language?

- You 

- Was

- Today

- The

Ans: C. *The word ‘today’ is not a stop word.*

#### Word frequency

Qn: If Zipf’s law was to be expressed as follows: 

A x B = constant 

What would A and B refer to?   
 
- A is the number of vowels present in a word.

- A is the frequency of a word.

- B is the length of a word.

- B is the rank of a word.

Ans: B & D. *The frequency of a word appears in the equation. The rank of a word appears in the equation. It is the ordered index of the word in the word list. $f(word)~×~r(word)\sim\\constant$*

#### Stop words

Qn: State whether the following statement is true or false. "Stop words provide useful information in classification problems such as spam detection."

- True

- False

Ans: B. *The statement is false because stop words are not good features to determine whether a message is spam or ham. This fact holds true for any classification problem.*

Now with stop words removed, let’s move onto the next part of text preprocessing, that is, tokenisation.