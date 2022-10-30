# Knowledge Graphs

Let’s get started with the first method of semantic processing, which is the knowledge graph.

A graph data structure consists of a finite set of vertices (also called nodes or points), where some pairs are connected through edges.

**VIDEO**

In the case of semantic processing, the text data is aggregated on the graph-based data structure. In the knowledge graph, entities are represented by nodes, where some pairs of the entities are related in some sense. These relations are represented by edges.

![Entity Relation](https://i.ibb.co/vXR38N9/Entity-Relation.png)

These graphs contain the semantic information of different entities. An example of a knowledge graph is given below.

![Knowledge Graph Example](https://i.ibb.co/RyCNFWR/Knowledge-Graph-Example.png)

  
You can see the different types of entities, which are human, occupation, names of people and names of places.

The different types of relationships are ‘is a’, ‘was born in’ and ‘is capital of’. 

This is a simple representation of graphs however, graphs are generally very complex structures. 

#### Knowledge Graphs

Qn: In a knowledge graph, what do edges represent?

- Semantic relations 

- Entities 

- Objects 

Ans: A. *Nodes represent entities, and edges represent the semantic relations between them.*

Qn: Which of the following types of semantic association exists between a college and its research laboratory?

- IS A

- IS IN 

- COULD BE

Ans: B. *The research laboratory is in the college.*

Qn: Which of the following relationships is an ‘IS A’ relationship? (Note: More than one option may be correct.)

- Student and human being  
 
- Facebook and Twitter

- Coffee and beverage

- The Indian Army and the Republic of India

Ans: A & C. *Student is a human being, and coffee is a beverage.*

In the next video, let’s take a look at the real-life examples of knowledge graphs.

**VIDEO**

The different types of knowledge graphs are as follows:

-   [WordNet:](https://wordnet.princeton.edu/) This is a lexical database of semantic relations between words. It is developed by Princeton University.

-   [ConceptNet](https://conceptnet.io/): This is a freely available semantic network that is designed to help computers understand the meanings of words that people use. It is developed by MIT.

The graph that describes the conceptnet is given below.
  
![ConceptNet](https://i.ibb.co/0Vz0BBz/Concept-Net.png)

Both WordNet and ConceptNet are used for natural language understanding. At the end of this session, we will use WordNet to solve a use of Word Sense Disambiguation.

Another type of knowledge graph is UMLS. 

-   Unified Medical Language System (UMLS): It is a set of files and software that brings together many health and biomedical vocabularies and standards to enable interoperability between computer systems.
    

Suppose you need to understand the text data that is related to the medical field. If you use WordNet or ConceptNet, you will have words that do not have relevance, and the results will be inaccurate. Hence, you require domain-specific knowledge graphs.

We know the famous knowledge graph called Google Search.

Although these are openly available knowledge graphs, many companies create their own knowledge graphs according to their company requirements.

-   Microsoft uses knowledge graphs for the Bing search engine, LinkedIn data and academics.
   
-   Facebook develops connections between people, events and ideas, focusing mainly on news, people and events related to the social network.

-   IBM provides a framework for other companies and/or industries to develop internal knowledge graphs.

-   eBay is currently developing a knowledge graph that functions to provide connections between users and the products present on the website.

Fun Exploration:

Watson is a question answering computer system that can answer questions posed in natural language. It is based on knowledge graphs. You can watch Watson winning the famous game of jeopardy [here](https://www.youtube.com/watch?v=P18EdAKuC1U). 

Now that you have gone through different types of knowledge graphs, in the next segment, you will gain a detailed understanding of one of the widely used knowledge graphs: ‘WordNet’.