# Word Sense Disambiguation

Homonymy is when a word has multiple (entirely different) meanings. For example, consider the word ‘pupil’. It can either refer to students or eye pupils depending on the context in which it is used. 

Suppose you are searching for the word ‘pupil’. The search engines sometimes give data relevant to the context and sometimes give irrelevant data. Such things happen because the query may contain words whose meaning is ambiguous or those having several possible meanings.

To solve this ambiguity problem, the Lesk algorithm is used.

In the previous segment, we understood different functions in WordNet. In the next video, you will learn how WordNet can be used to disambiguate words.

**VIDEO**

You can consider the definitions corresponding to the different senses of the ambiguous word and determine the definition that overlaps the maximum with the neighbouring words of the ambiguous word. The sense that has the maximum overlap with the surrounding words is then chosen as the ‘correct sense’.

“She booked the **flight tickets** to Delhi in **advance**”

|            |                                                                                                                                        |
|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Gloss 1    | arrange for and reserve (something for someone else) in **advance**                                                                    |
| Examples 1 | "reserve me a seat on a **flight**"; "The agent booked **tickets** to the show for the whole family"; "please hold a table at Maxim's" |
| Gloss 2    | a written work or composition that has been published (printed on pages bound together)                                                |
| Examples 2 | "I am reading a good book on economics"                                                                                                |

In this example, you will notice that the gloss or meaning 1 has more overlap than gloss 2. Hence, we consider gloss 1 as the correct sense.

Although we have shown only two senses, a lesk algorithm parses through all the word senses and outputs the gloss that has the maximum overlap.

In the next segment, you will learn how to understand how to use WordNet to code the Lesk algorithm in NLTK.

Source: [https://wordnet.princeton.edu](https://wordnet.princeton.edu/) .
