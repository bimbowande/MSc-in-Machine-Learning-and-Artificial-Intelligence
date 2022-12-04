# PoS Tagging Case Study - l

In the previous segment, you learnt to identify the PoS tags of each token in a given sentence using the Spacy library. 

Now, let’s come to a very interesting case study using PoS tagging. Here, we will provide you with the problem statement and some hints to produce output of each step involved to solve the case study. Once you are able to get the answer, we have solution videos which you can refer to after performing each step by yourself.

Please note that this is not a graded case study, but we recommend you solve this as a business use case to learn more about PoS tagging.

Let’s understand the problem statement first.

You have used this feature of Amazon many times before buying any product from the website where you look into the reviews of the product category-wise. Let’s look at the following.

![Amazon Customer Reviews](https://i.ibb.co/VHMGcQb/Amazon-Customer-Reviews.png)

  
The image is the Amazon page of Apple iPhone 12 Mini mobile phone. As you can see, there is categorisation of reviews into features based on the reviews’ text submitted by the users. These features can be **‘battery life’**, **‘value for money’**, **‘screen size’** and so on. 

It is interesting to know that these features have been created to categorise the reviews after looking into the reviews’ text given by multiple users. So, when you click on let’s say **‘battery life’**, you will get all the reviews related to the battery life of this phone.

Please note that in this case study, we are not going to segregate or categorise the reviews, but we are going to find out the top product features that people are talking about in their reviews.

The categorisation of reviews among the product features is just a task to assign each review to its category which can be done using simple coding steps once the main NLP steps are done. 

Can we find out the top product features that people are talking about in their reviews using the PoS tagging method? Let’s first listen to Gunnvant in the next video.

**VIDEO**

So, you are now clear about what you need to do in this case study. 

Please note that as this use case is not a graded component and is designed to be solved as a case study, you have been provided with the data set and the well-commented codes to solve it.

**We made this case study for your hands-on practice as you are well aware of Python now. Though it is not at all mandatory to solve each of the problems; you can watch the videos directly and then think about the questions.** 

You have been given the following link where you can find all the notebooks to write your code:

Download [POS Tagging Case Study](POS_Tagging_Case_Study.zip)

**Task - 1**: Let’s first find out the PoS tags of each token in the following sentences and observe the PoS tags of the words ‘screen’, ‘battery’ and ‘speaker’.

sent1 = "I loved the screen on this phone".  
sent2 = "The battery life on this phone is great".  
sent3 = "The speakers are pathetic".

You have an understanding of getting the PoS tags from the previous segments and can write the code to get the PoS tag of each token for these three sentences. Now, based on the output that you get after having the PoS tags, please answer the following question.

#### PoS tagging

Qn: What will be the PoS tags of the words ‘screen’, ‘battery’ and ‘speaker’ in the following sentences?

sent1 = "I loved the screen on this phone".  
sent2 = "The battery life on this phone is great".  
sent3 = "The speakers are pathetic".

- All three words are tagged as verbs.

- All three words are tagged as nouns.

- All three words have different PoS tags.

- None of the above.

Ans: B. *This is the correct option.*

```python
import spacy 
nlp = spacy.load("en_core_web_sm")

doc1 = nlp(sent1)
for tok in doc1:
    print(tok.text,tok.pos_)
```

*And same for all three sentences.*

You observe that the product features such as screen, battery and speaker have a PoS tag of a noun.

Let’s understand this in the next video.

**VIDEO**

An important thing to note here is that suppose we are able to find the frequency count of all the nouns in our data set, then by looking at top-n nouns, we can find out what product features people are talking about.

You have been given a Samsung phone reviews data set with file name ‘Samsung.txt’ file in the above given link. It contains the reviews about the phone. This data set is a txt file, and each review is in a new line. In the notebook, you have been given the code to load the data set into the notebook. 

**Task - 3**: In this task, you need to calculate the total number of reviews in the data set where each review is in a new line. Let’s solve the next question based on the defined task. You need to use the 'Samsung.txt' file to perform this task.  

#### EDA

Qn: How many reviews does the data set have?   
Hint: Each review is in a new line, so you can use the ‘split’ function with “\n”.   
 
- 45233

- 46340

- 46355

- Cannot be determined

Ans: C. *As each row is a new review, you can use the following lines of code:*

```python
len(samsung_reviews.split("\n"))
```

In the next part, you need to check whether the hypothesis, i.e., the product features that we are trying to extract are acting as nouns in the real-life data set such as ‘Samsung.txt’. But before that, let’s first try to understand why lemmatization of words is needed before extracting the nouns from the data set.  
 
**Task - 4**: In this task, you need to identify the right approach before extracting the nouns from the data set. You need to use the 'Samsung.txt' file to perform this task.

#### PoS tag

Qn: What will be the correct order of steps before extracting the noun PoS tags from the data set.

- Directly extract the most frequent noun PoS tags from the data set. 

- Calculate the PoS tags of each token and then convert them into their lemma form so that each word comes into their root form. Now, once you find the lemma form of each token, count the frequency of each word which has a noun PoS tag. 

- First remove the stop words, then lemmatise the reviews and extract the most frequent noun PoS tags from the data set. 

Ans: B.

So, you can see that there are many nouns in the review text but all of them are not at all relevant to identify the features. So, what should be the approach to get relevant nouns from the review text?

Let’s follow the approach that first calculates the PoS tags of each token and then converts them into their lemma form so that each word turns into its root form. Now, once you find the lemma form of each token, you need to count the frequency of each word which is acting as a noun.

  
**Task-5:**  You need to calculate the frequency of each noun after performing the lemmatization in the first review of the data set and arrange them in the descending order of their frequency of occurrence as a noun. You need to use the 'Samsung.txt' file to perform this task.

#### Noun Tag

Qn: Which of the tokens occurs most frequently as a noun in the first review of the data set?  
Hint: You need to get the most frequent lemma form of the nouns in the first review of the data set. You can use the following line of code to get the lemma form each word and its PoS tag:  

```python
# Convert each token into its lemma and identify the PoS tags.
pos = []
lemma = []
text = []
for tok in review1:
    pos.append(tok.pos_)
    lemma.append(tok.lemma_)
    text.append(tok.text)
 
# Convert the data into a dataframe object.
nlp_table = pd.DataFrame({'text':text,'lemma':lemma,'pos':pos})
nlp_table.head()
```

- honesty

- battery

- year

- phone

Ans: D. *First, calculate the PoS tags of each token and then convert them into their lemma form. Now, you need to count lemma forms which are acting as a noun in the first review’s text.*

```python
# Convert each token into its lemma and identify the PoS tags.
pos = []
lemma = []
text = []
for tok in review1:
    pos.append(tok.pos_)
    lemma.append(tok.lemma_)
    text.append(tok.text)

# Convert the data into a dataframe object.
nlp_table = pd.DataFrame({'text':text,'lemma':lemma,'pos':pos})
nlp_table.head()

#Get most frequent lemma forms of nouns
nlp_table[nlp_table['pos']=='NOUN']['lemma'].value_counts()
```

So, as you can see, when you restrict yourself to the top occurring noun, you can get the desired result. Now, let’s calculate the frequency of occurrence of nouns for each token in the first 1,000 reviews of the data set. 

**Task - 6**: Let’s extract all the nouns from the reviews (first 1,000 reviews) and look at the top five most frequently lemmatised noun forms. You need to use the 'Samsung.txt' file to perform this task.

#### EDA

Qn: What is the order of the frequency of occurrence of each word as a noun (after you have got the lemma form of each word) in the first 1,000 reviews of the data set?

1.  screen
2.  phone
3.  battery
4.  price
5.  time  

- 2, 3, 5, 4, 1

- 1, 2, 3, 4, 5

- 1, 3, 5, 2, 4 

- 5, 4, 1, 2, 3

Ans: A. *You need to apply the same function on 1,000 reviews as follows:*

```python
from tqdm import tqdm
nouns = []
for review in tqdm(samsung_reviews.split("\n")[0:1000]):
    doc = nlp(review)
    for tok in doc:
        if tok.pos_=="NOUN":
            nouns.append(tok.lemma_.lower())
pd.Series(nouns).value_counts().head(5)
```

*Here, the tqdm library is used to decrease the time to process the data. You will learn more about the tqdm library in the upcoming videos.*

Now, let’s look into the following video for a better understanding of all the steps that you have performed.

**VIDEO**

You learnt that the top frequently occurring noun PoS tags can work as product features. 

In the video, Gunnvant has used the ‘**tqdm**’ library to track the time of the processing of 1,000 reviews. You have seen that to process the first 1,000 reviews, it takes 17 seconds and, hence, to process the entire data set, it will take around 782 seconds which is approximately 13 minutes.

In the next segment, you will learn to optimise this time and will create more features from the users’ reviews for the given product.