# Evolution of Machine Translation

Language is a complicated problem to decode and we have been trying to solve it for many years. We, humans, are social animals, and a majority of our communication happens in English. However, there are many other languages all over the world. 

With the help of machine translation, we can remove this barrier between different languages and have seamless communication between two people from different parts of the globe.  
In the next video, Mohit will explain how machine translation bridges the language barrier and how it has evolved so far.

**VIDEO**

Mapping an input sentence present in one language to a sentence in another language is called machine translation. For a long period of time, translation was a labour-intensive process that depended exclusively on human effort. Though this process is reliable, it takes a lot of time and is computationally expensive too. To accurately translate the given text, translators have to depend on a volumetric amount of information within the required time. 
  
In 1949, Warren Weaver gave the idea of language translation using machines. To perform translation, all the linguistic relationship between the source and the target language was studied. This kind of translation was called **Rule-Based Machine Translation (RBMT)** as it was based on dictionaries and grammar.

As years progressed, different methods of translation emerged paving the way for better and quicker translation. Integrating statistical models helped get the job done by finding the statistically most likely translation for use. This kind of approach, known as **Statistical Machine Translation (SMT)**, performed better than RBMT and was used across the 1990s. 

With the development of neural-based language models by Yoshua Bengio, it was understood that the neural networks-based model could perform better in understanding languages. His work laid the foundation for using neural networks in machine translation.
  
In 2014, Sutskever et al. and Cho et al. developed a model known as **sequence to sequence (seq2seq)** for the task of **Neural Machine Translation(NMT)**. This model used long short-term memory (LSTM) for both encoder and decoder, which together framed end-to-end learning of the model. As an encoder, LSTM maps the input sequence to a vector of fixed dimensions. This vector is then propagated to the decoder as a context. Using this context vector, another LSTM decodes a target sequence which forms the translation. 
  
To understand more about what a sequence to sequence model is, let’s move to the next segment.