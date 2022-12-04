# Word Sense Disambiguation - Code Demonstration

In the previous segment, you understood the intuition behind the Lesk algorithm. In this session, you will gain an understanding of the implementation of Lesk in Python.

You can download the files from the github [link](https://github.com/ContentUpgrad/semantic_processing). Refer README.md for proper instructions of downloading the files.

**VIDEO**

You learnt how to find the correct sense of the word ‘die’ in the following sentences:

X = 'The die is cast.'

Y = 'Roll the die to get a 6.'

Z = 'What is dead may never die.'

Although the Lesk algorithm could give the correct sense, we had to provide the POS tag of the word as the input for it to perform accurately. But we are manually entering the POS tag for each word. In the next video, you will learn how to automate the process.

**VIDEO**

We created a function that automatically detects the POS tag of a function and provides it to the Lesk algorithm. We can now use this function to disambiguate words and find their correct sense.