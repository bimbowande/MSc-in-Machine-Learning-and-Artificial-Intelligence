# Code Demonstration - Gensim Part 1

In the previous segments, you understood the working of the skipgram model and the CBOW model. Now, let’s go through a code demonstration using the Gensim library.

We will create word vectors using the Word2Vec model from the Wikipedia data of all the countries that we have saved in ‘countries.json’.

Before starting the code demonstration, please follows the steps given below:

1.  Install the Gensim library using the command in Jupyter Notebook.
    
    `!pip install gensim`
    
2.  Download the data set from [here](https://drive.google.com/drive/u/0/folders/1KUnMvuufvo0yXS23EaI2EMNaq2lt5Ynh).
    
3.  Download the files from the github [link](https://github.com/ContentUpgrad/semantic_processing). Refer README.md in the link for proper instructions for downloading the files.
    
4.  Keep the utils.py in the same folder as the notebook.
    

_Note: The outputs that you will get might differ from the outputs shown in the below video. It is because the algorithms are randomly initialised._

In the upcoming video, we will start the code demonstration

**VIDEO**

NOTE: To see the total vocabulary, kindly replace the syntax model.wv with **model.wv.vocab.**

In this video, you saw how the input data set looks and understood the basic usage of the Word2Vec function in the Gensim library. You saw that the words similar to India were as follows:

[('China', 0.8318845629692078),

 ('Iran', 0.7939356565475464),

 ('Brazil', 0.762339174747467),

 ('Mexico', 0.7565432786941528),

 ('Pakistan', 0.7444307804107666)]

The output is not accurate and does not have much correlation. Now, let’s try to change the parameters of the Word2Vec function to check if we obtain words that are correlated.

**VIDEO**

You understood that you can obtain accurate word vectors by changing the parameters such as vector_size, epochs and max_vocab_size of the Word2Vec function. 

You also learnt how the loss decreases with an increasing number of epochs. As the accuracy of the neural network has remained constant approximately after the epoch 70, we can say that the word vectors have managed to capture the meaning of the words.

In the next segment, let’s apply some vector operations to these word vectors.