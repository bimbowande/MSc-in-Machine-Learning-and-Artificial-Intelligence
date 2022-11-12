# PoS Tagging Case Study Part - II

In the previous segment, you learnt that when you find the top frequently occurring token as a noun, you get the desired features of the product. Now, you have to perform the next task.

**Task - 7**: You need to extract all the nouns from all of the reviews and look at the top 10 most frequently lemmatised noun forms. You are already aware that it will take too much time to process the entire data set (approximately 13 minutes that we calculated in the previous segment). To reduce the processing time, you can use the following line of code when you load the Spacy model.  You need to use the 'Samsung.txt' file to perform this task.

```python
# shorten the pipeline loading
nlp=spacy.load('en_core_web_sm',disable=['parser','ner'])
```

 In the upcoming video, you will have more clarity on this ‘disable’ function. However, for solving the next question, please use the aforementioned lines of code.

#### EDA

Qn: What is the order of frequency of occurrence of each word as a noun in the whole data set? Hint: Use the following line of code to shorten the pipeline so that you get your result in less time.

```python
# shorten the pipeline loading
nlp=spacy.load('en_core_web_sm',disable=['parser','ner'])
```

1.  screen
2.  phone
3.  battery
4.  product
5.  time

- 2, 3, 4, 5, 1 

- 1, 2, 3, 4, 5

- 1, 3, 5, 2, 4

- 5, 4, 1, 2, 3

Ans: A. *Let’s perform the following lines of code:*

```python
nouns = []
for review in tqdm(samsung_reviews.split("\n")):
    doc = nlp(review)
    for tok in doc:
        if tok.pos_=="NOUN":
            nouns.append(tok.lemma_.lower())

nouns=pd.Series(nouns)
nouns.value_counts().head(5)
```

Let’s look into the next video to understand the steps that you have performed in the previous section.

**VIDEO**

In the video, Gunnvant has used the following lines of code to reduce the processing time:

```python
# shorten the pipeline loading
nlp=spacy.load('en_core_web_sm',disable=['parser','ner'])
```

When you load the Spacy using ‘en-core_web_sm’, the system finds everything like PoS tags, parsing dependencies, pre-built NER, lemmatised forms and so on. When you disable the ‘parser’ and ‘ner’, you are actually telling the system to not perform these tasks which eventually reduces the time to process the data set. As you can see, the time to process the entire data set was calculated as approximately 13 minutes earlier. However, in this case, the total time to process the entire data set is 4.6 minutes only.

Let’s summarise the video:

-   Now, we know that people mention battery, product, screen, etc. However, we still do not know in what context they mention these keywords.
-   The most frequently used lemmatized forms of nouns inform us about the product features people are talking about in product reviews.
-   In order to process the review data faster, Spacy allows us to use the idea of enabling parts of the model inference pipeline via the spacy.loads() command and the disable parameter.

Now, let’s come to a very interesting exercise. You have been able to identify the keywords or features such as ‘battery’, ‘screen’ and ‘phone’. Now, let’s try to see in what context these keywords occur using the following examples:

-   Good battery life
-   Big screen size
-   Large screen protector
-   Long battery lasts

In these examples, you can see that the keyword ‘battery’ occurs in the context of ‘good battery life’ or ‘screen’ occurs in the context of ‘big screen size’ and so on.
  
Can we use Regex to find the context in which the keywords occur?

Let's watch the next video and understand how you can separate out the prefixes and suffixes for a given keyword

**VIDEO**

So, you have learnt to get the most appropriate combination of keywords and its prefixes and suffixes after eliminating the stop words in the above video. 

You have now completed this case study. With this, you have also completed the session on PoS tagging.