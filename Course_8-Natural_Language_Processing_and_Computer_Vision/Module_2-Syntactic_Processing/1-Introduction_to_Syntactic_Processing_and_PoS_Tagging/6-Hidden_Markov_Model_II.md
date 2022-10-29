# Hidden Markov Model - II

In the previous segment, you learnt about Hidden Markov Model, and transition and emission matrices.

In HMM, you understood that **transition and emission matrices** specify the probabilities of transition between tags and the emission of the word from the tag, respectively. 

In this segment, you will learn how, with the use of transition and emission matrices, you can assign the correct PoS tag sequence based on the probability values. For this, let’s watch the next video and take a look at another example for a better understanding of the implication of HMM. 

**VIDEO**

Let’s summarise this video below.

Please note that you will not be gaining an in-depth understanding of HMM in this module, you will only gain an intuitive understanding of how HMM works on sequence labelling of PoS tags.

In the video provided above, Sumit took a basic example to understand the working of HMM. Suppose you have the following corpus of the training dataset.  

![Sumit HMM](https://i.ibb.co/bFq1CSV/Sumit-HMM.png)

The emission and transition matrices of this corpus are as follows:

![Emission and Transition Matrices](https://i.ibb.co/njCSf3n/Emission-and-Transition-Matrices.png)

Suppose you have been given the following test sentence to predict the correct PoS tags of the words.

S: 'Sumit teaches NLP.'

As of now, we are only considering the two PoS tags, i.e., noun (N) and verb (V).

There are many combinations of PoS tags possible for the sentence ‘S’ such as NVN, NNN, VVV and VVN or NNV.

If you calculate the total number of combinations for this example, then you will see that there are only noun and verb tags; hence, 2^3 will be the total number of combinations possible.

Let’s consider the two sequences as of now, which are NNN and NVN.

Calculate the score for the NNN sequence.

**Score of NNN:   
\[P(Start-Noun) \* P(Sumit|Noun)] \* \[P(Noun-Noun)*P(teaches|Noun)] \* \[P(Noun-Noun) *\ P(NLP|Noun)]**

(0.7\*0.2) \* (0.2\*0.05) \* (0.2\*0.1) = 0.000028

**Score of NVN:  
\[P(Start-Noun)\*P(Sumit|Noun)] \* \[P(Noun-Verb)\*P(teaches|Verb)] \* \[P(Verb-Noun) \* P(NLP|Noun)]**

(0.7\*0.2) \* (0.5\*0.3) \* (0.65\*0.1) = 0.001365

You get the maximum score for the NVN sequence; hence the model assigns the noun to ‘**Sumit**’, the verb to ‘**teaches**’ and another noun to ‘**NLP**’ in the test sentence.  
 
#### HMM

For the sequence of the three words: 'The high cost' and three possible tags: Noun, Adjective and Determinant, there are 27 possible tag sequences. Which of the following will be the generalised expression of n terms and t tags?  

- $n^t$

- $t^n$

- $n*t$

- None of the above

Ans: B. *$t*t*t*\dots~(n~\text{times})$ and hence, the value is $t^n$.*

Qn: Choose the correct option from those given below.  
What is ‘Hidden’ in the Hidden Markov Model in the context of PoS tagging?  
 
- Words

- PoS tags

- Transition and emission probabilities

Ans: B. *PoS tags are hidden.*

Qn: Choose the correct option from those given below. Suppose you have been given the following emission and transition matrices.  
 

![](https://images.upgrad.com/707ce2cf-0681-47e1-ac2a-40df6eaaf385-syntactic%20pic10.png)

![](https://images.upgrad.com/652054e9-05f0-40d3-9c13-c82c9b06d55c-syntactic%20pic11.png)

You also have been given the following sentence.  
   
*“Reena learns ML.”*  
   
You need to consider only two PoS tags as of now, which are noun and verb. What will be the score or the probability of the VNV sequence?  
 
- 0.00000121

- 0.00000456

- 0.00000305

- 0.00000231

Ans: C. *\[P(Start-Verb) \* P(Reena|Verb)\] \* \[P(Verb-Noun) \* P(learns|Noun)\] \* \[P(Noun-Verb) \* P(ML|Verb)\] = (0.03\*0.025)\*(0.65\*0.05)\*(0.5\*0.025) = 0.00000304687*

Qn: Choose the correct option from those given below. What do you mean by sequence labelling in PoS tagging tasks?  
 
- Assigning the PoS tags to each word of a sentence sequentially by considering the PoS tags of the previous word

- A sentence that is a sequence of words that follow some grammar rules and assign PoS tags to each word by looking at grammar is called sequence labelling

- None of the above

Ans: A. *Sequence labelling is the task of labelling the individual units (words) in a sequence (sentence) by looking at the PoS tag of the previous word. PoS tagging is thus a natural use case of sequence labelling.*

In practice, you do not have to calculate these scores from scratch. You will be using an already prepared toolkit to implement HMM, but it is important to be aware of the basic techniques used in PoS tagging. 

Although you are not going to implement these PoS tagging techniques in the real-life scenario, you are going to use the SpaCy library to tag the correct PoS tags that are based on the neural network models. It is important to have an intuitive understanding of these techniques, including the rule-based tagger and HMM, to understand how a PoS tagger works.

With this, you have understood the theory part of PoS tagging. In the next segment, we will implement PoS tagging in Python.