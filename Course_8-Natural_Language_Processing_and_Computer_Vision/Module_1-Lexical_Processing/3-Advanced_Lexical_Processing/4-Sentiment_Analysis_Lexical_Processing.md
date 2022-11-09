# Sentiment Analysis: Lexical Processing

Now, let’s combine all the different techniques you have learnt and implement them on a real-life dataset. In the next video, Mahesh will give an overview of the tasks that will be performed in the case study. You can find the code file for the case study attached below and the data set can be downloaded from the below. 

Download IMDB dataset from [Google Drive](https://drive.google.com/file/d/17YU_zWVuZ7wRqY9jXcWuoYA5WzwQHOJC/view?usp=sharing) or [Local](IMDB_Dataset.csv.zip)

Download [IMDB Case Study Notebook](Lexical_Processing_IMDb_Reviews.ipynb)

**VIDEO**

As Mahesh explained, the sentiment analysis model will be developed using the same process as a typical text analytics model. 

1.  Text cleaning 
   
2.  Feature extraction 
   
3.  Model building 

In this case study, Mahesh will build the model using both feature extraction methods you have studied: BoW and TFIDF. It will prove useful for comparing the results of both the models. It is also noteworthy that the model will use a normal logistic regression algorithm.  

Now, let’s read the data and understand it better in the upcoming video.

**VIDEO**

As shown in the video, the necessary libraries and the dataset were imported. The IMDB data has only two columns: one is the review itself and the other is the label of the sentiment, that is, positive or negative, corresponding to each review. You also saw certain peculiarities in the reviews, such as in the second review, as shown in the image given below. 

In the upcoming video, the basic lexical processing techniques will be performed on the IMDB data. 

**VIDEO**

The function shown in this video was the first step in text cleaning. The denoise_text function comprises all the basic techniques, such as removing HTML tags, removing emojis, using text encoding to deal with special characters and removing text with square brackets. The code used in the demonstration is given below. 

```python
#Collating all functions together and applying them for the 'IMDb reviews' dataset
def strip_html(text):
    soup = BeautifulSoup(text, "html.parser")
    return soup.get_text()
 
#Removing emojis
def deEmojify(text):
    regrex_pattern = re.compile(pattern = "["
        u"\U0001F600-\U0001F64F"  # emoticons
        u"\U0001F300-\U0001F5FF"  # symbols & pictographs
        u"\U0001F680-\U0001F6FF"  # transport & map symbols                                                                         
        u"\U0001F1E0-\U0001F1FF"  # flags (iOS)
                           "]+", flags = re.UNICODE)
    return regrex_pattern.sub(r'',text)
 
#Text-encoding: UTF-8 encoder
def to_unicode(text):
    if isinstance(text, float):
        text = str(text)
    if isinstance(text, int):
        text = str(text)
    if not isinstance(text, str):
        text = text.decode('utf-8', 'ignore')
    return text
 
#Removing the square brackets
def remove_between_square_brackets(text):
    return re.sub('\[[^]]*\]', '', text)
 
 
#Define function for removing special characters
def remove_special_characters(text, remove_digits=True):
    pattern=r'[^a-zA-z0-9\s]'
    text=re.sub(pattern,'',text)
    return text
 
#Removing the noisy text
def denoise_text(text):
    text = to_unicode(text)
    text = strip_html(text)
    text = re.sub(r"http\S+", "", text)
    text = deEmojify(text)
    text = text.encode('ascii', 'ignore')
    text = to_unicode(text)
    text = remove_between_square_brackets(text)
    text = remove_special_characters(text)
    text = text.lower()
    return text
```

You are already familiar with this code, as it is the same code used for the Zomato case study. 

#### Text Processing

Qn: Consider the text corpus given below.

"The Indian rupee (symbol: ₹; code: INR) is the official currency of India. The rupee is subdivided into 100 paise (singular: paisa), though as of 2019, coins of denomination of 1 rupee is the lowest value in use. The issuance of the currency is controlled by the Reserve Bank of India." 

If this text is processed through the denoise_text function discussed earlier in this segment, the symbol ‘₹’ would ______ in the processed text. 

- be removed 

- Remain as is

- Get converted into unicode

- Cannot predict the outcome 

Ans: A. *The ASCII text encoding used in the denoise_text function does not recognise the ‘₹’ character, and hence, it will be removed.*

#### Text Encoding

Qn: Use the internet to find a pictorial representation of the emoji U0001F600. 

- 😁

- 😀

- 😂

- 😆

Ans: B. *Each emoji has a specific Unicode attached to it. They can be easily found on the Google search engine. By choosing the right Unicode to filter out, you can create a custom filter to keep certain emojis and remove the others.*

Now, let’s use advanced lexical techniques, such as stopword removal, stemming and lemmatisation. 

**VIDEO**

So, now the stop words have been removed from the IMDB text data. Note that the code, the tools and the techniques are exactly the same as those used in the Zomato review case study. 

Next, let’s use stemming and lemmatisation on the dataset. In the upcoming video, Mahesh will demonstrate these techniques. 

**VIDEO**

Again, the code used in the demo is almost similar to that used in the Zomato review case study. 

However, there are a few points to highlight. Given below is the first review in the database without stemming or lemmatisation.

```
wonderful little production filming technique unassuming oldtimebbc fashion gives comforting sometimes discomforting sense realism entire piece actors extremely well chosen michael sheen got polari voices pat truly see seamless editing guided references williams diary entries well worth watching terrificly written performed piece masterful production one great masters comedy life realism really comes home little things fantasy guard rather use traditional dream techniques remains solid disappears plays knowledge senses particularly scenes concerning orton halliwell sets particularly flat halliwells murals decorating every surface terribly well done
```

Output of stemming

```
CPU times: user 2.19 ms, sys: 0 ns, total: 2.19 ms  
Wall time: 2.3 ms  
wonder littl product film techniqu unassum oldtimebbc fashion give comfort sometim discomfort sens realism entir piec actor extrem well chosen michael sheen got polari voic pat truli see seamless edit guid refer william diari entri well worth watch terrif written perform piec master product one great master comedi life realism realli come home littl thing fantasi guard rather use tradit dream techniqu remain solid disappear play knowledg sens particular scene concern orton halliwel set particular flat halliwel mural decor everi surfac terribl well done
```

Output of lemmatisation 

```
CPU times: user 9.99 ms, sys: 1.01 ms, total: 11 ms  
Wall time: 10.9 ms  
wonderful little production film technique unassuming oldtimebbc fashion give comfort sometimes discomforting sense realism entire piece actor extremely well choose michael sheen get polari voice pat truly see seamless edit guided reference williams diary entry well worth watch terrificly write perform piece masterful production one great master comedy life realism really come home little thing fantasy guard rather use traditional dream technique remain solid disappears play knowledge sens particularly scene concern orton halliwell set particularly flat halliwells mural decorate every surface terribly well do
```

**Diffrence between the computation effort in stemming and lemmatisation** 

Time taken by the Snowball stemmer to stem all the words in this review is about 2.19 ms. Whereas, the time taken by the WordNet lemmatizer to find the lemma for all the words in the same review is 9.99 sec. All the other variables, such as the performance of the machine, are the same in both cases. The change in the execution time is only attributed to the fact that lemmatisation needs more computation than stemming. 

Apart from the execution time, observe the words in the output of stemmer and lemmatizer. Stemmer produces incomplete words, whereas lemmatizer produces complete words. 

The decision to use a stemmer or a lemmatizer is based on the computational resources available. If enough computational resources are available, a lemmatizer is preferred, and if the text corpus is extremely large and the resources are not enough, then a stemmer is preferred.   

#### Stemming and Lemmatization

Qn: Consider the Covid-19 Open Research Dataset (CORD-19). It comprises about 500,000 research articles on coronavirus. The dataset is made available publicly to encourage the global community to find new insights using natural language processing (NLP) and AI techniques. 

Which technique (stemming or lemmatisation) would you use to process the CORD-19 data?   
 
Ans: *The choice between stemming and lemmatisation is governed by the availability of computational resources and time. If you have a huge amount of cloud resources with GPUs and parallel computing resources, use lemmatisation. More realistically, for a dataset of this size, stemming must be preferred.*
