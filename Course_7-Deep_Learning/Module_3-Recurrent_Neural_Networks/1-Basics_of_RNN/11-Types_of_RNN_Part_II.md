# Types of RNN - Part II

Apart from classifying RNNs based upon types of input and output you can also classify them depending upon the direction in which the input is fed into the RNN. You can have the following types of RNN based on direction:  
 

**Forward RNN**  
When the relevant information is available before the time step at which we are predicting, then we use forward RNN. It only considers the pre-occurring information for the prediction. Let’s take an example of a sentence where we want to predict the word at a certain time step.

*I will have to learn French since I am going to \_\_\_\_\_.*

In this example, the forward RNN will be effective as it will only consider the words occurring before the last time step, which is enough for the model to learn.

**Bidirectional RNN**

As of yet all of the RNNs that you saw used the prior information to make predictions. But what if the relevant information does not come before but after the time step at which we want to predict. Let’s look at the below example.

*I will have to learn \_\_\_\_\_ since I am going to France.*

As you can see here that the relevant information ‘France’, lies after the prediction time step and, hence, forward RNN will not be able to predict efficiently as it will look only at the pre-occurring words only.

Now, if you have the offline sequences i.e when the whole sentence is available beforehand, then you can input the post-occurring words to the RNN and get the output. The training will also be a bit different than the simple RNN as we will need to first train on a forward sequential path and then on backward sequential path. Hence for a sequence of size n,

1.  The first part of the training will be on the sequences occurring  in a forward path $(x_0, x_1,\dots,x_n)$ and we get hidden states $(h_{f0}, h_{f1},\dots,h_{fn})$ (‘$f$’ for ‘forward’)
2.  Then on the sequence occurring in the backward path $(x_n,x_{n−1},\dots,x_0)$ and we get output hidden states $(h_{bn}, h_{b(n−1)},...h_{b0})$ (‘$b$’ for ‘backward’)
3.  Ultimately we combine the hidden states obtained at each time step from these two paths and use them with some output layer to get the final output.

**Bidirectional RNN can be helpful in below two cases -**

1.  When you are not certain whether the relevant words are coming before or after the current time step
2.  When relevant information is present on both sides (before and after) of the current time step. For example I will have to learn French \_\_\_\_\_ I am going to France. Here the correct prediction will be the word ‘since’ and your model should be able to see both pre and post occurring sentences to predict it correctly.

As you can see, since the model is built twice on the input length as compared to once in case of a  forward or simple RNN, the training complexity also becomes two fold.

#### Match RNN Types with Use Cases

Qn: Which of the following pairs of sequential problems and RNN types are best suited?

- IMDb movie rating prediction: Bidirectional many-to-one RNN

- Music notes generation in real time: Bidirectional many-to-many RNN

- Part of speech tagger: Bidirectional many-to-many RNN

Ans: A & C. 

- *In IMDb movie rating we will be predicting only one value, i.e., rating, and we will also have all the reviews available beforehand (offline). Hence, Bidirectional many-to-one will give best results for this use case.*

- *In named entity recognition, the data will be completely available offline. Hence, we can apply Bidirectional RNN for better results.*

Now that you have a basic understanding of architecture along with types of RNN, let’s discuss the training part in the next segment.

## Additional Reading:

If you want to learn more about bidirectional RNNs, please refer to this [link](https://devopedia.org/bidirectional-rnn).