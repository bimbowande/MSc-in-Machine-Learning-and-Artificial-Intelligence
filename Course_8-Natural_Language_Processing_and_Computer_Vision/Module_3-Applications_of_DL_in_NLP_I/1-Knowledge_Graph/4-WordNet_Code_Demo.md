# WordNet - Code Demo

In the previous segment, you gained an understanding of word senses, synsets and relations between word senses in WordNet. In this segment, you will learn how to use the NLTK library to parse the graph in WordNet.

You can download the files from the github [link](https://github.com/ContentUpgrad/semantic_processing). Refer README.md in the link for proper instructions for downloading the files.

Put on your coding hats and let’s get started.

**VIDEO**

You learnt how to get the synsets of a word and the definition of each sense of the word. 

![WordNet Example Tractor](https://i.ibb.co/6w7YzhW/Word-Net-Example-Tractor.png)

[Source](https://web.stanford.edu/~jurafsky/slp3/18.pdf)

We started from the tractor and traversed the graph upwards using the hypernyms function in WordNet until we reached the wheeled vehicle. 

Then, we used the meronyms function to traverse the ‘has part’ relation.

Now that you learnt how to traverse up the graph, in the next video, let’s try to traverse down the graph.

**VIDEO**

We can traverse the graph downwards using the hyponyms function. 

Please note that all the hyponyms of a particular word are not shown in the graph.

#### Knowledge Graphs

Qn: Let’s consider the example given below.

![WordNet Example Tractor](https://i.ibb.co/6w7YzhW/Word-Net-Example-Tractor.png)

What function will you use to traverse in an upward direction for an ‘is a’ relation?

- Hypernyms

- Hyponyms 

- Meronyms 

- Holonyms

Ans: A. *We use the hypernyms function to traverse in an upward direction of an ‘is a’ relation.*

You also learnt how to use the NLTK library to traverse the WordNet graph and understood the different relations in WordNet. In the next segment, you will learn how to apply these functions for Word sense disambiguation.