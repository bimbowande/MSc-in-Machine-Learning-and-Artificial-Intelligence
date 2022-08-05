# Components of a Decision Tree

So far you have been introduced to the concept Decision Trees and the two main types of Decision Trees. Besides these two main types of Decision Trees, they can also be divided into the following:

1.  Binary Decision Tree: Test splits into exactly two partitions
2.  Multi-way Decision Tree: Test splits into more than two partitions.

Take a look at the image below for better understanding:

![Binary vs Multi-Class Decision Tree](https://i.ibb.co/QYxh41h/Binary-vs-Multi-Class-Decision-Tree.png)

Image 2

However, the basic structure of a Decision Tree for both types remains the same. In this particular segment, you will be introduced to different parts of the tree which you will be using while creating a tree yourself and solving the case-study in the upcoming segments.

In order to create a Decision Tree yourself, you need to be aware of basic terminologies related to Decision Trees. Let us do so using a short case study. You will be introduced to the problem statement and the Decision Tree structure in this segment so as to explain in detail about different parts of the tree structure. The same problem statement will be used as we move ahead in order to make computations and reach the solution. Let us hear Sajan explain the problem statement:

**VIDEO**

You have a case study where you need to predict whether or not a person is infected with coronavirus or not. It is a binary class problem i.e., the solution can be either ‘Yes’ or ‘No’. You will be dealing with the following features:

1.  **Symptoms showed by the patient.**
    1.  Fever
    2.  Breathing Problem
    3.  Cough
2.  **Days since International Travel.**
    1.  Less than 14 days
    2.  More than 14 days
3.  **Interaction with an Infected Person.**
    1.  With mask
    2.  Without mask

The Decision Tree for this problem statement has three categorical features: Symptoms, International Travel and Interaction with an Infected Person. You have seen how a decision tree looks like as shown below. However, the below decision is not the tree that you'll get when you build using the decision tree algorithm later in the session. This image is just to show how a decision tree looks like and how to interpret it using a series of if-else statements.  

![Corono Decision Tree](https://i.ibb.co/wsF3N5D/Corono-Decision-Tree.png)

Now that you have been introduced to the problem statement and visualised the Decision Tree, try comparing this Decision Tree structure as shown in the image above with the if-then-else statement as done in the previous segment. Try doing it on your own before you proceed to the upcoming video where Sajan explains the same in detail:

**VIDEO**

Now that you have a basic understanding of how the tree structure looks, let us understand from Sajan the terminologies related to a Decision Tree in detail in the next video:

**VIDEO**

The image below shows various components of the Decision Tree:

![Components of Decision Tree](https://i.ibb.co/yVyCJsB/Components-of-Decision-Tree.png)

You have already understood different parts of a tree in the above video but before moving forward let us quickly revise them. Following are the parts of the Decision Tree:

1.  **Root Node:** It is the starting/ first node of a Decision Tree. It further splits into different nodes to form a tree.
2.  **Splitting:** It is the process by means of which a node breaks down into further nodes.
3.  **Edge:** An edge represents possible values into which a parent node splits.
4.  **Leaf / Terminal Node:** The node that does not split is called Leaf or Terminal node.
5.  **Branch / Sub-Tree:** A subsection of the tree is called branch or sub-tree.
6.  **Parent and Child Node:** A node that divides into sub-nodes is called a parent node of the sub-nodes whereas the sub-nodes are the child of a parent node.

A leaf node represents the class label whereas attributes are shown by the other internal nodes. A Decision Tree is in the form of boolean functions. The answers to the questions asked are either “Yes” or “No” and outcomes are based on them.

In the next segment, we'll learn about the basis on which the split at any node occurs: Homogeneity.Binar