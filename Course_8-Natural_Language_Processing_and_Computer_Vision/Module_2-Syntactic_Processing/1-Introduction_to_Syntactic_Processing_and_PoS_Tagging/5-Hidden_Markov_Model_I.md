# Hidden Markov Model - I

In the previous segment, you learnt about PoS tagging based on the frequency of tags alone, which seems inefficient when words are used in different contexts. So, to improve this model, in this segment, you will learn about the Hidden Markov Model, which performs better and uses the context of the previous word to decide the PoS tag of the current word.

Let’s consider the following example; what does your mind process when you see the blank space at the end of this sentence?

'*Rahul is driving to \_\_\_\_\_.*'

Don’t you think that the blank space should be the name of a place?

How do you manage to identify that the blank space would be a name of the place? 

Try to analyse your thoughts after reading this statement, when you see the word ‘Rahul’ who is driving to some place and hence, you reach to a conclusion that the blank space should be the name of a place (noun).

This means that you have sequentially looked at the entire sentence and concluded that the blank space should be the name of a place. 

Now, what if we build an algorithm that can work sequentially to identify the PoS tags of the words based on the PoS tag of the previous word? In the next video, Sumit will explain sequence labelling techniques, particularly Hidden Markov Models, in detail.

**VIDEO**

Sequence labelling is the task of assigning the respective PoS tags of the words in the sentence using the PoS tag of the previous word in the sentence.

Hidden Markov Model can be used to do sequence labelling, which means that it takes input of words in a sequence and assigns the PoS tags to each word based on the PoS tag of the previous word. 

In the video example ‘The tortoise won the race’, to decide the PoS tag of ‘race’, the model uses the PoS tag of the previous word, i.e., ‘the’, which is an article. 

Now, let’s take a look at the following points and try to understand why Hidden Markov Model is called ‘Hidden’:

-   When you observe (read/listen) a sentence, you only observe the words in the sentence and not their PoS tags; thus, PoS tags are hidden.
-   You must infer these hidden tags from your observations, and that's why Hidden Markov Model is called Hidden.

There are majorly two assumptions that HMM follows, which are as follows:

-   The PoS tag of the next word is dependent only on the PoS tag of the current word.
-   The probability of the next word depends on the PoS tag of the next word. 

  
Before learning about HMM, you need to understand the two most important types of matrices, i.e., emission and transition matrices. In the next video, let’s take a look at an example of how you can build these matrices.

Play Video

3221820

To build any machine learning model, you first need to train that model using some training data, and then, you need to use that model to predict the output on the test data.

Here, the train data is the corpus of sentences, and you need to perform some manual tasks to assign the PoS tags to each word in the corpus. Once you manually assign the PoS tags to each word in the training corpus, you create two important matrices using the training dataset, which are as follows:

-   Emission matrix
-   Transition matrix

**Note**: We have used only two PoS tags, i.e., noun and verb, as of now to understand the concept in a simpler manner.

**Emission matrix:** This matrix contains all words of the corpus as row labels; the PoS tag is a column header, and the values are the conditional probability values.

**Note**: Conditional probability is defined as the probability of occurrence of one event given that some other event has already happened. You will get more idea about this in the following example.

![Emission Matrix](https://i.ibb.co/K750y01/Emission-Matrix.png)

For example, in the corpus that has been used in the video provided above, whenever a noun appears in the training corpus, there is an 18% chance that it will be the word ‘judge’. Similarly, whenever a verb appears in the training corpus, there is an 84% chance that it will be the word ‘laugh’.

So, here, 0.18 is the probability of occurrence of the word ‘judge’ given that there will be a noun at that place. In a similar way, 0.16 is the probability of occurrence of the word ‘judge’ given that there will be a verb at that place.

**Transition matrix**: This matrix contains PoS tags in the column and row headers. Let’s try to understand the conditional probability values that have been given in the following table.

Let’s take a look at the first row of the table; it represents that 0.26 is the probability of occurrence of a noun at the start of the sentence in the training dataset. In the same way, 0.73 is the probability of occurrence of a verb at the start of the sentence in the training dataset.

If you take a look at the second row, then you will see that 0.44 is the probability of occurrence of noun just after a noun in the training dataset, and similarly, 0.19 is the probability of occurrence of a verb just after a noun in the training dataset.

![Transition Matrix](https://i.ibb.co/q1WQHGf/Transition-Matrix.png)

Essentially, the transition matrix gives the information of the next PoS tag considering the current PoS tag of the word.

#### HMM

Which of the following assumptions (both implicit and explicit) is made while doing HMM sequence labelling?  

- The probability of the PoS tag for a given word is dependent upon the word and the previous tag in a sequence. 

- The probability of the next tag is dependent on the past $k$ tags, where $k>1$.

- Both A and B

Ans: A. *Markov assumption: The probability of the PoS tag of a word depends only on the PoS tag of the previous word.*

Qn: Choose the correct option from those given below.  
Suppose you have been given the following table in which there are a total of six words and their counts in the training corpus. You are also given information regarding how many times each word appears as a noun, verb or adjective.

![HMM Qn 1](https://i.ibb.co/2ZDymSd/HMM-Qn-1.png)

When you convert this table into a probability table, which is also known as an emission matrix, you get the following table.

![HMM Qn 2](https://i.ibb.co/8cL342t/HMM-Qn-2.png)

What will be the value of P1 and P12, respectively, in the table provided above?

- 0.76 and 0.094 

- 0.128 and 0.057

- 32 and 8

- None of the above

Ans: B. *$P1=32/(32+76+12+23+94+13)$ and $P12=8/(1+3+45+8+5+78)$*

Qn: Choose the correct option from those given below.  
Suppose you have been given the following table in which there are a total of six words and their counts in the training corpus. You are also given information regarding how many times each word appears as a noun, verb or adjective. From this table, you compute the following emission matrix.

![HMM Qn 2](https://i.ibb.co/8cL342t/HMM-Qn-2.png)

What is the meaning of the value P11 in this table?

- It is the value of conditional probability that if there is a verb at any place in the training corpus, then the probability that it will be the word ‘light’ is equal to P11. 

- It is the value of conditional probability that if there is a word ‘light’ at a particular place in the training corpus, then the probability that it will appear as a verb is equal to P11.

- Both options A and B are interpreting the same thing.

- None of the above.

Ans: A. *This is the correct option, as the column-wise sum of all the probability values is equal to 1.*

Now that you have understood what transition and emission matrices are, in the next segment, you will get an intuitive understanding of HMM and understand how it calculates the scores or probability to identify the correct PoS tags in a sequential manner.