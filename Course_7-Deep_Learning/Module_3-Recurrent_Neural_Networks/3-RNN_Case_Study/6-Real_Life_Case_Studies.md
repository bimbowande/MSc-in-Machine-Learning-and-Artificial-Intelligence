# Real-Life Case Studies

The problem statement that you solved is one such example where RNN can be applied with good accuracy. However, some big names in the industry, such as Google, Facebook, Apple and Amazon, are using it in their products for speech recognition, image captioning, etc. You will understand how these companies form their problem solutions using the RNN models.

Let’s start with discussing the image captioning model that Google uses.

**VIDEO**

Google uses an image captioning model in its image search results to assist its users in selecting the right link. Being able to automatically describe the content of an image using properly formed English sentences is a very challenging task, but it could have great impact, for instance by helping people better under-stand the content of images on the web.

![Google Image Captioning](https://i.ibb.co/JnwVyr1/Google-Image-Captioning.png)

A description must capture not only the objects contained in an image, but it also must express how these objects relate to each other as well as their attributes and the activities they are involved in. Moreover, the above semantic knowledge has to be expressed in a natural language like English, which means that a language model is needed in addition to visual understanding. Therefore, computer vision Inception v1, v2 models have been used, whereas for good results, LSTM can be used as a language generation model.

You can find additional details about the architecture used by Google for image captioning [here](https://blog.google/products/search/get-more-useful-information-captions-google-images/) and [here](https://ai.googleblog.com/2016/09/show-and-tell-image-captioning-open.html).

However, that is not the only use case of RNN that Google applies. Their online translation tool – Google Neural Machine Translation (GNMT) – also uses RNN-based attention models (LSTM encoder-decoder + attention) for effective translation.

**VIDEO**

The strength of GNMT (Google Neural Machine Translation) lies in its ability to learn directly, in an end-to-end fashion, the mapping from input text to associated output text.  GNMT supports over 10,000 pairs of language translation.

![Language Translation](https://i.ibb.co/s9LJMBm/Language-Translation.png)

The GNMT architecture typically consists of two recurrent neural networks (RNNs), one to consume the input text sequence and one to generate translated output text. NMT is often accompanied by an attention mechanism which helps it cope effectively with long input sequences. The attention mechanism is based on getting context out of different parts of the input sequence rather than just focusing on the context generated at the last time step. You will learn more about it in later modules. You can find more about GNMT’s models,  [here](https://arxiv.org/pdf/1609.08144.pdf) and [here](https://ai.googleblog.com/2016/09/a-neural-network-for-machine.html).

Amazon uses RNN-based models for its virtual assistant, Alexa, to get state-of-the-art results for conversational AI.

Play Video

3221820

Alexa uses a very complex encoder-decoder based architecture to get efficient results and Attention mechanism based on RNN architectures is in the base of its encoder which helps in understanding the personalised voices of its users. You can learn more about Alexa's underlying modeling structure [here](https://www.amazon.science/blog/the-scalable-neural-architecture-behind-alexas-ability-to-select-skills) and [here](http://pages.cs.wisc.edu/~ybkim/paper/acl2018.pdf).

Now, you must be confident to take on the challenges on your own and solve them to enhance your skills.

In the next segment, you will get an idea about how the sequential modelling area is still on the move and how RNNs are relevant with the advent of new technologies.