# What is Sequential Data?

You must have watched a lot of movies. However, have you ever tried watching movies from the interval? That does not make any sense, right! Why? Because all the events in the movie are inter-connected. Now, can we swap two such events together? No, there is a specific order of occurrence of events. Let’s hear an example from the professor.  

**VIDEO**

So, you learnt two things –

-   We need previous knowledge to interpret current events.
-   Swapping two such events will not make any sense.

Hence, if you observe these two properties in a data set, it is a sequential data. Let’s understand this better as the professor explains with some more examples.

**VIDEO**

In sequential data, entities occur in a particular order. If you break the order, you do not have a meaningful sequence anymore and it can be anything – numbers, image frames, audio, text, etc. For example, you could have a sequence of words which makes up a document. If you jumble the words, you will end up having a nonsensical document. Now, let’s also see examples where the sequence comprises images and audio.

**VIDEO**

Similarly, you could have a sequence of images or frames which makes up a video. If you shuffle the frames, you will end up having a different video. Likewise, you could have a piece of music which comprises a sequence of notes. If you reshuffle the notes, you will mess up the melody.

#### Sequential Data

Qn: Which of the following data sets can be classified as sequential data?

- Stock market prices

- Music notes

- Order history of customer

- Temperature history

Ans: All of the above. 

- *Stock market prices follow a sequential nature as previous prices can be used as an indication to determine future prices.*

- *Music notes follow a sequential nature as a sequence of notes form a soothing music.*

- *Order history of a customer follows a sequential nature as previous order history can be used as an indication to determine future order values. For example, groceries are usually bought on a weekly basis.*

- *Weather temperature follows a sequential nature as previous temperatures along with other meteorological parameters can be used as an indication to determine future temperature trends.*

#### Sequential Modelling

Qn: Which of the following algorithms/models consider the sequential ordering for making predictions?

- Naive Bayes

- Decision tree

- ARIMA

- Convolutional Neural Networks

Ans: C. *Auto regressive integrated moving average (ARIMA) predicts the future target variable considering the current and previous values of the target variable.*

You saw some examples of sequence data and their use cases. But are RNN models necessary to solve these types of problems? Let’s see in the next segment.