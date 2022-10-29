# PoS Tagging

As of now, you have understood what the different part-of-speech tags are and their relevance in understanding the text. Now, let’s understand how a machine assigns these PoS tags to the words in a sentence.

In the next video, you will understand the broad architecture of the PoS tagger model.

**VIDEO**

As discussed above, a PoS tagger is a model/algorithm that automatically assigns a PoS tag to each word of a sentence.

![PoS Tagger](https://i.ibb.co/xHDp7np/Po-S-Tagger.png)

In this example, the input is 'upGrad is teaching NLP.'. When you put this sentence into a model or tagger, it will result in the output with respective PoS tags assigned to each word of the sentence such as ‘**upGrad**’ (noun), ‘**is**’ (verb), ‘**teaching**’ (verb) and ‘**NLP**’ (noun).

Let’s take a look at another example given below.

**-   Tagger input**: *‘She sells seashells on the seashore.’*

**- Tagger output**: *‘She **(PRON)** sells **(VERB)** seashells **(NOUN)** on **(SCONJ)** the **(DET)** seashore **(NOUN)**.’*

You can refer to the [universal PoS tag](https://universaldependencies.org/docs/u/pos/index.html) list for finding tags corresponding to their parts of speech and also refer to the alphabetical list of part-of-speech tags used in the [Penn Treebank](https://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html) Project, which is being used by the SpaCy library.

Now, let’s try to understand how one can build a simple rule-based PoS tagger to assign PoS tags to individual words in a sentence. 

Suppose you have been given a training dataset that comprises words and their respective PoS tags’ count. This is visually demonstrated in tabular format below. 

![PoS Tags Naive Model](https://i.ibb.co/Gny3kRY/Po-S-Tags-Naive-Model.png)

In this table, the word ‘Word_1’ occurs as a noun two times, and as an adjective, it occurs six times and so on in the training dataset.

The identification of PoS tags in the training dataset is done manually to predict the PoS tags of the test data.

In the table provided above, ‘Word_1’ appears as a noun two times, and as an adjective, it appears three times and so on. Now, suppose, you are given the following sentence (S).

S: “Word_4  Word_1  Word_3.”

What will be the PoS tags of each word in this sentence?

Let’s try to find the answer to this exercise in the next video.

**VIDEO**

In this video, you got the answer to the previous exercise, i.e., the PoS tags of the words of the sentence S will be as follows:

Word_4: Noun  
Word_1: Adjective  
Word_3: Pronoun

You assign the most frequent PoS tags that appear in the training data to the test dataset, and you realise that rule based tagger gives good results most of the time.

But, sometimes, it does not give satisfactory results because it does not incorporate the context of the word.

Let’s take the following example.

Consider the word ‘race’ in both the sentences given below:

1.  ‘The tortoise won the race.’
2.  ‘Due to the injury, the horse will not be able to race today.’

In the first sentence, the word ‘race’ is used as a noun, but, in the second sentence, it is used as a verb. However, using the simple frequency-based PoS tagger, you cannot distinguish its PoS tags in different situations.

#### PoS tagging

Qn: In the sentence given below, A and B are the PoS tags for the word 'wound'. Which of the following options is correct? The bandage was wound/**A** around the wound/**B**.  

- A - Verb, B - Verb

- A - Noun, B - Verb

- A - Noun, B - Noun

- A - Verb, B - Noun

Ans: D. *The first mention of '**wound**' represents the injury/cut, and the second represents the act of '**winding**' the bandage.*

Suppose you have been given a training dataset that comprises words and their respective PoS tags’ counts, which are given in the following table.

![PoS Tagging Qn](https://images.upgrad.com/f680dbfa-2fc1-4fc1-a460-715a687d574a-syntactic%20pic3.png)
 
You have been given the following two sentences:  
S1: ‘I am working as a teacher.’  
S2: ‘Teachers light the way of working professionals.’  
   
Based on the information given above and the rule-based tagger technique, please answer the following question. 

Qn: What will be the PoS tag of the word ‘light’ in the sentence S2 using the rule-based tagger?

- Noun

- Verb

- Adjective

Ans: B. *The count of occurrence of the word ‘**light**’ as a verb is 10, which is maximum.*

Qn: What will be the PoS tag of the word ‘working’ in the sentence S2 using the rule-based tagger?

- Noun

- Verb

- Adjective

Ans: C. *The count of occurrence of the word ‘working’ as an adjective is 8, which is maximum.*

Qn: Is the PoS tag of the word ‘working’ in S1 that you have determined using the rule-based tagger technique correct?  
 
- Yes

- No

Ans: B. *The correct PoS tag of the word ‘**working**’ in S1 is a verb, but if you take a look at the table provided above, you will see that the count of occurrence of the word ‘**working**’ as an adjective is 8, which is maximum; hence, its tag will be an adjective but not a verb based on the rule-based technique.*

Qn: Is the PoS tag of the word ‘working’ in S2 that you have determined using the rule -based tagger technique correct?

- Yes

- No

Ans: A. *The correct PoS tag of the word ‘**working**’ in S2 is an adjective, and if you take a look at the table provided above, then you will see that the count of occurrence of the word ‘**working**’ as an adjective is 8, which is maximum; hence, its tag will be an adjective based on the rule-based technique.*

To improve this method of PoS tagging further, in the next segment, you will learn about how context information can be incorporated while building PoS taggers. You will understand how Hidden Markov model, a type of sequence labelling modelling technique, help us in doing exactly that.