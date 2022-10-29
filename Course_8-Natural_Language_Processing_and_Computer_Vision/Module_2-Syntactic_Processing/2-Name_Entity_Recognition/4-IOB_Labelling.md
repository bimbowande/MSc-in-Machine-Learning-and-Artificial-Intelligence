# IOB Labelling

As you learnt in the previous segment, machine learning can prove to be a helpful strategy in named entity recognition. So, before understanding how exactly ML is used in the NER system, you will learn about IOB labelling and sequence labelling related to the NER system.

**IOB (inside-outside-beginning) labelling** is one of many popular formats in which the training data for creating a custom NER is stored. IOB labels are manually generated.

This helps to identify entities that are made of a combination of words like ‘Indian Institute of Technology’, ‘New York’ and ‘Mohandas KaramChand Gandhi’.

Let’s watch the next video to learn about IOB labels (tags).

**VIDEO**

Suppose you want your system to read words such as ‘Mohandas Karamchand Gandhi', ‘American Express’ and ‘New Delhi’ as single entities. For this, you need to identify each word of the entire name as the PER (person) entity type in the case of, say, ‘Mohandas Karamchand Gandhi'. However, since there are three words in this name, you will need to differentiate them using IOB tags.

The IOB format tags each token in the sentence with one of the following three labels: I - inside (the entity), O - outside (the entity) and B - at the beginning (of entity). IOB labelling can be especially helpful when the entities contain multiple words. 

So, in the case of ‘Mohandas Karamchand Gandhi', the system will tag ‘Mohandas’ as B-PER, ‘Karamchand’ as I-PER and ‘Gandhi' as I-PER. Also, the words outside the entity ‘Mohandas Karamchand Gandhi' will be tagged as ‘O’.

**Consider the following example for IOB labelling:**  
Sentence: ‘Donald Trump visit New Delhi on February 25, 2020 ”

| Donald   | Trump    | visit | New   | Delhi | on  | February | 25     | ,      | 2020   |
| -------- | -------- | ----- | ----- | ----- | --- | -------- | ------ | ------ | ------ |
| B-Person | I-Person | O     | B-GPE | I-GPE | O   | B-Date   | I-Date | I-Date | I-Date |

In the example above, the first word of more than one-word entities starts with a B label, and the next words of that entity are labelled as I, and other words are labelled as O.

**Note that you will not always find the IOB format only in all applications. You may encounter some other labelling methods as well. So, the type of labelling method to be used depends on the scenario.** Let's take a look at an example of a healthcare data set where the labelling contains 'D', 'T', and 'O', which stand for disease, treatment and others, respectively.

S: ‘In[O] the[O] initial[O] stage[O], Cancer[D] can[O] be[O] treated[O] using[O] Chemotherapy[T]’

#### IOB Labelling

Qn: State whether the following IOB labelling for the given sentence is correct or not.

*'Michael Jeffrey Jordan was born in New York on February 17, 1963’*  
Note: GPE is the abbreviation of geopolitical entity.

**IOB labels:**

|              |               |
| ------------ | ------------- |
| **Token**    | **IOB Label** |
| **Michael**  | **B-Person**  |
| **Jeffrey**  | **I-Person**  |
| **Jordan**   | **I-Person**  |
| **was**      | **O**         |
| **born**     | **O**         |
| **in**       | **O**         |
| **New**      | **B-GPE**     |
| **York**     | **I-GPE**     |
| **on**       | **O**         |
| **February** | **B-Date**    |
| **17**       | **I-Date**    |
| **,**        | **I-Date**    |
| **1963**     | **I-Date**    |

- Correct

- Incorrect

Ans: A. *The words 'Michael’', 'Jeffrey' and ‘Jordan’ belong to the same entity. Similarly, 'New' and 'York' represent the same entity. Date starts with ‘February’ till ‘1963’*

In the next segment, you will learn about the pre-trained models for NER in Spacy using Python.
