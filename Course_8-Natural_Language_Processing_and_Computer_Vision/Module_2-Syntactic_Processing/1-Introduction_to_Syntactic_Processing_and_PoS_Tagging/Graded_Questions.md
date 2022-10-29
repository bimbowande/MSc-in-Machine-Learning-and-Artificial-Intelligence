# Graded Questions

In this graded exercise, you are provided with a ‘csv’ file named ‘**tagged_words.csv**’, which contains words and their respective PoS tags in the format given below.  
 
![Tagged Words](https://i.ibb.co/C6GyVfQ/Tagged-Words.png)

Download [Tagged words dataset](tagged_words.csv)

So, you have a PoS-tagged data set, named ‘tagged_words.csv’, which you can consider the training data set. 

You can refer to the link below to understand the PoS tags provided in the data. (Note that the data provided below does not cover all the tag definitions; nevertheless, this link data suffices for the purposes of the exercise.)

[Universal PoS Tags](https://universaldependencies.org/u/pos/)

Now, using this training data set named ‘tagged_words.csv’, you need to create a rule/frequency-based PoS tagger (use the most common PoS tag for a word as the prediction for its PoS tag) to solve the next couple of questions.

#### Graded Question

Qn: Using the rule/frequency-based PoS tagger (which you can build with the training data set provided above), you can find out the PoS tag for each word.  
What will be the PoS tag for the word ‘saw’ in this sentence?

S: “I saw him running away”.

(Ignore the case of the text in the sentence as well as in your training data).  
 

- PRON

- ADV

- VERB

- DT

Ans: C. *You can count the number of times the word ‘saw’ occurs as different PoS tags. The majority tag will be the PoS tag of the word ‘saw’ in this sentence.*

```python
data = pd.read_csv("tagged_words.csv")
sent = "I saw him running away"

def get_common_tag(data,word):
    if word.lower() in data['word'].unique():
        q = f"word=='{word.lower()}'"
        return word , data.query(q)['tag'].value_counts().head(1).index.tolist()[0]
    else:
        return f"{word} not in data"

for word in sent.split(" "):
    print(get_common_tag(data,word))
 
data.query("word=='saw'")['tag'].value_counts()
```

Qn: You can use the rule/frequency-based PoS tagger (which you can build with the training data set provided above) to find out the PoS tag for each word of any sentence.

Now, use this data set to create PoS tags for the sentence “**He wished he was rich**”. (Ignore the case of the words in the sentence as well as in the training data). Match the words in the left column with their PoS tags in the column on the right.  
 
|           |         |
|-----------|---------|
| 1. He     | a. Verb |
| 2. wished | b. ADJ  |
| 3. he     | c. PRON |
| 4. was    | d. NOUN |
| 5. rich   | e. ADP  |

- \[1->c,2->a, 3->c,4->a,5->b\]

- \[1->a,2->d, 3->a,4->c.5-b\]

- \[1->e,2->d, 3->e,4->c.5-b\]

- \[1->b,2->a, 3->b,4->d.5-e\]

Ans: A. *‘He’ occurs the most frequently with a tag of PRON. ‘Wished’ occurs only with the tag VERB in the training data set. ‘was’ occurs only with the tag VERB and ‘rich’ occurs only with the tag ADJ.*

```python
data = pd.read_csv("tagged_words.csv")
s = "He wished he was rich"

def get_common_tag(data,word):
    if word.lower() in data['word'].unique():
        q = f"word=='{word.lower()}'"
        return word , data.query(q)['tag'].value_counts().head(1).index.tolist()[0]
    else:
        return f"{word} not in data"

for word in s.split(" "):
    print(get_common_tag(data,word))
```

Qn: You are already aware of how an emission matrix looks. Now, take a look at this emission matrix.  
 

| WORDS  | POS TAG_1 | POS TAG_2 | POS TAG_3 |
| ------ | --------- | --------- | --------- |
| word_1 | 0.25      | 0.31      | 0.12      |
| word_2 | 0.054     | 0.10      | 0.08      |
| word_3 | 0.15      | 0.09      | 0.32      |
| ...    | ...       | ...       | ...       |

You already know that the column-wise sum of an emission matrix is always 1. So, in the matrix above, suppose the word ‘word_1’ appears a total of 20 times as a ‘PoS_TAG_1’ in the entire data set, and the total count of ‘PoS_TAG_1’ in the entire data set is 80. Then the emission probability of ‘word_1’ will be 20/80, i.e., 0.25, which is also referred to as **P(word_1| PoS_TAG_1).**

Now, based on the knowledge of the emission matrix and probability, you need to create an emission matrix for the given data set, i.e., ‘tagged_words.csv’. You can ignore the case of the words in the data set. What is the value of **P(his|PRON)**?

**Hint**: You can use the Pandas library and try to create a crosstab using **pd.crosstab()** and use the normalize option for the columns to obtain the proportion values appropriately.

- 0.051

- 0.001

- 0.0002

- 0.01

Ans: B. *Please refer to this code:*

```python
import pandas as pd
data = pd.read_csv("tagged_words.csv")
emmission_matrix = pd.crosstab(data['word'],data['tag'],normalize='columns')
word = 'his'
emmission_matrix.loc[word][emmission_matrix.loc[word]>0].round(3)
emmission_matrix['PRON'].loc['his'].round(3)
```

Qn: Using the given data set, can you compute the transition matrix? Hint: Look for definite markers of sentence boundary, don't assume "?", "!" etc to be representing end of sentence conclusively in this dataset

- Yes

- No

Ans: B. *To compute the transition matrix, you need data on the sentence boundaries as well. In the current data set, you only know which words had which PoS tags.*

Qn: When you use spaCy to perform PoS tagging, which token attributes can be used to extract PoS tags? (Multiple options can be correct.)

- `.pos_`

- `.tag_`

- `.pos`

- `.tag`

Ans: A & B. *In spaCy, `.pos_` reveals the PoS attributes of a token object. In spaCy, `.tag_` reveals the PoS tag attributes of a token object.*
