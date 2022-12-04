# Understanding Generators

Now that you understand the two types of architectures to experiment with, let's discuss how to **set up the data ingestion pipeline**. As you already know, in most deep learning projects you need to feed data to the model in batches. This is done using the concept of **generators.** 

Creating data generators is probably the most important part of building a training pipeline. Although libraries such as Keras provide builtin generator functionalities, they are often restricted in scope and you have to write your own generators from scratch. For example, in this problem, you need to feed _batches of videos_, not images. Similarly, in an entirely different problem such as 'music generation,' you may need to write generators which can create batches of audio files. 

In this segment, you will learn the basic concepts of a generator function and apply them to create a data generator from scratch.

## **Understanding Generators (External Links)**

In this project, you will write your own batch data generator (explained in the next couple of lectures). Before moving to those lectures, we highly recommend that you develop an intuitive understanding of Python's **generator functions**. The following two resources explain the concept of generators well, we recommend that you go through both of them in this order:

-   [Introduction to Python Generators](https://realpython.com/introduction-to-python-generators/)
-   [Corey Schafer (YouTube video): Generator functions](https://www.youtube.com/watch?v=bD05uGo_sVI)

You must have figured out from the above links that a generator object requires very less memory as compared to a function which is of primary importance in deep learning models.

## **Keras' Fit Generator**

Now that you understand how generator functions work, let's see how Keras uses the 

fit.generator() method with a generator function (that you will write) to train the model.

**VIDEO**

You understood that the generator **yields a batch of data** and 'pauses' until the fit_generator calls next(). Note that in Python-3, this functionality is implemented by _next_(). 

In the next segment, you'll be taken through the different parts of the starter code in detail.