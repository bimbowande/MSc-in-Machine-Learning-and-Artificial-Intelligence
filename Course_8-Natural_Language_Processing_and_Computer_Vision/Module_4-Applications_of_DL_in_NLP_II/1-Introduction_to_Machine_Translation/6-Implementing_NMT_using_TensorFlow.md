# Implementing NMT using TensorFlow

Now that you have understood all the theoretical understanding on how a seq2seq model works, let’s now implement the model. 

**VIDEO**

In this demonstration, the goal is to convert a sentence from the source language (English) to the target language (Hindi).

To understand the notebook effectively the following are the pre-requisites:

-   Sequence to sequence models
-   Working with Keras layers & classes (covered in the segment-'Custom Model Building in Tensorflow'):
    -   Custom [`keras.Model`](https://www.tensorflow.org/api_docs/python/tf/keras/Model) building 
    -   Custom [model.fit()](https://www.tensorflow.org/guide/keras/customizing_what_happens_in_fit)  with Keras

The notebook mentioned in the video can be downloaded from [here](https://drive.google.com/file/d/14kh3C1GO-fTGuANCCDT6xnS2ZkwpEZ-V/view?usp=sharing)

In the next video, Mohit will take you through the demonstration and explain the data preparation process for machine translation.

**VIDEO**

## Data pre-processing

The pre-processing steps can be summarised as :

-   Create the tokenized vectors by tokenizing the sentences and stripping the input and output of extra unnecessary characters. This gives us a vocabulary of all of the unique words in the data. Keep the total number of sentences to 70000 for saving memory.
-   Add `<sos>` (start-of-sentence) and `<eos>` (end-of-sentence) to each sentences.
-   Create word-to-index and index-to-word mappings.
-   Pad all sequences to be the same length as the longest one.

The next step is to split the input & target data into training and validation sets using an 80-20 split. 

After creating the train and validation set, the next task is to create the tf.dataset.

This helps us in creating a data pipeline that can be directly fed to the encoder-decoder model.

**VIDEO**

Once you have created the training dataset, the shape of the input_sequence and target_sequence in the dataset should be of an order [ batch_size,max_length ].

```python
example_input_batch, example_target_batch = next(iter(dataset))
example_input_batch.shape, example_target_batch.shape
```

```python
(TensorShape([64, 72]), TensorShape([64, 69]))
```

where 64 is the batch_size, 72 is the max_length of the input_sequence and 69 is the max_length of the output_sequence.

## Model building

The following image shows us the entire architecture of the NMT model you are going to build.

![NMT Architecture](https://i.ibb.co/8zn9xt5/NMT-Architecture.png)

NMT Architecture

Let's break down the encoder and decoder separately and see the components.

**Encoder model:**

-   It consists of an Embedding layer([layers.Embedding](https://keras.io/api/layers/core_layers/embedding/)) which creates an embedding vector for each token ID.
-   Once the embeddings are generated the GRU([layers.GRU](https://www.tensorflow.org/api_docs/python/tf/keras/layers/GRU))units processes them to a new sequence .

After processing the entire sequence the model returns the encoder output and the hidden state.

![Encode Model](https://i.ibb.co/Ypvzjsm/Encode-Model.png)

![Encoder class](https://i.ibb.co/Hd2B575/Encode-Class.png)

Once you have built your encoder successfully, you can observe: 

Encoder output shape: **(batch size, sequence length, units)** = (64, 72, 1024)

Encoder Hidden state shape: **(batch size, units)** = (64, 1024)

**Decoder model:**

-   It is initialised with the hidden state from the encoder.
-   The embedding layer present in it creates an embedding vector for the target output. The initial input to the layer will be `<sos>` tag and in the shape of **(batch_size,1) as you are passing one token at each timestep.**
-   These vectors are then passed on to GRU units which creates output and hidden state.
-   The hidden state is fed to the next GRU cell and the output is passed the output through a dense layer.

![Decode Class](https://i.ibb.co/pb5N6wS/Decoder-Model.png)

![Decoder class](https://i.ibb.co/NydbKtN/Decoder-Class.png)

After creating the decoder model successfully, you can observe:

Decoder output shape: **(batch_size, vocab size) =** (64, 22224)

Now that we have defined the encoder and decoder model, let’s create the training process for the entire seq2seq model. 

**VIDEO**

## Model Training

After building all the encoder and decoder models you need to set up the training process for the entire NMT architecture. For this, you have to do the following:

-   Set the optimizer('Adam') & loss object(`SparseCategoricalCrossentropy`).
-   Create your checkpoint path.
-   Create your training step functions, which will define how the model will be updated for each input/target batch.

The entire sequence of the model training can be summarised as follows:

Overall the implementation for the [`Model.train_step`](https://www.tensorflow.org/api_docs/python/tf/keras/Model#train_step) method is as follows:

1.  `input_sequence, target_sequence` is received as a batch from the training dataset and passed to `train_step` .
2.  The`input_sequence` is fed to the encoder along with the hidden state to produce `enc_output` and `enc_hidden`.
3.  The decoder is initialised with the `enc_hidden`and is employed with teacher forcing where the target is fed as the next input. Therefore the prediction process is looped over the entire `target_sequence` :
    -   The decoder is run one step at a time. Once the predictions are created the **loss is calculated for each step/word.** 
    -   **Teacher forcing** is applied to change the decoder input to **targ[ : , t],** which denotes the target word at the tth timestep present in the batch.
4.  The average loss is accumulated(by dividing the loss by sentence length) to calculate the batch_loss.
5.  The gradient is calculated using the `tape.gradient` and all the `trainable_variables` (Encoder and Decoder) are updated using the optimizer.  
6.  The model is saved at the checkpoint path after every 2 epochs. 

![train_step function](https://i.ibb.co/PQzpWs2/Train-Step-Function.png)

## Model Inference

Once the model is trained you need to create a `evaluate` function to run the model inference.

Overall the function is similar to `train_step` except that the input to the decoder at each time step is the last prediction from the decoder. 

The major changes to the function are as follows:

-   The input text is processed first by `preprocess_sentence` and padded using the `keras.preprocessing.sequence.pad_sequences` .
-   Once the text is converted to their respective token IDs, the trained decoder will produce a list of predictions (probability scores) for the first word. By taking the argmax of the predictions, the next word is computed and appended to an empty list ‘Result’.
-   This previous prediction, stored in ‘Result’, is then sent as an input to the model in the next timestep. 

The entire process is repeated until the model produces an `<eos>` token, which indicates the end of the prediction process. 

NOTE: To avoid the situation when no n-gram overlaps are found, a smoothing function can be used. For example:

```python
from nltk.translate.bleu_score import corpus_bleu
from nltk.translate.bleu_score import SmoothingFunction
smoothie = SmoothingFunction().method4
corpus_bleu([reference], candidate, smoothing_function=smoothie)
```

To read more refer to [this](https://www.nltk.org/_modules/nltk/translate/bleu_score.html) documentation

NOTE: The model built in this demonstration is a baseline model and not the state of art model with the available settings. It is recommended for you to explore and play with the notebook, by changing different hyperparameters and epoch duration, to improve the model performance. 

This brings us to the end of NMT implementation. We have seen that the model works very well for shorter sentences. However, whenever it is fed with longer sentences, the model fails to understand the context and performs poorly.

The next session will introduce you to the attention mechanism and will help you in understanding how we can improve the model performance.